# Sales Manager Performance Analysis

### Overview

This real-world project explores whether a Sales Manager's number of direct reports has an influence on their performance, focusing on two key questions:

1. Does the number of direct reports affect H1 performance?
2. Does office location affect H1 performance?

The analysis was carried out using Python, combining:

- Data cleaning and preparation (pandas)
- Visual exploration (matplotlib / seaborn)
- Simple Linear Regression (scikit-learn)
- Statistical testing (ANOVA)

The goal was to determine whether these factors are meaningful predictors of performance. The findings of this project had a real-world business impact, particularly in terms of headcount discussions between senior stakeholders.

---

## Dataset

**Note:** The original dataset is not included due to confidentiality.

The dataset contained anonymised records at a manager level with the following fields:

| Column | Description |
|------|------------|
| SDP Manager | Manager identifier |
| Office | Office location |
| No. Direct Reports | Team size |
| H1 Performance | Performance as a proportion of target (e.g. 1.2 = 120%) |

---

## Data Preparation

Before analysis, the dataset was cleaned to ensure consistency and reliability:

- Converted relevant columns to numeric types
- Handled missing and invalid values
- Removed rows where key fields were missing
- Standardised column formats for modelling

This step was important to ensure that the model was using accurate and comparable data.

---

### Analysis 1: Direct Reports vs Performance

## Approach

To assess whether team size influences performance:

- Created a scatter plot to visualise the relationship
- Calculated correlation between variables
- Built a **Simple Linear Regression** model

---

## Key Results

- **Correlation ≈ 0**
- **R² ≈ 0.0002**
- **MAE ≈ 0.45 (≈ 45 percentage points)**
- **RMSE ≈ 0.58 (≈ 58 percentage points)**

---

## What these metrics mean

- **R² (≈ 0)**
The model explains ~0% of the variation in performance  
Team size provides almost no useful information

- **MAE (≈ 45%)**  
On average, predictions are off by ~45 percentage points  
Example: actual = 120%, predicted could be ~75% or ~165%

- **RMSE (≈ 58%)**  
Some errors are even larger, showing wide variability

---

## Interpretation

- The regression line is almost flat
- Predictions are highly inaccurate
- Team size does not meaningfully predict performance

**Conclusion:**  

There is **no meaningful relationship** between number of direct reports and H1 performance.

---

### Analysis 2: Performance by Office

## Approach

To assess whether office location affects performance:

- Compared distributions using box plots
- Analysed mean performance using bar charts
- Applied a **one-way ANOVA test**

---

## Key Result

- **ANOVA p-value ≈ 0.455**

---

## What this means

ANOVA tests whether differences between office averages are real or just random variation.

- A low p-value (< 0.05) --> meaningful differences  
- A high p-value (> 0.05) --> differences are likely random  

In this case:

- The observed differences between offices are not statistically significant.

---

## Interpretation

- No clear performance advantage for any office
- Differences are due to individual variation, not location

**Conclusion:**  

Office location does not meaningfully influence performance.

---

### Final Takeaways

Across both analyses:

- Team size is not a predictor of performance
- Office location is not a predictor of performance  

Performance appears to be driven more by individual or operational factors, rather than structural ones.

---

### Next Steps

To better understand performance drivers, future analysis could include:

- Manager tenure
- Historical performance trends
- Sales activity metrics
- Team composition
- Territory / account complexity

A multivariate model (Multiple Linear Regression - MLR) would provide deeper insights by analysing multiple variables together.

---

### Tech Stack

- Python
- pandas
- matplotlib / seaborn
- scikit-learn
- scipy

---

### Key Learning

This project reinforced the importance of:

- Taking ownership of a business question, thinking through my project, and working to find an answer to it end-to-end
- Not relying on intuition alone (e.g. bigger teams = better results)
- Validating findings with analysis metrics 
- Understanding when a model is not useful, which can be just as valuable as finding a strong relationship

### Challenges I Faced

- Initially communicating findings to a non-technical audience, in a way that made it easy for them to effectively feedback to senior stakeholders
- Standardising data types and handling NULLs
