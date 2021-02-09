# Lead-Scoring-LOGIT
X education wants to know most promising leads. For that they want to build a Model which identifies the hot leads. Deployment of the model for the future use


Data Preparation
• Reading the data and performing some data quality checks, Identifying data types and visually inspecting the data
• Converting all the Yes/No variables into Binary i.e. 0/1 values to be used later
• Multiple columns filled with ‘Select’ values are found, Converted them to NaNs to be treated ahead
• Data Cleaning
1. Checkingthepercentageofmissingvaluesineachcolumn
2. Dropping the columns with at least 70% missing values
3. Columnbycolumntreatmentofalltheothercolumnswithmissing values
4. Skewed columns were found i.e. having over 80% of the same value, these were dropped
5. Categorical columns with numerous values were found, making them hard to interpret, These columns were condensed to contain only the most frequent values and ‘others’ category
6. Following this process, only a few rows were left which still contained missing values, these rows were dropped as they were only 1-2% rows
7. 98.2% of the data was retained after cleaning the data
1
 Exploratory Data Analysis
The Analysis was done by plotting each of the variables against the dependent variable ‘Converted’ to infer insights from the current data, Some insights found were as follows :
• Most of the traffic driven through Google and Directly through the website has a higher chance of conversion
• The leads to whom SMS were sent out have a higher conversion rate
• Leads with Asymmetric Activity Index as Medium have higher chance of conversion
Model Building
• Dummy Variables were used in order to allow the model to interpret categorical variables effectively, whereas binary variables as converted earlier could be used directly
• Train Test Split from sklearn was used to split the data into test and training sets and the chosen split was 70 Train/ 30 Test
• Standard Scaler was used to scale the data making numerical columns better predictors and improving the model performance
• Feature Selection was done using Recursive Feature Elimination (RFE) and the top 30 variables were chosen
• The first model was built with 30 variables and many insignificant variables having P-Values > 0.05 were found, these were to be dropped
• The process of model building and feature selection went on and the resulting model was finalised
• The model contains of all significant variables and low (<5) VIF values
• ROC Curve was plotted and the AUC (Area under Curve) was 0.96 proving the high performance of the model
• The optimal cut-off point was found to be 0.3, found by maximising Accuracy, Sensitivity & Specificity
• The model was used to predict on the test set thereafter
2

Model Evaluation
• Sensitivity - 85.7%
• Specificity - 87.6%
• False Positive Rate - 12.3% • Precision Score - 83.1%
• Business Aspects
A. Sensitivity of 85.7 % was found on test data, which shows that a high percentage of hot leads are being captured by our model
B. With a precision score of 83.1 % , it shows that our model is returning a high a number of relevant results i.e. out of all predicted values, 83.1% are correct
C. This shows our model to be dependable at rejecting cold leads and identifying hot leads
D. AhighAUCvalueshowsthehighperformanceofourmodel.
