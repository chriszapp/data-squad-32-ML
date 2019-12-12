Data Cleaning
- First check the shape to understand how much data we're dealing with.
- Check nulls and remove any columns with higher than 10% values missing since these most likely do not influence the price as much and would be hard for us to infer.
- Investigating columns with nulls < 10% we see some fall into the same categories with equal missing rows - basement and garage.
- Can assume these are houses with no basement or garage, so replace nulls.
- Now there's under 10 rows that are NA so going to go ahead and drop those.

Categorical Variables
- Given machine learning algorithms tend to deal with numeric values, we need to investigate this.
- Over half of our columns are categorical.
- Ideally we would investigate each categorical variable and convert to numeric - however given the unique values of each of these, this would take time to understand the meaning of each.
- Given the time constraint, we will just look at numeric columns for this model.

Colinearity
- Looking at the heatmap to determine what features to keep in the model.
- Keeping OverallQual  GarageArea, 1stFlrSF, YearBuilt, TotRmsAbvGrd based on high correlation with the target variable
- Not including GarageCars, GrLivArea since they have high colinearity with one of the other features selected even though they have high correlation with the target

Distribution
- Checking the distribtion of the selected features to ensure they are close to normally distributed.
- Housing & SalePrice is left skewed, so transforming it to a log function.

Model
- Initially used a linear regression based on the features selected from the heatmap.
- Second tried to use RFE to select features, but these resulted in lower R2 and higher RMSE.

Model Improvements
- Increase train sample size to 85%
- Used pipeline
- RMSE reduced

Further Improvements
- Investigate categorical variables further
