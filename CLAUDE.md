# Development Guidelines

## Core Development Principles

### Project Structure
- Use `src`-layout: `src/your_package_name/`
- Tests in `tests/` directory
- Configuration via environment variables
- Requirements in `pyproject.toml`

### Package Management
- ONLY use `uv` for dependency management
- Install: `uv add package`
- Upgrade: `uv add package --upgrade`
- Development tools: `uv run tool`

## Code Quality Standards

### Type System
- Mandatory type hints for all functions
- Use `typing` module for complex types
- Prefer `Optional[Type]` over `Type | None`
- Define custom types in `types.py`

### Naming Conventions
- Functions/variables: `snake_case`
- Classes: `PascalCase`
- Constants: `UPPER_SNAKE_CASE`
- Prefix handlers with "handle_"

### Code Style
- Maximum line length: 88 characters
- Use Black for formatting
- Use isort for import sorting
- Prefer f-strings for string formatting
- Use absolute imports

### Functional Principles
- Prioritize immutable approaches
- Use early returns to reduce nesting
- Keep functions small and focused
- Implement DRY (Don't Repeat Yourself) principle
- Minimize code footprint

## Testing Requirements
- Framework: pytest
- Async testing: use anyio
- 100% coverage for new features
- Test edge cases and error scenarios
- Regression tests for bug fixes

## Error Handling
- Use specific exceptions
- Provide clear error contexts
- Utilize `from e` for exception chaining
- Avoid generic exception handling

## Development Workflow

### Commit Guidelines
- Descriptive commit messages
- For bug fixes:
  ```bash
  git commit --trailer "Reported-by:<n>"
  ```
- For GitHub issues:
  ```bash
  git commit --trailer "Github-Issue:#<number>"
  ```

### Code Review
- Create detailed PR descriptions
- Focus on problem-solving approach
- Reviewer: ArthurClune

## Tools and Validation

### Code Formatting
1. Ruff
   - Format: `uv run ruff format .`
   - Lint: `uv run ruff check .`
   - Fix: `uv run ruff check . --fix`

2. Type Checking
   - Tool: pyright
   - Explicit None checks
   - Type narrowing

3. Pre-commit Hooks
   - Runs on git commit
   - Checks: 
     - Formatting
     - Type checking
     - Import sorting

## Performance and Maintainability
- Write readable code
- Optimize selectively
- Create reusable components
- Minimize complexity
- Document public APIs thoroughly

## Forbidden Practices
- No `pip` usage
- No `@latest` package syntax
- No co-authorship mentions
- Avoid commenting obvious code