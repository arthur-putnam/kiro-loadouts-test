---
title: Data Analysis Skill
description: Expertise in analyzing datasets with pandas and generating insights
tags: [data-analysis, pandas, statistics]
---

# Data Analysis Skill

## Capabilities

This skill provides expertise in:

- Loading and validating datasets
- Exploratory data analysis (EDA)
- Statistical analysis and hypothesis testing
- Data visualization
- Identifying patterns and anomalies
- Generating actionable insights

## Usage

When analyzing data, I will:

1. **Understand the Context**: Ask about the business problem and goals
2. **Validate Data Quality**: Check for missing values, outliers, data types
3. **Explore Distributions**: Analyze statistical properties of variables
4. **Identify Relationships**: Look for correlations and patterns
5. **Visualize Findings**: Create clear, informative plots
6. **Provide Insights**: Translate findings into actionable recommendations

## Example Workflow

```python
# 1. Load and validate
df = pd.read_csv('sales_data.csv')
print(df.info())
print(df.describe())

# 2. Check data quality
missing = df.isnull().sum()
print(f"Missing values:\n{missing[missing > 0]}")

# 3. Explore distributions
df['revenue'].hist(bins=50)
plt.title('Revenue Distribution')
plt.show()

# 4. Analyze relationships
correlation = df[['revenue', 'marketing_spend', 'customer_count']].corr()
sns.heatmap(correlation, annot=True)
plt.show()

# 5. Generate insights
print(f"Average revenue per customer: ${df['revenue'].sum() / df['customer_count'].sum():.2f}")
```

## Best Practices

- Always start with data validation
- Use appropriate statistical tests
- Visualize before and after transformations
- Document assumptions and limitations
- Provide confidence intervals where applicable

