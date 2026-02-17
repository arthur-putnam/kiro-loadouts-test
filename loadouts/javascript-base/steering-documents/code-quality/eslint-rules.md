---
title: ESLint Rules and Standards
inclusion: always
tags: [eslint, code-quality, javascript]
---

# ESLint Rules and Standards

## Core Principles

- Enforce consistent code style across the project
- Catch common errors before runtime
- Follow industry best practices
- Maintain readability and maintainability

## Recommended Rules

### Error Prevention

```json
{
  "rules": {
    "no-unused-vars": "error",
    "no-undef": "error",
    "no-console": "warn",
    "no-debugger": "error"
  }
}
```

### Code Quality

```json
{
  "rules": {
    "eqeqeq": ["error", "always"],
    "curly": ["error", "all"],
    "no-var": "error",
    "prefer-const": "error",
    "prefer-arrow-callback": "error"
  }
}
```

### Modern JavaScript

- Use `const` and `let` instead of `var`
- Use arrow functions for callbacks
- Use template literals instead of string concatenation
- Use destructuring where appropriate
- Use async/await instead of promise chains

## Auto-fixing

Run ESLint with auto-fix:

```bash
npm run lint -- --fix
```

