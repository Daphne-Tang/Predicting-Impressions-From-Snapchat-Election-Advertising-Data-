# Step-By-Step Instructions
### Calculating Number of Days 
- Identify the columns "StartDate" and "EndDate." Insert to the right a column called "Number of Days"
- Enter the following formula: =IF(ISBLANK(EndDate)=FALSE,EndDate-StartDate,TODAY()-StartDate)
- This formula covers two scenarios: 
  -   If there is an EndDate, then the StartDate will be subtracted from the EndDate to get the number of days.
  -   If there is no EndDate, then the StartDate will be subtracted from today's date to get the number of days. 
  - Note: EndDate and StartDate refer to the cells with those values
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
### Multiple Linear Regression
### Creating Data Visuals
