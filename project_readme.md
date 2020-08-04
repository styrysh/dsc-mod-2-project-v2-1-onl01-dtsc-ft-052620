
# Module 2 Final Project Readme

We are looking at variables that affect the housing prices in King County, Washington

Our objective is to determine which qualities of the houses affect their prices the most to provide the property investors a better idea of what criteria to screen for when looking at potential targets.

We are using kc_house_data.csv as our dataset containing property characteristics including prices

## Data manipulation

Cleaning

We identified and replaced the NaN values in the 'view' and 'yr_renovated' columns with median values for these respective columns. Median values were used since we determined that the exact values didn't matter as much as whether the house has been viewed or renovated. We replaced the missing values in the 'waterfront' column with 0s. The date column was dropped as well since it was in the format not supported by the model, and given we didn't use it as one of the independent variables, it made sense to drop instead of converting to float values.

Manipulation

'been_viewed' and 'has_renovation' are the columns containing dummy variables based on the columns 'view' and 'yr_renovated'. Since we are interested primarily in whether the house has been viewed or renovated, dummy variables provide a concise way to indicate that.

## EDA

We plotted price against each independent variable in separate scatterplots to determine which variables had a noticeable effect or a linear relationship with price.

The values of 'id', 'yr_built', 'sqft_basement' and 'date' columns didn't seem to have a clear relationship with price.
House prices increased as the number of bedrooms increased with the peak prices belonging to homes with 5 and 6 bedrooms. House prices decreased as the number of bedrooms increased after that.
As the values of 'bathrooms', 'condition', 'grade', 'sqft_above' and 'sqft_living' increased the house prices increased. The relationship was linear for 'sqft_living' and almost linear for 'bathrooms'
House prices for 'sqft_lot' were the highest for smaller values (<250,000). House prices for houses with sqft_lot values > 250,000 didn't seem to have a clear relationship with 'sqft_lot' values.
Houses with 2 floors had the highest peak prices and houses with 3 or more floors had the lowest values on average.
Having a waterfront didn't particularly affect the price of a house.
The value of 'view' column didn't have much effect on house prices (i.e 1, 2, or 3 views didn't differ much in price). There was however a difference between houses that have been viewed at least once vs never been viewed.
As 'lat' values increased house prices increased, as 'long' values increased house prices decreased.

## Questions

What characteristics of the house have the biggest impact on price?
House size as indicated by 'sqft_living' and 'bathrooms' seem to have the largest impact
Renovated homes and those that have been viewed are usually more expensive than those that haven't, given similar characteristics.

## Recommendation
Focus on homes that have not been viewed or renovated to increase price through renovation and advertising. Filter houses by size ('bathrooms' and 'sqft_living') to find ones that fit your budget.

## Modeling
The initial model was fairly rough and had an R-squared value of 0.705, which means that only 70.5 percent of residual errors were explained. Further, 'sqft_living' and 'sqft_above' were reduntant when used together and hence only 'sqft_living' was used in the final iteration.

The final model had an improvement in the R-squared value and increased from 0.705 to 0.725. With that said, there is still room for improvement. 'sqft_living','bathrooms', 'has_renovation', 'been_viewed' were used as independent variables. Columns 'has_renovation' and 'been_viewed' are dummy variables based on columns 'view' and 'yr_renovated'. The RMSE value of 213464 is too high, and the model should be adjusted in the future.

## Conclusion and future work
The final model needs improvement, R-squared is too low and RMSE is too high. In the future, I would like to experiment with subdiving houses according to latitude and longitude to provide more targeted predicitions for a specific location, trying out various transformations and testing out several more models with slightly different independent variables.


