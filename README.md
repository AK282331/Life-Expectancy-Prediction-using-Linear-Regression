Life Expectancy Prediction using Linear Regression
Project Overview
This project focuses on predicting the Life Expectancy of a country using Linear Regression. The goal is to build a model that can estimate the average lifespan based on different economic, social, geographical, and health-related factors.

Dataset
The dataset was taken from Kaggle, originally based on data collected by the World Health Organization (WHO).

It includes data from both developed and developing countries across several years.

Some of the key features in the dataset are:

Adult mortality, infant deaths, alcohol consumption, GDP, schooling, BMI, immunization rates, and more.

Steps Followed
1. Exploratory Data Analysis (EDA)
Removed columns that were not useful.

Applied One Hot Encoding using pd.get_dummies() to handle categorical variables.

Checked correlations between features using a heatmap.

Most features had correlations between -0.5 and 0.5, so multicollinearity was not a big concern.

The target column (Life Expectancy) was negatively skewed, meaning most people live between 65 and 85 years.

2. Outlier Detection and Transformation
Used box plots to identify outliers. Most were genuine, so instead of removing them, I applied a Power Transformer (Yeo-Johnson) to reduce their effect.

3. Relationship Between Features and Target
Plotted scatter plots between each feature and Life Expectancy.

Some features like Income composition of resources, Alcohol, and Schooling showed a visible linear relationship.

4. Handling Missing Values
Used .isnull().sum() to identify missing data.

If missing values were less than 5% in any row, those rows were dropped.

For the rest, missing values were filled using SimpleImputer.

Used a ColumnTransformer to apply transformations in one step.

5. Feature Selection
Used SelectKBest to select the top 10 features.

This helped to focus on only the most important variables for prediction.

6. Model Training
Split the data using Train Test Split.

Trained the model using Ordinary Least Squares (OLS) method.

Checked the p-values of each feature:

Features with p-value > 0.05 were considered not significant and removed.

8 out of 10 features turned out to be statistically significant.

7. Interpreting the Results
The most impactful features (based on coefficient values) were:

Income composition of resources

Adult Mortality

Infant Deaths

Under-five deaths

HIV/AIDS

These features had a bigger influence on predicting life expectancy.

Conclusion
Life expectancy depends on a mix of health, economic, and social factors.

The top contributing features in this analysis were:

Income composition

Schooling

Adult mortality

Infant and under-five deaths

Diphtheria immunization rate

HIV/AIDS rate

Thinness in children (5–9 years)

Recommendations
Policy makers and health organizations should focus on the factors listed above to improve life expectancy.

A larger dataset could improve the model's accuracy.

In future studies, focusing only on key features might help make better and faster predictions.
