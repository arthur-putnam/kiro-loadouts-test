---
title: TypeScript Configuration
inclusion: always
tags: [typescript, configuration]
---

# TypeScript Configuration for React

## Strict Mode Configuration

Always enable strict mode in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "strictFunctionTypes": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true
  }
}
```

## Type Definitions

### Component Props

Always define explicit prop types:

```tsx
interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
  disabled?: boolean;
}

export function Button({ label, onClick, variant = 'primary', disabled }: ButtonProps) {
  return <button onClick={onClick} disabled={disabled}>{label}</button>;
}
```

### Event Handlers

Use proper event types:

```tsx
function handleChange(event: React.ChangeEvent<HTMLInputElement>) {
  console.log(event.target.value);
}

function handleClick(event: React.MouseEvent<HTMLButtonElement>) {
  event.preventDefault();
}
```

## Common Patterns

### Generic Components

```tsx
interface ListProps<T> {
  items: T[];
  renderItem: (item: T) => React.ReactNode;
}

function List<T>({ items, renderItem }: ListProps<T>) {
  return <ul>{items.map(renderItem)}</ul>;
}
```

