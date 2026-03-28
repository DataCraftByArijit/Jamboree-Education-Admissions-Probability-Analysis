# Jamboree Education Admissions Probability Analysis (Industry: EdTech / Education)
This project explores Jamboree Education's case study data to analyze the key academic and profile factors influencing graduate admissions to top global universities, successfully predicting a student's probability of admission.

# Project Overview
This project examines graduate applicant data to uncover how various parameters—such as GRE, TOEFL, CGPA, and Research experience—impact the chances of getting into Ivy League colleges.  It aims to answer key questions such as: Which independent variables have the most significant impact on graduate admissions? How do academic merit and research background collectively influence outcomes? The insights derived can help Jamboree refine its prediction algorithms and offer targeted counseling to students to improve specific weak areas.

# Problem Statement
Jamboree seeks to build a robust Linear Regression model to accurately estimate a candidate's Chance of Admit based on critical profile parameters. The objective is to identify driver variables, explore relationships among them, rigorously validate statistical assumptions, and leverage these insights to optimize student counseling strategies.

# Objectives
 * Perform Exploratory Data Analysis (EDA) to understand the structure and distribution of applicant data.
 * Preprocess the data by verifying missing values, treating outliers, and transforming features using MinMaxScaler.
 * Build and compare Linear, Ridge, and Lasso Regression models to predict admission probabilities.
 * Test the underlying assumptions of linear regression: Multicollinearity (VIF), Mean of Residuals, Linearity, Homoscedasticity, and Normality.
 * Evaluate model performance using metrics like MAE, RMSE, R-squared, and Adjusted R-squared.
 * Provide actionable strategic recommendations to help students target and improve their application profiles.

# Data Set
 * Serial No.: Unique row ID
 * GRE Score: GRE Scores (out of 340)
 * TOEFL Score: TOEFL Scores (out of 120)
 * University Rating: University Rating (out of 5)
 * SOP: Statement of Purpose Strength (out of 5)
 * LOR: Letter of Recommendation Strength (out of 5)
 * CGPA: Undergraduate GPA (out of 10)
 * Research: Research Experience (either 0 or 1)
 * Chance of Admit: Chance of Admit (ranging from 0 to 1)

# Milestones
 * Load and inspect dataset to identify variables and data types.
 * Check data quality — dataset has no missing values and 0 duplicate records.
 * Conduct Non-Graphical and Visual Analysis using boxplots and distribution plots to identify feature behaviors and 3 outliers.
 * Analyze group-wise relationships and multicollinearity using a Correlation Heatmap.
 * Data preparation and scaling using MinMaxScaler().
 * Build initial OLS Linear Regression and evaluate R2, Adj R2, MSE, RMSE, and MAE.
 * Apply Ridge and Lasso Regression to handle multicollinearity without losing critical features.
 * Validate regression assumptions using Variance Inflation Factor (VIF), Goldfeld-Quandt test (Homoscedasticity), and Shapiro-Wilk test (Normality).
 * Compile findings and business recommendations.

# Findings
 * The initial dataset contains 500 records and 9 columns, with no missing values or duplicates. 
 * 3 records were identified as outliers and subsequently removed.
 * The standard Linear Regression model has a good fit, showing an R-squared of 0.8234 for training data and 0.8154 for test data.
 * Ridge and Lasso regressions yielded similar accuracy to the standard linear regression model.
 * The dataset exhibits high multi-collinearity; CGPA (39.16), TOEFL Score (28.64), and GRE Score (27.93) showed very high VIF scores.
 * Dropping multi-collinear variables (like CGPA and GRE) mathematically satisfied VIF constraints but severely reduced the model's predictive power (Test R-squared dropped to 0.4167) and removed key real-world predictors.
 * Ridge Regression was chosen as the ideal model because it handles multi-collinearity mathematically without requiring the deletion of critical data.
 * The mean residual for both the Training Data and Test Data under the Ridge model is nearly 0.
 * The Goldfeld-Quandt test yielded a p-value > 0.05, meaning we fail to reject the null hypothesis; the data is Homoskedastic.
 * The Shapiro-Wilk test yielded p-values > 0.05 for residuals, confirming the residuals are normally distributed.
 * CGPA has the highest positive correlation (0.88) with Chance of Admit.
 * GRE and TOEFL scores are highly correlated with each other (0.83).

# Recommendations
 * **Prioritize GPA Enhancement:** Because CGPA has the strongest correlation with admission, Jamboree's counseling should prioritize GPA enhancement or strongly recommend universities that align strictly with a student's GPA tier. A high GRE score may not fully compensate for a low GPA.
 * **Offer Bundled Exam Prep Packages:** GRE and TOEFL scores move closely together. Students struggling with the English language (TOEFL) are highly likely to struggle with the Verbal section of the GRE. Jamboree should create combined prep packages that address verbal reasoning holistically across both tests.
 * **Leverage Research as a Key Differentiator:** For students with average GPAs or test scores, having research experience acts as a unique lever to pull. Jamboree should consider partnering with research internship programs to provide profile-building services for borderline candidates.
 * **Focus on Hard Metrics over Soft Documents:** The correlation for LOR (0.65) and SOP (0.68) is demonstrably lower than for hard metrics like GPA and test scores. Counselors should ensure students do not neglect GRE prep in order to spend disproportionate time trying to "perfect" their SOP, as hard data acts as the primary gatekeeper.

# Colab Link
 * https://colab.research.google.com/drive/1rHJ81kXhTFpIysbiYEqUOvdm4pdMoh17

# Data Link
 * https://drive.google.com/file/d/1VO1Fu2QydSyJw0krmVICx-U0vStHL3vF/view?usp=drive_link

