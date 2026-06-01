# MSCS_634_Lab_1

## Overview

This lab demonstrates a complete data analysis workflow using Python, Pandas, NumPy, and Matplotlib. The objective is to explore a Sample Superstore dataset, create meaningful visualizations, apply preprocessing techniques, and perform statistical analysis.

---

## Dataset Description

The dataset file used in this project is:

```text
SampleSuperstore.csv
```

The dataset includes the following columns:

- Ship Mode
- Segment
- Country
- City
- State
- Postal Code
- Region
- Category
- Sub-Category
- Sales
- Quantity
- Discount
- Profit

This dataset is useful for exploratory data analysis because it contains both categorical and numerical variables. The categorical variables help compare sales performance across regions, categories, sub-categories, and customer segments. The numerical variables support statistical analysis, outlier detection, scaling, and correlation analysis.

---

## Objectives

The main objectives of this lab are:

1. Load the Sample Superstore dataset into a Pandas DataFrame.
2. Display the first five rows of the dataset.
3. Create meaningful visualizations to explore the dataset.
4. Detect and handle missing values.
5. Identify and manage outliers using the IQR method.
6. Apply data reduction using sampling and column elimination.
7. Apply Min-Max Scaling and discretization.
8. Perform statistical analysis using central tendency, dispersion, and correlation measures.

---

## Data Visualization

Several visualization techniques were used to explore the dataset.

### Scatter Plot: Sales vs Profit

A scatter plot was created to analyze the relationship between Sales and Profit.

**Insight:**  
The scatter plot shows that higher sales do not always lead to higher profit. Some high-sales transactions have low or negative profit, which may be related to discounts or product costs.

### Line Plot: Average Profit by Category

Since this version of the dataset does not include an order date column, a line plot was used to compare average profit across product categories.

**Insight:**  
The line plot shows differences in average profitability among product categories. This helps identify which categories are generally more profitable.

### Bar Chart: Total Sales by Category

A bar chart was used to compare total sales across product categories.

**Insight:**  
The bar chart shows which categories contribute the most to total sales. This is useful for understanding overall revenue distribution.

### Histogram: Sales Distribution

A histogram was created to display the distribution of sales values.

**Insight:**  
The sales distribution is right-skewed. Most transactions have smaller sales values, while a smaller number of transactions have very high sales values.

### Box Plot: Profit

A box plot was used to examine the spread of profit values and identify potential outliers.

**Insight:**  
The profit column contains several unusually high and low values. These outliers may influence statistical measures such as the mean and standard deviation.

### Pie Chart: Order Distribution by Region

A pie chart was used to show the proportion of records from each region.

**Insight:**  
The pie chart shows how sales records are distributed across regions. This helps compare geographic representation in the dataset.

---

## Data Preprocessing

### Handling Missing Values

Missing values were checked using Pandas. Numerical columns were handled using mean replacement, and categorical columns were handled using mode replacement.

### Outlier Detection and Removal

The Interquartile Range method was used to detect outliers in the Profit column.

The process included:

1. Calculating Q1 and Q3.
2. Computing the IQR.
3. Calculating lower and upper bounds.
4. Identifying records outside those bounds.
5. Removing the identified outliers for further analysis.

### Data Reduction

Data reduction was performed in two ways:

1. A 30% sample of the cleaned dataset was selected.
2. Less relevant columns such as Postal Code and Country were removed.

The Country column was removed because all records belong to the same country. Postal Code was removed because it is more useful as an identifier than as an analytical variable.

### Data Scaling and Discretization

Min-Max Scaling was applied to the following numerical columns:

- Sales
- Profit
- Quantity
- Discount

Sales values were also discretized into the following categories:

- Low
- Medium
- High
- Very High

---

## Statistical Analysis

### General Overview

The `.info()` function was used to inspect column names, data types, and non-null counts. The `.describe()` function was used to generate summary statistics for numerical columns.

### Central Tendency Measures

The following measures were calculated:

- Minimum
- Maximum
- Mean
- Median
- Mode

These measures helped summarize the typical values and range of each numerical variable.

### Dispersion Measures

The following measures were calculated:

- Range
- Quartiles
- Interquartile Range
- Variance
- Standard Deviation

These measures helped understand how spread out the numerical values are.

### Correlation Analysis

A correlation matrix was created for the numerical columns:

- Sales
- Profit
- Quantity
- Discount

**Insight:**  
The correlation matrix helped identify relationships among numerical variables. For example, discount may negatively affect profit, while sales and profit may show a positive but imperfect relationship.

---

## Key Findings

- Higher sales do not always guarantee higher profit.
- Discounts may reduce profitability.
- Sales values are right-skewed, with many small transactions and fewer large transactions.
- Profit contains noticeable outliers.
- Product categories differ in both total sales and average profit.
- Regional distribution varies across the dataset.
- Scaling makes numerical features easier to compare.

---

## Challenges and Decisions

No major challenges in this exercise

One key decision was to use Profit for outlier detection because profit values can include both unusually high gains and significant losses. The IQR method was selected because it is simple, effective, and less affected by extreme values than methods based only on the mean.

---

## Conclusion

This lab exercis used Sample Superstore dataset to demonstrate a complete data analysis workflow. The dataset was loaded, visualized, preprocessed, reduced, scaled, and analyzed using statistical techniques. The results showed meaningful patterns in sales, profit, discounts, product categories, and regions. These steps form an important foundation for data mining and more advanced analytics.
