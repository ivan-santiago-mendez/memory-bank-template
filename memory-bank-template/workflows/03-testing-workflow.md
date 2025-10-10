# Testing Workflow

This document defines the testing strategy, execution procedures, and quality assurance standards for the intapi-assistant project.

## Testing Strategy

### Test Pyramid
```
           /\
          /  \    E2E / Functional Tests
         /____\
        /      \   Integration Tests
       /________\
      /          \  Unit Tests
     /____________\
```

- **Unit Tests**: Fast, isolated tests of individual components (~70%)
- **Integration Tests**: Tests of module interactions and external dependencies (~20%)
- **Functional Tests**: End-to-end tests of complete use cases (~10%)

## Test Execution

### Running Tests Locally

#### All Tests (Excludes Integration & Functional by Default)
```bash
mise run test
```

#### Specific Test Class
```bash
mise run test_one <TestClassName>

# Examples:
mise run test_one ChatServiceSpec
mise run test_one PromptLoaderSpec
```

#### Integration Tests
```bash
# Integration tests require SAP XSUAA and Azure AI configuration
# Set environment variables in ~/.gradle/gradle.properties

gradle test --tests "*IntegrationTest*"
```

#### Functional Tests
```bash
# Functional tests require external services
gradle test -PexecuteFunctionalTests=true
```

#### Full Test Suite (CI/CD)
```bash
# Run everything including integration and functional tests
gradle test -PexecuteFunctionalTests=true
```

## Test Types and Conventions

### Unit Tests (Spock)

**Location**: `*/src/test/groovy/**/*Spec.groovy`

**Example**:
```groovy
class ChatServiceSpec extends Specification {

    ChatService chatService
    PromptService mockPromptService

    def setup() {
        mockPromptService = Mock(PromptService)
        chatService = new ChatService(
            promptService: mockPromptService
        )
    }

    def "should return welcome message when user input is empty"() {
        given: "an empty user input"
        def userInput = ""
        def conversationId = UUID.randomUUID().toString()

        when: "calling chat service"
        def response = chatService.call(userInput, "WORKING_CAPITAL", conversationId)

        then: "welcome message is returned"
        response.success == true
        response.messages.size() == 1
        response.messages[0].content.contains("Hello")
    }
}
```

**Best Practices**:
- Use Spock's BDD-style: given/when/then
- Mock external dependencies
- Test one behavior per test method
- Use descriptive test names
- Test happy path and edge cases

### Integration Tests

**Location**: `*/src/test/groovy/**/*IntegrationTest.groovy`

**Example**:
```groovy
@SpringBootTest
@ActiveProfiles("test")
class ChatServiceIntegrationSpec extends BaseServicesIntegrationTest {

    @Autowired
    ChatService chatService

    @Autowired
    ConversationMessageRepository messageRepository

    def "should persist conversation messages to database"() {
        given: "a valid user input"
        def userInput = "What is working capital?"
        def conversationId = UUID.randomUUID().toString()

        when: "calling chat service"
        def response = chatService.call(userInput, "WORKING_CAPITAL", conversationId)

        then: "messages are persisted"
        def messages = messageRepository.findByConversationThreadId(conversationId)
        messages.size() >= 2 // user + assistant messages
    }
}
```

**Best Practices**:
- Use Testcontainers for Docker dependencies
- Test actual integration points
- Clean up test data after each test
- Use realistic test data

### Functional Tests

**Location**: `*/src/test/groovy/**/*FunctionalTest.groovy` or `**/*FunctionalSpec.groovy`

**Example**:
```groovy
@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
@ActiveProfiles("functional")
class BuyerAssistantFunctionalSpec extends Specification {

    @Autowired
    TestRestTemplate restTemplate

    def "should complete end-to-end buyer assistant conversation"() {
        given: "a buyer assistant query"
        def request = new QueryRequest(
            userInput: "Show me my payment forecast",
            category: "WORKING_CAPITAL"
        )

        when: "sending request to API"
        def response = restTemplate.postForEntity(
            "/api/v1/assistant/query",
            request,
            MessageResponse
        )

        then: "response is successful"
        response.statusCode == HttpStatus.OK
        response.body.success == true
        response.body.messages.size() > 0
    }
}
```

**Best Practices**:
- Test complete user workflows
- Include authentication if required
- Test with realistic production-like data
- Verify side effects (database, external calls)

## Test Organization

### Test File Naming
- Unit tests: `*Spec.groovy` (Spock convention)
- Integration tests: `*IntegrationTest.groovy`
- Functional tests: `*FunctionalTest.groovy` or `*FunctionalSpec.groovy`

### Package Structure
Mirror production code structure:
```
services/src/main/groovy/com/taulia/assistant/services/llm/ChatService.groovy
services/src/test/groovy/com/taulia/assistant/services/llm/ChatServiceSpec.groovy
```

## Writing Good Tests

### Test Naming
Use descriptive names that explain behavior:
```groovy
// Good
def "should return error when conversation thread id is invalid"()

// Bad
def "testChat()"
```

### Test Structure
Follow AAA pattern (Arrange/Act/Assert):
```groovy
def "descriptive test name"() {
    given: "context and setup"
    // Arrange - set up test data and mocks

    when: "action is performed"
    // Act - execute the code under test

    then: "expected outcome"
    // Assert - verify results
}
```

### Test Data
```groovy
// Use builders or factories for complex objects
def createTestQueryRequest() {
    new QueryRequest(
        userInput: "test input",
        category: "WORKING_CAPITAL",
        conversationThreadId: UUID.randomUUID().toString()
    )
}

// Use constants for repeated values
static final String TEST_CONVERSATION_ID = "test-conv-123"
```

### Mocking
```groovy
// Mock external dependencies
def mockPromptService = Mock(PromptService)

// Define mock behavior
mockPromptService.getPrompt(_ as String) >> new Prompt("test prompt")

// Verify interactions
1 * mockPromptService.getPrompt("WORKING_CAPITAL")
```

## Test Coverage

### Coverage Goals
- **Unit Tests**: 80%+ code coverage
- **Integration Tests**: Cover all critical paths
- **Functional Tests**: Cover all major use cases

### Measuring Coverage
```bash
# Generate coverage report
gradle test jacocoTestReport

# View report
open build/reports/jacoco/test/html/index.html
```

### Coverage Guidelines
- Focus on business logic, not boilerplate
- Cover edge cases and error scenarios
- Don't sacrifice test quality for coverage numbers

## Testing Checklist

### Before Committing
- [ ] All tests pass locally
- [ ] New code has corresponding tests
- [ ] Tests are meaningful and maintainable
- [ ] No commented-out or skipped tests
- [ ] Test names are descriptive

### Before Creating PR
- [ ] Full test suite passes
- [ ] Integration tests pass (if applicable)
- [ ] Manual testing completed
- [ ] Performance impact considered

### During Code Review
- [ ] Tests cover new functionality
- [ ] Tests are well-structured
- [ ] Edge cases tested
- [ ] No flaky or intermittent tests

## Common Testing Patterns

### Testing Spring AI Integration
```groovy
@SpringBootTest
class SpringAiIntegrationSpec extends Specification {

    @Autowired
    ChatClient chatClient

    def "should call LLM with correct prompt"() {
        given: "a user message"
        def userMessage = new UserMessage("test input")

        when: "sending to chat client"
        def response = chatClient.prompt()
            .user("test input")
            .call()
            .chatResponse()

        then: "response is received"
        response != null
        response.result.output.text != null
    }
}
```

### Testing with Testcontainers
```groovy
@SpringBootTest
@Testcontainers
class DatabaseIntegrationSpec extends Specification {

    @Container
    static MySQLContainer mysql = new MySQLContainer("mysql:8.0.16")
        .withDatabaseName("test_db")
        .withUsername("test")
        .withPassword("test")

    @DynamicPropertySource
    static void setProperties(DynamicPropertyRegistry registry) {
        registry.add("spring.datasource.url", mysql::getJdbcUrl)
        registry.add("spring.datasource.username", mysql::getUsername)
        registry.add("spring.datasource.password", mysql::getPassword)
    }
}
```

### Testing Async Operations
```groovy
def "should handle async operation"() {
    given: "an async operation"
    CompletableFuture<String> future = service.asyncMethod()

    when: "waiting for completion"
    def result = future.get(5, TimeUnit.SECONDS)

    then: "result is returned"
    result == "expected value"
}
```

## Troubleshooting Tests

### Flaky Tests
```bash
# Run test multiple times to identify flakiness
for i in {1..10}; do mise run test_one FlakyTest; done

# Common causes:
# - Timing dependencies
# - Shared state between tests
# - External service dependencies
# - Race conditions
```

### Test Debugging
```groovy
// Add logging
log.info("Test data: {}", testObject)

// Use Spock's printed output
println "Debug: ${variable}"

// Enable detailed error messages
def "test with detailed error"() {
    expect:
    actual == expected || {
        println "Expected: ${expected}, but got: ${actual}"
        false
    }()
}
```

### Test Performance
```bash
# Run tests with profiling
gradle test --profile

# View profile report
open build/reports/profile/profile-<timestamp>.html
```

## Continuous Integration

### CI Test Execution
```yaml
# Example GitHub Actions workflow
- name: Run tests
  run: |
    mise run test
    gradle test -PexecuteFunctionalTests=true

- name: Upload test results
  if: always()
  uses: actions/upload-artifact@v3
  with:
    name: test-results
    path: build/test-results/
```

### Test Failure Handling
- All tests must pass before merge
- Investigate and fix failures immediately
- No disabling tests without ticket
- Document flaky tests in ticket

---

_Last updated: 2025-10-09_