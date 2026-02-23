# Socioeconomic Differences in Age at First Childbirth: Evidence from NHANES 2009-2012
## Table of Contents
1. [NHANES Variable Descriptions](https://github.com/bradleyb98/nhanes-income-childbirth/blob/f176e50b24bfc9bc260002c1b03802cf5ef0a8fa/NHANES_Variable_Descriptions.pdf)
2. [Report: Quarto](https://github.com/bradleyb98/nhanes-income-childbirth/blob/f176e50b24bfc9bc260002c1b03802cf5ef0a8fa/NHANES_Report_Final.qmd)
3. [Report: PDF](https://github.com/bradleyb98/nhanes-income-childbirth/blob/f176e50b24bfc9bc260002c1b03802cf5ef0a8fa/NHANES_Report_Final.pdf)
4. [Figures](https://github.com/bradleyb98/nhanes-income-childbirth/tree/f176e50b24bfc9bc260002c1b03802cf5ef0a8fa/Plots)

##
### Overview
This project examines whether household income is associated with the age at which women have their first child using data from the National Health and Nutrition Examination Survey (NHANES) 2009–2012. Both categorical income group comparisons and continuous poverty ratio modeling were used to evaluate whether reproductive timing differs systematically across socioeconomic strata.

The analysis combines exploratory data visualization, variance-robust ANOVA, post-hoc testing, and linear regression modeling to quantify the strength and structure of this relationship.

##
### Research Question
Does household income influence age at first childbirth among women in the NHANES sample?

### Hypothesis
Women having lower income will have their first child at a younger age compared to women in higher-income groups.

##
### Data Source
* Dataset: NHANES 2009–2012
* Population: Female participants with non-missing age at first childbirth
* Final analytic sample: n = 1,741

### Key Variables
* Age1stBaby – Age at first live birth (continuous outcome)
* IncomeLevel – Four ordered household income categories derived from NHANES income midpoints
* Poverty – Continuous ratio of household income relative to federal poverty guidelines (top-coded at 5)
* Race1 and Education – Included in multivariable modeling

NHANES data were accessed via the NHANES R package.

##
### Methods
**1. Exploratory Data Analysis**
* Distribution assessment via histogram
* Group comparison using side-by-side boxplots
* Scatterplot visualization of poverty ratio vs. age at first childbirth

**2. Group Comparisons**
* One-way ANOVA
* Levene’s test for homogeneity of variance
* Welch’s ANOVA (variance-robust)
* Games–Howell post-hoc comparisons with 95% confidence intervals

**3. Regression Modeling**
* Simple linear regression: Age1stBaby ~ Poverty
* Multiple linear regression: Age1stBaby ~ Poverty + Race1 + Education

Model diagnostics and fit statistics were evaluated, including R², adjusted R², residual standard error, and confidence intervals.

##
### Key Findings
* Age at first childbirth increases monotonically across income groups.
* Welch’s ANOVA showed statistically significant differences in mean age across all income categories.
* Games–Howell tests confirmed that all six pairwise comparisons were significant (p < 0.001).
* In the simple regression model, poverty ratio was positively associated with age at first childbirth (β = 1.02, p < .001), explaining approximately 12% of the variance.
* After adjustment for race/ethnicity and education, the model explained approximately 32% of the variance (adjusted R² = 0.319).
* The association between poverty and age at first childbirth was attenuated but remained statistically significant after adjustment.

Overall, results indicate that reproductive timing is socially patterned by socioeconomic status.

##
### Limitations
* NHANES uses a complex sampling design; survey weights were not applied in this analysis.
* Poverty ratio is top-coded at 5, limiting resolution at higher income levels.
* The analysis is observational and does not support causal inference.

##
### Author
**Bradley Bobbett, M.S. Biological Data Science**

This project was completed as part of graduate training in applied data science and reflects independent analysis, modeling, and interpretation using reproducible R workflows. With any questions, comments, or feedback, please reach out to me at [bradleybobbett@gmail.com](mailto:bradleybobbett@gmail.com).
