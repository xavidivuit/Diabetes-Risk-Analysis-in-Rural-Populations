# Analysis of Type 2 Diabetes in Rural Populations

An R Markdown analysis of Type II diabetes risk factors in a rural African American population from Central Virginia, based on clinical, anthropometric and biochemical data.

**Author:** Xavier Tarragó  
**Date:** January 2026

## Dataset

Data sourced from the [Vanderbilt Biostatistics Repository](https://hbiostat.org/data/repo/cdiabetes), originally collected by Dr. John Schorling (University of Virginia). It includes 403 subjects from two rural localities — Buckingham and Louisa — with variables covering blood glucose, HbA1c, total cholesterol, HDL, blood pressure, BMI, and waist/hip measurements. A subject is classified as diabetic if HbA1c > 7.0%.

The dataset file (`diabetes.csv`) must be placed in the working directory before running the analysis.

## Research Questions

1. Which anthropometric and clinical variables are the strongest predictors of Type II diabetes?
2. Can the waist/hip ratio serve as an early marker for diabetes risk?
3. Is there evidence of "Syndrome X" (co-occurrence of hypertension and diabetes) in this population?
4. Can k-means clustering identify subgroups with distinct metabolic risk profiles?
5. How does metabolic risk evolve with age?
6. Does postprandial time influence glucose and HbA1c levels?
7. Are there sex differences in metabolic risk markers?

## Structure

| Section | Content |
|---|---|
| 1. Introduction | Study context, dataset description, research questions |
| 2. EDA | Data cleaning, missing value handling, outlier assessment, descriptive statistics |
| 3. Inference | Diabetes prevalence, demographic risk factors, Monte Carlo simulation |
| 4. Predictor Analysis | Logistic regression, correlation analysis, k-means clustering, Syndrome X assessment |
| 5. Shiny App | Interactive data explorer with filters by gender, location, diagnosis, and age |

## Key Findings

- ~15% of individuals in the dataset meet the HbA1c > 7.0% threshold for diabetes.
- The **Cholesterol/HDL ratio** is the strongest predictor (logistic regression, p < 0.001), followed by systolic blood pressure.
- The **waist/hip ratio** is a statistically significant early marker for diabetes risk (chi-square p < 0.05 in both sexes), using sex-specific thresholds (>0.94 for men, >0.84 for women).
- **No evidence of Syndrome X** was found: blood pressure was not significantly associated with diabetes diagnosis (chi-square p = 0.48).
- **K-means clustering** (k = 3) identified three distinct risk profiles: high (~90% diabetic), moderate (~11%), and low (~1%).
- No significant sex differences were observed in HbA1c, glucose, or blood pressure.

## Requirements

```r
install.packages(c("readr", "dplyr", "ggplot2", "patchwork", "shiny", "DT"))
```

R version 4.0 or higher is recommended.

## Running the Analysis

1. Clone the repository and set it as your working directory.
2. Place `diabetes.csv` in the same folder as the `.Rmd` file.
3. Open the `.Rmd` in RStudio and click **Knit**, or run:

```r
rmarkdown::render("Analysis-of-Type-2-Diabetes-in-Rural-Populations.Rmd")
```
The embedded Shiny app will launch automatically when the document is rendered with `runtime: shiny`.

## References

- Willems JP et al. (1997). Prevalence of coronary heart disease risk factors among rural blacks. *Southern Medical Journal*, 90, 814–820.
- Schorling JB et al. (1997). A trial of church-based smoking cessation interventions for rural African Americans. *Preventive Medicine*, 26, 92–101.

