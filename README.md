# Analyzing and Predicting College Graduation Rates

## 1. Problem Definition

### Objective
This project aims to analyze and predict college graduation rates based on various institutional characteristics, including:

- Public vs. private status
- Elite status
- Student enrollment
- Tuition costs
- Faculty qualifications
- Alumni donations

### Goal
Develop regression models to:
- Explain variability in graduation rates.
- Identify key predictors influencing outcomes.

---

## 2. Data Collection and Understanding

### Dataset
The data was sourced from the `College.csv` file and includes information for 775 universities across 17 variables:

- **Institutional Characteristics**: Private (Private/Public), Elite status.
- **Student Metrics**: Applications (Apps), Acceptances (Accept), Enrollments (Enroll), Full-time and Part-time Undergraduates (F.Undergrad, P.Undergrad).
- **Financial Metrics**: Out-of-state tuition (Outstate), Room and board (Room.Board), Books, Personal expenses (Personal).
- **Faculty**: Percentage of faculty with PhDs (PhD) or terminal degrees (Terminal), Student-Faculty Ratio (S.F.Ratio).
- **Alumni and Expenditures**: Percentage of alumni donations (perc.alumni), Instructional expenditure per student (Expend).
- **Outcome**: Graduation rate (Grad.Rate).

---

## 3. Data Exploration and Cleaning

### Exploration Steps
- **Dimensionality Check**: 775 observations, 17 variables.
- **Random Sampling**: Created a subset of 700 observations using a fixed random seed for reproducibility.
- **Summary Statistics**: Key characteristics of the data:
  - 504 private universities, 196 public universities.
  - Distribution of tuition costs, enrollment, and expenses analyzed.

### Visualizations
- Histograms for out-of-state tuition, room and board, and personal expenses to understand variance.
- Bar plots for private/public and elite/non-elite distributions.

---

## 4. Data Preprocessing

### Steps
- **Data Partitioning**: Analyzed trends separately for private/public and elite/non-elite universities.
- **Feature Selection**: Started with all variables, narrowed to significant predictors based on statistical analyses.

---

## 5. Model Building

### Regression Models
1. **Simple Linear Regression**:
   - Predictors: `Private`, `Elite`.
   - **Adjusted R-squared**: 22.35%.
   - **F-statistic**: 101.6 (p-value < 2.2e-16).

2. **Multiple Linear Regression**:
   - Included all 17 variables.
   - **Adjusted R-squared**: 44.59%.
   - Significant Predictors: `Private`, `Apps`, `Outstate`, `PhD`, `perc.alumni`, `Expend`.

### Model Comparison
- ANOVA confirmed that the multiple regression model significantly outperforms the simple regression model.

---

## 6. Model Evaluation

### Diagnostic Plots
- **Residuals vs Fitted Values**: Showed slight non-linearity.
- **Q-Q Plot**: Residuals not fully normal.
- **Scale-Location Plot**: Homoscedasticity assumption satisfied.
- **Leverage Plot**: Identified high-influence points.

---

## 7. Model Improvement

### Techniques
1. **Variable Selection**:
   - Used exhaustive search to select the top 8 predictors: `Private`, `Apps`, `Outstate`, `PhD`, `perc.alumni`, `Expend`, and others.
   - **Adjusted R-squared**: 43.94%.

2. **Polynomial Regression**:
   - Improved **Adjusted R-squared** to 45.29%.

3. **Interaction Terms**:
   - Added interactions like `Private * Apps`.
   - Final **Adjusted R-squared**: 46.08%.

---

## 8. Conclusion

### Final Model
- The final model explained **46.08%** of the variance in graduation rates.
- Key predictors included:
  - **Private/Public Status**: Private colleges tend to have higher graduation rates.
  - **Applications Received**: More applications correlate with better graduation rates.
  - **Out-of-State Tuition**: Higher tuition positively impacts graduation rates.
  - **Alumni Donations**: Alumni engagement correlates with institutional success.

---

## 9. Future Work and Recommendations

### Suggestions
1. **Enhance Dataset**:
   - Include additional variables like student demographics, financial aid, or academic quality metrics.
2. **Non-Linear Models**:
   - Explore machine learning methods such as decision trees, random forests, or gradient boosting for improved predictions.
3. **Model Validation**:
   - Implement cross-validation techniques to ensure generalization to unseen data.
4. **Policy Implications**:
   - Use insights to guide resource allocation, improve student retention, and boost graduation rates.

---

## Project Highlights
- **R² Improvement**: From 22.35% (Simple Linear Regression) to 46.08% (Final Model with Interaction Terms).
- **Significant Predictors**: Institutional type, tuition, faculty qualifications, and alumni engagement.
- **Future Applications**: Tailored strategies for colleges to improve graduation outcomes and resource planning.
