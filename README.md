# Retail-Sales-Prediction

## Aim of Project
- To find relation between different features and Weekly_Sales of different Stores of Walmart
- To build a Regression Model that can predict Weekly_Sales for a particular Store.
- To find out Impact of Hoildays on Sales.

## MetaData
**Data has 6435 records, having Sales Data from Feb 2010 to October 2012.**
- Store - the store number
- Date - the week of sales
- Weekly_Sales - sales for the given store
- Holiday_Flag - whether the week is a special holiday week.
- Temperature - Temperature on the day of sale
- Fuel_Price - Cost of fuel in the region
- CPI – Prevailing Consumer Price Index (Indicator of Inflation).
- Unemployment - Prevailing unemployment rate

## EDA
- Exploring the Data, we found that there was data for 45 stores and Weekly_Sales was from every Friday-to-Friday.
- Then heatmap was made to check for correlation between different variables.
- No significant correlation was found between any two variables, therefore multicollineartity will not be a problem.
- Then Oultiers were detected using IQR (Inter quartile range) method, and the Outliers were scaled down.
- New features such as "year" and "week_num" were extracted from the "Date" column.
- Only week_number 6, 36, 47, 52 were having Holiday_Flag = 1.

## Preprocessing Data and Model fitting
- Data was splitted into train-test data, with test data being 20% of total data.
- Coulmn transformer was used to preprocess data, where "Store" column was One-Hot Encoded, and other numerical columns were Standardized.
- Standardization is essential as many Linear Models use Gradient Descent, which Converges faster if all numerical columns are of Similar Scale.
- Linear Regression model was trained on training data, and then it was used to make predictions on test data.
- R2 score of 0.929 was obtained on test data.
- Cross validation was also done, where the mean R2 score came out to be 0.919.
- Root_mean_sqaured_error came out to be 1,53,029.

## Output Interpretations
- Unemployment and Temperature have negative coefficients, indicating negative correlation with Weekly_Sales.
- CPI has positive coefficient, one possible explaination might be increase in Sales means increase in demand, which may lead to high inflation.
- "year" has slight negative coefficient, but it seems to be insignificant.
- "week_num" and Holiday_Flag have positive coefficient, which means Sales have a increasing trend throughout a year, and average Sales during Holiday weeks is higher than Non holiday weeks.
- Fuel_Price has a slight positive coefficent, therefore it doesn't seems to have a significant relation with Sales.


- A function was made that takes the input and makes prediction of Sales in that Week.
- Finally different graphs were made to get answers on Which Store has Max Sales ?, Which Holidays had greater impact on Sales ?.
