```markdown
# shenyu Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and workflows used in the `shenyu` Java codebase. It covers coding conventions, commit patterns, testing strategies, and step-by-step instructions for common repository workflows—especially around improving test coverage. This guide is ideal for contributors looking to align with the project's established practices.

## Coding Conventions

### File Naming
- **Style:** PascalCase  
  Example:  
  ```java
  public class UserServiceImpl { ... }
  ```

### Import Style
- **Relative imports** are used within the codebase.  
  Example:  
  ```java
  import org.apache.shenyu.common.utils.JsonUtils;
  ```

### Export Style
- **Named exports** are preferred for clarity and maintainability.  
  Example:  
  ```java
  public class PluginDataHandler { ... }
  ```

### Commit Patterns
- **Conventional commits** are used, with prefixes such as `test` and `chore`.
- **Average commit message length:** ~63 characters.
- **Examples:**
  - `test: add unit tests for PluginDataHandler`
  - `chore: update dependencies for security patch`

## Workflows

### Improve Test Coverage
**Trigger:** When you want to improve or ensure code quality and coverage for a module, package, or class.  
**Command:** `/improve-test-coverage`

1. **Identify** classes or packages with low or missing test coverage.
2. **Add** new test files or enhance existing test files under the corresponding test directory:
   ```
   src/test/java/<package>/
   ```
3. **Commit** your changes with a message referencing improved test coverage for the targeted area.
   - Example commit message:  
     ```
     test: increase coverage for UserServiceImpl
     ```
4. **Push** your changes and open a pull request for review.

#### Example: Adding a Test Case
```java
// src/test/java/org/apache/shenyu/plugin/UserServiceImplTest.java

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class UserServiceImplTest {

    @Test
    void shouldReturnUserWhenIdExists() {
        UserServiceImpl service = new UserServiceImpl();
        User user = service.findById(1);
        assertNotNull(user);
    }
}
```

## Testing Patterns

- **Testing Framework:** Not explicitly detected, but Java projects commonly use JUnit.
- **Test File Pattern:** Test files are placed under `src/test/java/` and follow the `*.java` naming convention, typically ending with `Test`.
- **Example Test File:**
  ```java
  // src/test/java/org/apache/shenyu/plugin/PluginDataHandlerTest.java

  import org.junit.jupiter.api.Test;
  import static org.junit.jupiter.api.Assertions.*;

  public class PluginDataHandlerTest {

      @Test
      void testHandleData() {
          PluginDataHandler handler = new PluginDataHandler();
          assertTrue(handler.handleData("test"));
      }
  }
  ```

## Commands

| Command                 | Purpose                                                        |
|-------------------------|----------------------------------------------------------------|
| /improve-test-coverage  | Initiate the workflow to improve or add test coverage to code. |
```
