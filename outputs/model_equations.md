# Model Architecture & Regression Equations

## Dummy Variable Configuration
To incorporate qualitative attributes into the mathematical models, categorical variables were translated into binary indicator fields ($1$ or $0$). To eliminate statistical redundancy and satisfy structural modeling constraints, a baseline reference category was omitted for each variable profile.

### 1. Region Dummies
* **Dummies Created:** `region_North`, `region_South`, `region_West`
* **Reference Category:** `East` (Omitted baseline; represented when all region indicators equal 0)

### 2. Store Type Dummies
***Dummies Created:** `store_High_Street`, `store_Airport`, `store_Mall`
***Reference Category:** `Residential` (Omitted baseline; represented when all store type indicators equal 0)

Simple Linear Regression Models & Business Interpretation

## Model 1: Marketing Spend Performance
* **Dependent Variable ($Y$):** `monthly_sales`
* **Independent Variable ($X$):** `marketing_spend`

### 1. Regression Equation
$$\text{monthly\_sales} = 560,777.35 + 2.1296 \times (\text{marketing\_spend})$$

### 2. R-squared
* **Value:** 0.1672 (16.72%)
* **Interpretation:** Approximately 16.72% of the variation in monthly store sales is explained by marketing spend alone.

### 3. Coefficient
* **Intercept ($\beta_0$):** 560,777.35
* **Marketing Spend ($\beta_1$):** 2.1296

### 4. P-value
* **Value:** $2.48 \times 10^{-14}$ (Effectively 0.0000)

### 5. Business Interpretation
* **Baseline Sales:** If a store allocates zero budget to monthly marketing, it is structurally predicted to clear a baseline revenue of **$560,777.35**.
* **Marginal Return Multiplier:** For every **$1.00** addition to the monthly marketing budget, a store's sales are expected to expand by **$2.13**.

### 6. Variable Usefulness Evaluation
* **Status:** **Highly Useful.** The p-value sits exponentially below the standard $\alpha = 0.05$ significance threshold, indicating that marketing spend is a statistically reliable and positive top-line driver.

## Model 2: Footfall Traffic Performance
* **Dependent Variable ($Y$):** `monthly_sales`
* **Independent Variable ($X$):** `footfall`

### 1. Regression Equation
$$\text{monthly\_sales} = 446,410.58 + 35.6780 \times (\text{footfall})$$

### 2. R-squared
* **Value:** 0.7363 (73.63%)
* **Interpretation:** Roughly 73.63% of the differences in monthly sales across store locations are explained by customer traffic patterns alone.

### 3. Coefficient
* **Intercept ($\beta_0$):** 446,410.58
* **Footfall Traffic ($\beta_1$):** 35.6780

### 4. P-value
* **Value:** $4.75 \times 10^{-94}$ (Effectively 0.0000)

### 5. Business Interpretation
* **Baseline Sales:** If physical footfall drops to zero, the predicted baseline sales structure rests at **$446,410.58**.
* **Traffic Multiplier:** Every **single customer addition** to physical store traffic yields an average expected sales increase of **$35.68** over the course of the month.

### 6. Variable Usefulness Evaluation
* **Status:** **Critical/Highly Useful.** With an exceptionally strong R-squared of 73.63% and a p-value practically near zero, footfall represents the most powerful single operational factor available to leadership for sales generation.

## Multiple Linear Regression Model

* **Dependent Variable ($Y$):** `monthly_sales`
* **Independent Variables ($X$):** `marketing_spend`, `footfall`, `avg_discount_pct`, `region_North`, `region_South`, `region_West`
* **Mathematical Equation:**
  $$\text{monthly\_sales} = 391327.13 + 1.1428(M) + 33.7593(F) - 72697.03(D) + 13427.78(R_N) + 21268.10(R_S) + 19854.55(R_W)$$

### Coefficient Interpretations:
1. **Intercept (391,327.13):** The predicted average baseline monthly sales for a store located in the reference region (**East**) with zero marketing layout, no footfall traffic, and no discounting mechanics.
2. **Marketing Spend ($1.1428$):** Holding all other factors constant, every additional $1 spent on marketing yields $1.14 in sales.
3. **Footfall ($33.7593$):** The strongest absolute driver. Each additional customer visiting the store increases monthly sales by $33.76.
4. **Average Discount Pct ($-72,697.03$):** Shows a negative trajectory but is statistically insignificant ($p > 0.05$), meaning aggressive discounting may erode top-line margins without reliably driving sales volume.
5. **Regional Shifts (South: $21,268.10$ | West: $19,854.55$):** Holding operational inputs equal, stores in the South and West statistically outperform the baseline **East** branch by roughly $21.3k and $19.9k respectively.

* **Final Model Selection:** The **Multiple Linear Regression Model** is selected as the definitive operational framework.
* **Selection Rationale:** Moving from simple regression to a multiple regression framework expanded the model's explanatory power (R-Squared) from 16.72% (Marketing) and 73.63% (Footfall) up to **79.26%**, minimizing the standard error to 47,706.49.
