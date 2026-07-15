# Agent Principles

## Core Principles

### Decoupling
- Components must be independent and loosely coupled
- Use interfaces and abstractions to define boundaries
- Avoid direct dependencies between unrelated modules
- Changes in one module should not require changes in others

### Testing
- **Unit Tests**: Every function/method must have unit tests covering happy path, edge cases, and error conditions
- **Integration Tests**: Test interactions between modules, APIs, and external services
- Tests must be fast, reliable, and deterministic
- Aim for high test coverage but prioritize meaningful tests over coverage metrics

### Self-Documenting Code
- Code should be readable without requiring comments
- Use meaningful names for variables, functions, and classes
- Functions should do one thing and do it well
- Keep functions short and focused
- Use TypeScript types to document contracts

### Separation of Concerns
- Each module/class has a single responsibility
- Business logic separate from data access and presentation
- Configuration separate from implementation
- Routes separate from controllers separate from services

## Code Review Checklist
- [ ] No direct dependencies between unrelated modules
- [ ] Unit tests for new code
- [ ] Integration tests for new features
- [ ] Code is self-documenting
- [ ] Each module has a single responsibility
- [ ] No premature optimization
- [ ] Error handling is appropriate
- [ ] Security considerations addressed
