# Poverty and Diabetes Prevalence: An Inference-Based Analysis

## Overview

This project examines the association between state-level poverty prevalence and diabetes prevalence in the United States using data from the **CDC Chronic Disease Indicators (CDI)** dataset. The analysis focuses on **statistical inference**, modeling how average diabetes prevalence varies with poverty prevalence across states, rather than predicting individual outcomes.

The goal is to understand population-level health disparities through an interpretable, assumption-driven regression framework. Exploratory visualizations were generated for both 2019 and 2021. Formal regression inference is presented for 2019, with results for 2021 used as a robustness check.

---

## Research Question

**Is there a statistically significant association between state-level poverty prevalence and age-adjusted diabetes prevalence in the United States?**

---

## Data

- **Source:** CDC Chronic Disease Indicators (CDI)
- **Unit of analysis:** U.S. states
- **Year analyzed:** 2019 
- **Key variables:**
  - **Poverty prevalence (%):** Proportion of the population living below 150% of the federal poverty threshold (crude prevalence)
  - **Diabetes prevalence (%):** Age-adjusted prevalence of diagnosed diabetes among adults

Age-adjusted diabetes prevalence is used to allow comparisons across states with different age distributions.

---

## Methodology

We modeled the conditional mean of diabetes prevalence as a linear function of poverty prevalence using **ordinary least squares (OLS) regression**:

`E[Y | X] = β₀ + β₁X`

where:
- `Y` is diabetes prevalence,
- `X` is poverty prevalence,
- `β₁X` represents the average change in diabetes prevalence associated with a one–percentage point increase in poverty prevalence.

OLS is equivalent to **maximum likelihood estimation** under the assumption of independent, normally distributed errors with constant variance.

### Assumptions

- Linearity of the conditional mean  
- Independence of state-level observations  
- Mean-zero errors  
- Approximate homoskedasticity  
- Normality of errors for valid inference  

These assumptions were assessed visually using scatterplots and residual diagnostics.

---

## Results

The estimated slope for 2019 was:

- **β̂₁ = 0.33**
- **95% confidence interval:** (0.25, 0.41)
- **p < 0.001**

This indicates a statistically significant positive association between poverty prevalence and diabetes prevalence at the state level. A parallel analysis conducted for 2021 yielded a similarly positive association, indicating temporal robustness of the estimated relationship.




**Interpretation:**  
On average, a one percentage-point increase in poverty prevalence is associated with an approximately 0.33 percentage-point increase in diabetes prevalence across states.

---

## Visualizations

The analysis includes:

- A scatterplot of poverty prevalence versus diabetes prevalence with the estimated conditional mean and 95% confidence band
- A choropleth map showing geographic variation in diabetes prevalence across U.S. states

These visualizations support the plausibility of a linear mean relationship and highlight regional health disparities.

---

## Interpretation and Scope

This analysis is **ecological** and **associational**. Results describe population-level relationships and should not be interpreted as causal or applied to individuals. Potential confounding factors (e.g., access to healthcare, demographic composition, environmental exposures) are not explicitly modeled.

---

## Tools

- Python  
- pandas, NumPy  
- statsmodels  
- matplotlib, plotly  
- Jupyter Notebook  
- Git & GitHub  

---

## Next Steps

Potential extensions include:

- Adding additional social determinants as covariates  
- Comparing results across multiple years  
- Using robust or clustered standard errors  
- Exploring spatial dependence  

---

## Author

*Donjhai "DJ" Holland*
