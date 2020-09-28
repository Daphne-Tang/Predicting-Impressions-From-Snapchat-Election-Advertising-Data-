# Step-By-Step Instructions
### Calculating Number of Days 
- Identify the columns "StartDate" and "EndDate." Insert to the right a column called "Number of Days"
- Enter the following formula: =IF(ISBLANK(EndDate)=FALSE,EndDate-StartDate,TODAY()-StartDate)
- This formula covers two scenarios: 
  -   If there is an EndDate, then the StartDate will be subtracted from the EndDate to get the number of days.
  -   If there is no EndDate, then the StartDate will be subtracted from today's date to get the number of days. 
  - Note: EndDate and StartDate refer to the cells with those values
  
![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Calcualte%20Number%20of%20Days.png)

### Removing Data Points With Zero or Negative Number of Days
- Several political ads have started and ended on the same day. Others have end dates that are earlier than their start dates, which results in a negative number of days. We want to eliminate these values from our analysis, so create a column next to "Number of Days" called "Negative or 0?"
- Enter the following formula: =IF(NumberOfDays>0,"No","Yes")
  - If the NumberOfDays is positive, then the formula will return "No"
  - If the NumberOfDays is zero or negative, then the formula will return "Yes"
  - Note: NumberOfDays refers to the cell containing that value
- For the "Negative or 0?" column, filter for "no" to only get the data points with positive number of days. 
### Calculating Range of Ages that the Ads Target
- Next to the "AgeBracket" column, insert 5 columns to the right
- Copy and paste the "AgeBracket" column into the "Start Age Version 1" column 
- Highlight the "Start Age Version 1" column and select "Text to Columns" under the "Data" tab
  - Select "Delimited" (click "Next")
  - Select "Other" and enter "+" (click "Next")
  - Select "General" (click "Finish")
  
![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Screen%20Shot%202020-09-28%20at%206.47.44%20PM.png)
- Highlight the "Start Age Version 1" column again and select "Text to Columns" under the "Data" tab
  - Select "Delimited" (click "Next")
  - Select "Other" and enter "-" (click "Next")
  - Select "General" (click "Finish")
  - Label the new column "End Age Version 1"
  
![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Screen%20Shot%202020-09-28%20at%206.49.31%20PM.png)

- Some political ads have age ranges that are "18+" or "17-." For age brackets with no upper limit, we are going to use 80. For age brackets with no lower limit, we are going to use 0. 
- Next to "End Age Version 1" column, insert 2 columns called "Start Age Version 2" and "End Age Version 2." 
- Copy the data from "Start Age Version 1" to "Star Age Version 2." Do the same for "End Age Version 1" and "End Age Version 2"
- Under "Start Age Version 2," filter for "blank." 
  - Enter the following formula: =IF(ISBLANK(StartAgeVersion1)=TRUE,"0",StartAgeVersion1)
  - This formula says that if the start age is blank, then use 0 for that value. Otherwise, use the existing start value
  - Apply this formula to all cells in "Start Age Version 2"
- Under "End Age Version 2," filter for "blank."
  - Enter the following formula: =IF(ISBLANK(EndAgeVersion1)=TRUE,"80",EndAgeVersion1)
  - This formula says that if the end age is blank, then use 80 for that value. Otherwise, use the existing end value
  - Apply this formula to all cells in "End Age Version 2"
- Under the "Age Range" column, enter the following formula: =EndAgeVersion2 - StartAgeVersion1

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Age%20Range.png)

### Multiple Linear Regression
- We will conduct a multiple linear regression to determine whether we can predict the number of impressions from the ad's number of days, spending, and age range targeted. 
- Create a new tab called "Relevant Columns from Data." Only copy and paste the following columns: ADID, Impressions, Number of Days, Age Range, and Spending. 
- We are going to test for multicollinearity. Under Data, select "Data Analysis" and "Correlation." Use the "Number of Days," "Age Range" and "Spending" columns as the input range, select "Labels in the First Row," and hit "Enter." 

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Multicollinearity.png)

- We will now do a multiple regression. Under "Data," select "Data Analysis" and "Regression." Select the y-range as the "Impressions" column and the x-range as the "Number of Days," "Age Range," and "Spending" columns. Select "labels" and "residuals" and create a new worksheet called "Multiple Linear Regression."
- Next to the "Residuals" column, we are going to check for outliers. Create a new column called "outliers" and enter the following formula:
=IF(ABS(Resdiauls)>2 * Standard Error,"Outlier","Not Outlier")
  - This formula says that if the absolute value of the residual is greater than 2 standard errors, then the data point is an outlier. 

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Multiple%20Linear%20Regression.png)
### Creating Data Visuals
- Create a new tab called "Data Visuals." We are going to create a scatterplot representing the relationship between spending and the number of impressions. Copy and paste the "ADID," "Spending," and "Impressions" columns from the original data set into the "Data Visuals" tab.
- Select both the "Impressions" and "Spending" columns. Select "Insert" and "Scatterplot." 
- Rename the graph's title as "How Spending Impacts Number of Impressions," the x-axis as the "Spending (USD)," and the y-axis as "Number of Impressions."
- Insert a trendline and add the equation as well as the R squared value. 

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Step-By-Step%20Instructions%20Screenshots/Data%20Visual.png)
