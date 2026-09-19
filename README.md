# NovaRetail Customer Correlation Analysis

## Project Overview

NovaRetail is a Latin American e-commerce platform looking to better understand which customer behavior factors are most strongly associated with annual revenue.

The main business question for this project is:

**Which customer behavior variables are most strongly associated with annual revenue?**

This project is an **exploratory correlation analysis**, so the results are interpreted as associations rather than causal relationships.

> Correlation does not imply causation.

---

## Business Objective

The goal of this analysis is to identify which customer characteristics and behavioral variables show the strongest statistical relationships with `ingreso_anual` (annual revenue).

The analysis focuses on variables such as:

- Monthly visits
- Monthly purchases
- Targeted advertising spend
- Premium membership
- Churn
- Age
- Income level
- Satisfaction
- Region
- Device type

The objective is not to prove causality, but to identify patterns that could guide future customer segmentation, marketing analysis, and experimentation.

---

## Dataset

The dataset contains customer-level behavioral and profile information for NovaRetail.

Key variables include:

- `ingreso_anual`
- `compras_mes`
- `visitas_mes`
- `gasto_publicidad_dirigida`
- `miembro_premium`
- `abandono`
- `edad`
- `nivel_ingreso`
- `satisfaccion`
- `region`
- `tipo_dispositivo`

---

## Methodology

Different statistical methods were used depending on the type of variables being compared.

### Numerical variables

Two correlation coefficients were used:

- **Pearson correlation** to measure linear relationships
- **Spearman correlation** to evaluate monotonic relationships and reduce sensitivity to extreme values

### Numerical vs Binary Variables

**Point-biserial correlation** was used to evaluate relationships such as:

- `miembro_premium` vs. `ingreso_anual`
- `abandono` vs. `ingreso_anual`

### Categorical Variables

**Cramér's V** was used to evaluate the association between categorical variables such as:

- `region`
- `tipo_dispositivo`

---

## Exploratory Data Analysis

The analysis included:

- Correlation heatmaps
- Scatterplots
- Distribution analysis
- Pearson and Spearman coefficients
- Point-biserial correlations
- Cramér's V
- Business interpretation of statistical results

The visual analysis was focused on the relationships most relevant to annual revenue rather than plotting every possible variable combination.

---

## Key Findings

### 1. Monthly visits show the most relevant behavioral association with annual revenue

Monthly visits show a positive association with annual revenue:

- **Pearson:** approximately 0.34
- **Spearman:** approximately 0.32

Customers who visit the platform more frequently tend to generate higher annual revenue, although the relationship is dispersed and far from deterministic.

This suggests that visit frequency may be a useful behavioral signal, but it should not be interpreted as a direct cause of higher revenue.

---

### 2. Targeted advertising spend shows a weak positive association with annual revenue

The relationship between targeted advertising spend and annual revenue is positive but weak:

- **Pearson:** approximately 0.20
- **Spearman:** approximately 0.18

This indicates that customers associated with higher advertising investment tend to generate slightly more revenue, but the relationship is limited.

The result suggests that advertising effectiveness may depend on additional factors such as customer profile, visit frequency, campaign characteristics, or customer segment.

---

### 3. Monthly purchases and annual revenue show very high collinearity

`compras_mes` and `ingreso_anual` show a correlation of approximately **0.97**.

This is the strongest relationship in the dataset.

However, because both variables are conceptually closely related and display very similar relationships with the rest of the numerical variables, this result is treated primarily as evidence of **statistical redundancy and collinearity**, rather than as an independent behavioral insight.

For this reason, monthly purchases are used mainly as a reference variable rather than as one of the main business findings.

---

### 4. Profile variables show very weak associations on their own

Some customer profile variables show little individual association with annual revenue.

Examples include:

- `miembro_premium` vs. `ingreso_anual`: approximately **0.09**
- `abandono` vs. `ingreso_anual`: approximately **-0.003**
- `region` vs. `tipo_dispositivo`: Cramér's V approximately **0.012**

These results suggest that these variables provide limited explanatory value when analyzed independently.

However, they may still become useful when combined with behavioral variables or used for customer segmentation.

---

## Business Implications

The analysis suggests that customer behavior variables may be more informative than profile variables when studying annual revenue.

Potential business applications include:

- Using visit frequency as a signal for identifying higher-value customers
- Evaluating conversion from visits to purchases
- Measuring advertising effectiveness by customer segment
- Combining profile and behavioral variables to create richer customer segments
- Investigating whether high-visit, low-conversion customers require different commercial strategies

---

## Limitations

Several limitations should be considered when interpreting the results:

- **Correlation does not imply causation.**
- Relevant variables may be missing from the dataset.
- Most relationships were analyzed individually rather than jointly.
- Strong collinearity exists between `compras_mes` and `ingreso_anual`.
- Weak individual correlations do not necessarily mean that a variable has no business value.

Potential missing variables include:

- Average order value
- Product category
- Customer tenure
- Promotion usage
- Purchase channel
- Campaign characteristics

---

## Next Steps

Future analysis could include:

- Customer segmentation based on behavioral variables
- Visit-to-purchase conversion analysis
- Advertising effectiveness by customer segment
- Multivariate statistical models
- Predictive modeling
- Additional behavioral and transactional variables
- Controlled experiments and A/B testing

These approaches could help determine which combinations of variables provide the most useful information about customer value and annual revenue.

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Google Colab

---

## Skills Demonstrated

This project demonstrates experience in:

- Exploratory Data Analysis
- Correlation Analysis
- Pearson Correlation
- Spearman Correlation
- Point-Biserial Correlation
- Cramér's V
- Data Visualization
- Collinearity Analysis
- Statistical Interpretation
- Business Insight Generation
- Customer Behavior Analysis
- Data-Driven Recommendations

---

## Repository Structure

```text
novaretail-customer-correlation-analysis/
├── README.md
├── NovaRetail_customer_behavior_analysis.ipynb
└── novaretail_comportamiento_clientes_2024.csv
