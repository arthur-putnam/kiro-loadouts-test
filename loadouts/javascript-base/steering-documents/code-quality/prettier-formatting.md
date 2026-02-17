---
title: Prettier Formatting Standards
inclusion: always
tags: [prettier, formatting, code-style]
---

# Prettier Formatting Standards

## Configuration

Use this `.prettierrc` configuration:

```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 100,
  "tabWidth": 2,
  "useTabs": false,
  "arrowParens": "always"
}
```

## Formatting Rules

### Semicolons

Always use semicolons:

```javascript
// ✅ Good
const x = 5;
const y = 10;

// ❌ Bad
const x = 5
const y = 10
```

### Quotes

Use single quotes for strings:

```javascript
// ✅ Good
const message = 'Hello, world!';

// ❌ Bad
const message = "Hello, world!";
```

### Line Length

Keep lines under 100 characters for readability.

### Trailing Commas

Use trailing commas in multi-line objects and arrays:

```javascript
// ✅ Good
const obj = {
  name: 'John',
  age: 30,
};

// ❌ Bad
const obj = {
  name: 'John',
  age: 30
};
```

## Editor Integration

Configure your editor to format on save for automatic formatting.

