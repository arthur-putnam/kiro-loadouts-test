---
title: Pandas Best Practices
inclusion: fileMatch
fileMatchPattern: "**/*.py"
tags: [python, pandas, data-science]
---

# Pandas Best Practices

## Efficient Data Loading

```python
import pandas as pd

# Use appropriate dtypes to save memory
df = pd.read_csv('data.csv', dtype={
    'id': 'int32',
    'category': 'category',
    'value': 'float32'
})

# Parse dates during loading
df = pd.read_csv('data.csv', parse_dates=['date_column'])
```

## Vectorized Operations

Always prefer vectorized operations over loops:

```python
# ❌ Bad - slow loop
for idx, row in df.iterrows():
    df.at[idx, 'new_col'] = row['col1'] * row['col2']

# ✅ Good - vectorized
df['new_col'] = df['col1'] * df['col2']
```

## Method Chaining

Use method chaining for readable data transformations:

```python
result = (df
    .query('age > 18')
    .groupby('category')
    .agg({'value': ['mean', 'sum']})
    .reset_index()
)
```

## Memory Management

```python
# Check memory usage
df.memory_usage(deep=True)

# Optimize dtypes
df['category_col'] = df['category_col'].astype('category')

# Use chunking for large files
for chunk in pd.read_csv('large_file.csv', chunksize=10000):
    process(chunk)
```

## Common Pitfalls

- Avoid `inplace=True` - it's not actually faster
- Use `.loc` and `.iloc` for indexing, not chained indexing
- Be careful with `SettingWithCopyWarning`
- Use `.copy()` when creating derived DataFrames

