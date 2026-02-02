# AP_MSCS634_Assignment
Advanced Big Data and Data Mining

## Purpose
The purpose of this lab is to apply data visualization, data preprocessing, and statistical analysis techniques using Python in a Jupyter Notebook environment. The lab demonstrates how raw data can be explored, cleaned, transformed, and analyzed to extract meaningful insights while following best practices in data mining and analytics.

## Dataset
The analysis was performed on a loan approval dataset, which includes applicant demographic information, financial attributes, and loan approval outcomes. The dataset contains features such as applicant age, income, loan amount, credit score, number of dependents, existing loans, employment status, and loan approval status.

## Key Techniques Used
- Data visualization (box plots, histograms, scatter plots, bar chart)
- Missing value handling
- Outlier detection using IQR
- Data reduction through sampling and column elimination
- Feature scaling and discretization
- Statistical analysis (central tendency, dispersion, correlation)

## Data Preprocessing
The dataset was checked for missing values using isnull().sum(). No missing values were found in any of the columns. Standard missing-value handling techniques (median for numeric attributes and mode for categorical attributes) were still applied to demonstrate preprocessing methodology. After verification, the dataset remained unchanged, confirming that no imputation was required.

## Outlier detection
Outliers were evaluated using the Interquartile Range (IQR) method on the loan_amount attribute. The calculated lower and upper bounds did not identify any records outside the acceptable range. This confirms that the dataset does not contain significant outliers, and no removal or transformation was necessary.

## Data Reduction
A random sample of 60% of the dataset was selected using a fixed random seed to reduce data size while preserving overall characteristics.

The applicant_id column was removed since it is an identifier and does not contribute analytical or predictive value.

## Data Scaling and Discretization
Min-Max scaling was applied to the annual_income attribute to normalize values into a range between 0 and 1.

The annual_income attribute was discretized into three categories—Low, Medium, and High—to simplify analysis and enable categorical comparisons.

## Statistical Analysis
The dataset structure and characteristics were examined using .info() and .describe(), providing details on data types, record counts, and summary statistics.

For the loan_amount attribute, the following measures were calculated Minimum, Maximum, Mean,Median, Mode. These values provide insight into typical loan sizes and the overall distribution.

## Dispersion Measures
Dispersion metrics including range, quartiles, interquartile range (IQR), variance, and standard deviation were computed. The results show significant variability in loan amounts, which is typical for financial datasets.

## Corre;ation Analysis
A correlation matrix was generated for numerical attributes to examine linear relationships between variables. The analysis revealed:
- Moderate positive correlation between loan approval and credit score
- Negative correlations between loan approval and both number of dependents and existing loans
- Weak correlations among most other variables, indicating low multicollinearity

## Key Insights
- Loan approval shows moderate correlation with credit score.
- Loan amount and income have weak linear relationships.
- Loan amounts exhibit significant variability, justifying preprocessing steps.

## Challenges
Interpreting datasets without missing values or outliers required careful justification rather than forced data manipulation.

## Conclusion
This lab demonstrates a complete data mining workflow, from visualization and preprocessing to statistical analysis. The process highlights the importance of understanding data characteristics before applying advanced modeling techniques and reinforces best practices for working with real-world datasets.