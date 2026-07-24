# Analysis of Risk Factors Associated with Heart Attacks in Indonesia

*Evidence from Clinical and Demographic Data*

Group project (team of 3) completed for the **Applied Machine Learning and Predictive Modelling** course.

## Objective

Explore the relationships between demographic and clinical variables and the occurrence of a heart attack. Using exploratory data analysis, statistical models, and machine learning methods, the project examines patterns and associations in the data and assesses each model's predictive performance.

## Data Source

**Heart Attack Risk Factors dataset** from [Kaggle](https://www.kaggle.com/), covering Indonesia. 158'355 observations and 28 variables spanning demographic factors (age, gender, region, income), lifestyle behaviors (smoking, alcohol, physical activity, diet, sleep), environmental factors (air pollution, stress), and clinical measurements (blood pressure, cholesterol, blood sugar, triglycerides, EKG results). After cleaning, a random sample of 10'000 observations was used for analysis.

## Approach

1. **Data cleaning & preparation**: engineered a risk-factor count variable, checked for missing values and duplicates (none found), converted binary/categorical fields to factors, verified class balance (~60/40 split on the target), and sampled 10'000 rows for a manageable working dataset.
2. **Exploratory data visualization**: examined relationships between age, blood pressure, cholesterol, fasting blood sugar, and heart attack status.
3. **Linear regression**: modeled fasting blood sugar against demographic/clinical predictors, using partial F-tests to identify the strongest contributors.
4. **Logistic regression (GLM, binomial)**: modeled heart attack occurrence directly, checked for multicollinearity (VIF), simplified the model via likelihood ratio tests, and interpreted odds ratios.
5. **Generalized Additive Model (GAM)**: tested for non-linear effects of continuous predictors (age, fasting blood sugar) on heart attack risk.
6. **Poisson regression (GLM)**: modeled the engineered risk-factor count as a count outcome.
7. **Support Vector Machine (my lead)**: trained a linear-kernel SVM on an 80/20 stratified train/test split, evaluated with a confusion matrix, ROC curve, and AUC.
8. **Neural network**: trained a feed-forward neural network (1 hidden layer, 3 neurons) on standardized numeric predictors as a final predictive comparison.

## Tools & Technologies

`R` · `tidyr` · `dplyr` · `ggplot2` · `readr` · `readxl` · `ggforce` · `plotly` · `car` · `mgcv` · `corrplot` · `ggfortify` · `caret` · `e1071` · `pROC` · `neuralnet`

## Key Findings

- **Logistic regression** identified age, hypertension, diabetes, cholesterol level, obesity, fasting blood sugar, previous heart disease, and smoking status as significant predictors of heart attack risk. In odds-ratio terms, previous heart disease (5.4x), hypertension (4.7x), diabetes (3.5x), and obesity (2.7x) were the strongest risk multipliers, while each additional year of age raised the odds by about 3%.
- The **GAM** revealed that age and fasting blood sugar affect risk non-linearly. Risk stays relatively flat before rising sharply past certain age and blood-sugar thresholds, a pattern a purely linear model would miss.
- The **SVM** was the strongest overall predictive model, reaching 72% accuracy and an AUC of 0.79. Good discriminative ability between heart attack and non–heart attack cases.
- The **neural network** underperformed, matching the no-information baseline at 60.2% accuracy and catching only 24% of true heart attack cases (sensitivity), not reliable for detection in its current form.
- Across all models, **sensitivity was a persistent weak point**, meaning a meaningful share of true heart attack cases went undetected, a critical limitation for any real-world screening use case.

## My Role

Led the **Support Vector Machine** modeling stage. Preparing the train/test split, training and tuning the model, and evaluating performance via confusion matrix, ROC curve, and AUC. Also contributed to the shared data cleaning and exploratory analysis stages alongside the team.

## How to View

Open `Analysis_of_risk_factors_associated_with_heart_attacks.Rmd` in RStudio or open `Analysis_of_risk_factors_associated_with_heart_attacks.pdf` directly to read the rendered report.

