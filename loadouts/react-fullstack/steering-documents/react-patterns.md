---
title: React Patterns and Best Practices
inclusion: always
tags: [react, patterns, components]
---

# React Patterns and Best Practices

## Component Structure

When building React components, follow these patterns:

### Functional Components with Hooks

Always prefer functional components with hooks over class components:

```tsx
import { useState, useEffect } from 'react';

export function UserProfile({ userId }: { userId: string }) {
  const [user, setUser] = useState(null);
  
  useEffect(() => {
    fetchUser(userId).then(setUser);
  }, [userId]);
  
  return <div>{user?.name}</div>;
}
```

### Custom Hooks for Reusable Logic

Extract reusable logic into custom hooks:

```tsx
function useUser(userId: string) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  
  useEffect(() => {
    setLoading(true);
    fetchUser(userId)
      .then(setUser)
      .finally(() => setLoading(false));
  }, [userId]);
  
  return { user, loading };
}
```

## State Management

- Use `useState` for local component state
- Use `useContext` for shared state across components
- Consider Redux or Zustand for complex global state
- Keep state as close to where it's used as possible

## Performance Optimization

- Use `React.memo` for expensive components
- Use `useMemo` for expensive calculations
- Use `useCallback` for stable function references
- Avoid inline object/array creation in render

## File Organization

```
src/
  components/
    Button/
      Button.tsx
      Button.test.tsx
      Button.module.css
  hooks/
    useUser.ts
    useAuth.ts
  utils/
    api.ts
```

