---
title: Jest Testing Guide
inclusion: fileMatch
fileMatchPattern: "**/*.test.{js,jsx,ts,tsx}"
tags: [testing, jest, react-testing-library]
---

# Jest Testing Guide for React

## Test Structure

Follow the Arrange-Act-Assert pattern:

```tsx
import { render, screen } from '@testing-library/react';
import { UserProfile } from './UserProfile';

describe('UserProfile', () => {
  it('displays user name when loaded', async () => {
    // Arrange
    const mockUser = { id: '1', name: 'John Doe' };
    
    // Act
    render(<UserProfile userId="1" />);
    
    // Assert
    expect(await screen.findByText('John Doe')).toBeInTheDocument();
  });
});
```

## Testing Best Practices

### Test User Behavior, Not Implementation

```tsx
// ❌ Bad - testing implementation details
expect(component.state.isOpen).toBe(true);

// ✅ Good - testing user-visible behavior
expect(screen.getByRole('dialog')).toBeVisible();
```

### Use Testing Library Queries

Priority order:
1. `getByRole` - Most accessible
2. `getByLabelText` - For form fields
3. `getByPlaceholderText` - For inputs
4. `getByText` - For non-interactive elements
5. `getByTestId` - Last resort

### Mock External Dependencies

```tsx
jest.mock('./api', () => ({
  fetchUser: jest.fn(() => Promise.resolve({ name: 'Test User' }))
}));
```

## Coverage Goals

- Aim for 80%+ code coverage
- Focus on critical paths and edge cases
- Don't chase 100% coverage at the expense of test quality

