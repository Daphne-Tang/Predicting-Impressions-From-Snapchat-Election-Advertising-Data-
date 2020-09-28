# Step-By-Step Instructions
### Calculating Number of Days 
1. Identify the columns "StartDate" and "EndDate"
1. Insert to the right a column called "Number of Days"
1. Enter the following formula: =IF(ISBLANK(EndDate)=FALSE,EndDate-StartDate,TODAY()-StartDate)
- This formula covers two scenarios: 
  -   If there is an EndDate, then the StartDate will be subtracted from the EndDate to get the number of days.
  -   If there is no EndDate, then the StartDate will be subtracted from today's date to get the number of days. 
- Note: EndDate and StartDate refer to the cells with those values

### Calculating Range of Ages that the Ads Target
### Multiple Linear Regression
### Creating Data Visuals
