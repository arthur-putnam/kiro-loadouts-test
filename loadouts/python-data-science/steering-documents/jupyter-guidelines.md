---
title: Jupyter Notebook Guidelines
inclusion: fileMatch
fileMatchPattern: "**/*.ipynb"
tags: [jupyter, notebooks, data-science]
---

# Jupyter Notebook Guidelines

## Notebook Structure

Organize notebooks with clear sections:

1. **Imports and Setup** - All imports at the top
2. **Data Loading** - Load and validate data
3. **Exploratory Analysis** - Initial exploration
4. **Data Cleaning** - Handle missing values, outliers
5. **Analysis/Modeling** - Main analysis
6. **Results and Visualization** - Present findings
7. **Conclusions** - Summary and next steps

## Best Practices

### Keep Cells Small and Focused

```python
# ✅ Good - one logical operation per cell
df = pd.read_csv('data.csv')
```

```python
# ✅ Good - separate cell for validation
print(f"Shape: {df.shape}")
print(f"Columns: {df.columns.tolist()}")
```

### Use Markdown for Documentation

Add markdown cells to explain your analysis:

```markdown
## Data Cleaning

We need to handle missing values in the following columns:
- `age`: 5% missing - will impute with median
- `income`: 2% missing - will drop rows
```

### Restart and Run All

Before sharing or committing:
1. Restart kernel
2. Run all cells
3. Verify all outputs are correct

### Version Control

- Use `.gitignore` to exclude output cells
- Consider using `nbstripout` to clean notebooks
- Keep notebooks focused and under 100 cells

## Visualization

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Set style once at the top
sns.set_style('whitegrid')
plt.rcParams['figure.figsize'] = (12, 6)

# Create clear, labeled plots
plt.figure()
sns.histplot(data=df, x='value', bins=30)
plt.title('Distribution of Values')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()
```

