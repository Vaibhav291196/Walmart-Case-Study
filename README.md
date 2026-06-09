# Walmart Customer Purchase Behavior Analysis

## Overview

This project analyzes customer purchasing behavior at Walmart using transactional retail data. The objective is to understand spending patterns across different customer demographics such as gender, age, marital status, occupation, and product categories.

The analysis leverages Exploratory Data Analysis (EDA), Statistical Inference, the Central Limit Theorem (CLT), and Bootstrapping techniques to estimate customer spending behavior and provide actionable business recommendations for Walmart's inventory planning and marketing strategies.

---

## Business Problem

Walmart wants to better understand its customers' purchasing behavior to improve inventory management, targeted promotions, and customer experience.

This project aims to answer the following business questions:

- Do male and female customers spend differently?
- Does marital status influence purchasing behavior?
- Which age groups contribute the most revenue?
- What product categories are preferred by different customer segments?
- How can statistical inference help estimate customer spending patterns?

---

## Dataset Information

The dataset contains customer-level transaction records collected from Walmart stores.

### Features

| Feature | Description |
|----------|------------|
| User_ID | Unique customer identifier |
| Product_ID | Unique product identifier |
| Gender | Customer gender |
| Age | Age group |
| Occupation | Occupation category |
| City_Category | Customer city category |
| Stay_In_Current_City_Years | Number of years in current city |
| Marital_Status | Married (1) / Unmarried (0) |
| Product_Category | Product category purchased |
| Purchase | Purchase amount |

### Dataset Summary

- Records: 550,068
- Features: 10
- Missing Values: None
- Dataset Size: ~42 MB

---

## Project Workflow

### 1. Data Understanding

Performed:

- Dataset inspection
- Data type validation
- Missing value analysis
- Shape verification
- Statistical summaries

#### Key Findings

- No missing values present.
- 550,068 customer transactions available.
- Both categorical and numerical features present.
- Data suitable for statistical inference.

---

### 2. Data Cleaning & Outlier Treatment

Outliers were detected using:

- Boxplots
- Distribution analysis

Continuous variables analyzed:

- Purchase Amount
- Product Category
- Occupation

Outlier treatment was performed using percentile clipping:

```python
clipped_purchase = np.clip(
    purchase,
    purchase.quantile(0.05),
    purchase.quantile(0.95)
)
```

---

### 3. Exploratory Data Analysis

#### Product Preferences Across Age Groups

Analysis revealed:

- Product Categories 1–5 are the most purchased across all age groups.
- Product Categories 15–20 have the lowest sales volume.
- Customers aged 18–45 contribute the majority of purchases.

#### Product Preferences by Gender

Key observations:

- Both males and females prefer Product Categories 1–8.
- Male customers make more purchases than female customers.
- Product demand patterns remain similar across genders.

#### Marital Status Analysis

Findings indicate:

- Unmarried customers account for a higher number of purchases.
- Product category preferences remain largely consistent across marital groups.

---

## Statistical Analysis

The project uses inferential statistics to estimate population purchasing behavior.

### Central Limit Theorem (CLT)

The Central Limit Theorem was applied to estimate customer spending behavior using different sample sizes:

- n = 300
- n = 3,000
- n = 30,000

As sample size increases:

- Sampling distributions become more normal.
- Confidence intervals become narrower.
- Estimates become more stable.

---

## Gender-Based Spending Analysis

### Average Purchase Amount

| Gender | Average Purchase |
|----------|----------------|
| Female | 8,734 |
| Male | 9,438 |

### Key Findings

- Male customers spend more on average.
- Confidence intervals for males and females overlap significantly.
- Spending patterns are relatively similar despite higher male averages.

---

## Marital Status Spending Analysis

### Average Purchase Amount

| Marital Status | Average Purchase |
|---------------|----------------|
| Unmarried | 9,266 |
| Married | 9,261 |

### Key Findings

- Spending behavior is nearly identical.
- Confidence intervals overlap substantially.
- Marital status has minimal impact on spending.

---

## Age-Based Spending Analysis

### Average Purchase by Age Group

| Age Group | Average Purchase |
|------------|----------------|
| 0–17 | 8,933 |
| 18–25 | 9,170 |
| 26–35 | 9,253 |
| 36–45 | 9,331 |
| 46–50 | 9,209 |
| 51–55 | 9,535 |
| 55+ | 9,336 |

### Key Findings

- Age group 51–55 has the highest average spending.
- Age group 0–17 has the lowest spending.
- Confidence intervals overlap across age groups.
- Spending differences are relatively small.

---

## Bootstrapping Analysis

Bootstrapping was used to estimate confidence intervals without relying solely on theoretical assumptions.

### Procedure

1. Random sampling with replacement
2. 1000 bootstrap iterations
3. Mean purchase calculation
4. Confidence interval estimation

### Insights

- Bootstrap results closely matched CLT estimates.
- Larger sample sizes produced tighter confidence intervals.
- Sampling distributions approached normality.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

---

## Project Structure

```text
Walmart-Customer-Purchase-Analysis/
│
├── data/
│   └── walmart_data.csv
│
├── notebooks/
│   └── Walmart_Business_Case.ipynb
│
├── README.md

```

---

## Key Business Insights

### Customer Spending Behavior

- Male customers spend slightly more than female customers.
- Spending patterns remain largely similar across genders.

### Marital Status Impact

- Married and unmarried customers exhibit nearly identical spending behavior.
- No major business differentiation required.

### Age-Based Purchasing Power

- Customers aged 51–55 generate the highest average revenue.
- Younger customers spend comparatively less.

### Product Category Demand

- Product Categories 1–8 dominate sales.
- Higher-numbered product categories contribute less to revenue.

---

## Business Recommendations

### Inventory Optimization

Maintain higher inventory levels for frequently purchased product categories (1–8).

### Demographic-Based Marketing

Focus premium product campaigns on customers aged 36–55, who demonstrate higher purchasing power.

### Gender-Neutral Promotions

Since spending confidence intervals overlap, large-scale gender-specific inventory strategies may not be necessary.

### Customer Retention

Develop loyalty programs targeting high-spending age groups to increase customer lifetime value.

### Future Analysis

Future enhancements may include:

- Seasonal purchase behavior analysis
- Monthly sales trend analysis
- Customer Lifetime Value (CLV) modeling
- Product recommendation systems
- Customer segmentation using clustering techniques

---

## Results

The analysis demonstrates that while demographic factors such as gender and age influence spending behavior, the differences are relatively small and confidence intervals overlap considerably. Statistical inference using CLT and Bootstrapping confirms the stability of these estimates and provides Walmart with reliable insights for inventory planning and customer-focused decision making.

---

## Author

**Vaibhav Solanke**

Data Analyst | Business Analytics | Statistical Inference | Machine Learning

---

## License

This project is intended for educational and analytical purposes only.
