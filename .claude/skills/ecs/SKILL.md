```markdown
# ecs Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `ecs` TypeScript codebase. You'll learn about file organization, import/export styles, commit message patterns, and how to write and run tests. These guidelines help maintain code consistency and streamline collaboration.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `entityManager.ts`, `componentStore.ts`

### Import Style
- Use **relative imports** for referencing modules within the project.
  - Example:
    ```typescript
    import { Entity } from './entity';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // entity.ts
    export function createEntity() { ... }
    export const ENTITY_TYPE = 'basic';
    ```

### Commit Messages
- Commit messages are **freeform**, sometimes with prefixes.
- Average commit message length: ~26 characters.
  - Example: `add entity system`, `fix bug in componentStore`

## Workflows

### Adding a New Module
**Trigger:** When you need to add a new feature or module  
**Command:** `/add-module`

1. Create a new file using camelCase naming (e.g., `newFeature.ts`).
2. Use relative imports to include dependencies.
3. Export all functions, types, or constants using named exports.
4. Add corresponding test file as `newFeature.test.ts`.
5. Commit changes with a concise, descriptive message.

### Writing and Running Tests
**Trigger:** When you add or update code and need to ensure correctness  
**Command:** `/run-tests`

1. Create a test file with the pattern `*.test.ts` (e.g., `entityManager.test.ts`).
2. Write tests using the project's testing framework (framework is currently unknown).
3. Run the test suite using the project's test runner (refer to project documentation or scripts).
4. Review and fix any failing tests.

## Testing Patterns

- **Test files** follow the `*.test.ts` pattern and are placed alongside the modules they test.
- The specific testing framework is not detected; check the project for configuration or scripts.
- Example test file:
  ```typescript
  // entityManager.test.ts
  import { createEntity } from './entityManager';

  test('should create a new entity', () => {
    const entity = createEntity();
    expect(entity).toBeDefined();
  });
  ```

## Commands
| Command        | Purpose                                  |
|----------------|------------------------------------------|
| /add-module    | Scaffold a new module with conventions   |
| /run-tests     | Run all test files in the codebase       |
```
