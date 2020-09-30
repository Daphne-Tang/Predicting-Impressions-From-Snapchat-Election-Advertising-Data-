# Predicting-Impressions-From-Snapchat-Election-Advertising-Data-

## Background
With the election season heating up, candidates are spending more money on political advertisements, especially on social media platforms that can reach younger voters. Snapchat's election advertising data would provide insights into what factors increase an advertisement's number of impressions. Specifically, this analysis would consider advertisement spending, size of the targeted age bracket, and the amount of days that the advertisement was displayed.

## Business Question
How does spending, size of the targeted age bracket, and the amount of days influence an advertisement's number of impressions? 

## Data Question - Open Data
The [Snap Political and Advocacy Ads Library](https://www.snap.com/en-US/political-ads/) provides open-source information on Snapchat advertisements that are political, issue-specific, or advocacy-related. This analysis uses Snapchat Election Advertising Data from 2020. 

Here is the original dataset: [Snapchat Election Advertising Data from 2020](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Original%20Datasets/PoliticalAds.csv)

For each advertisement, there is information on the impressions, spending, start and end dates, paying entities, age bracket, gender, and targeting criteria like location. Here is a more detailed description of different categories within the original dataset: [ReadMe](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Original%20Datasets/readme.txt)

## Data Question - Analysis
This analysis uses Microsoft Excel to answer the following questions: 
- How can we predict the number of impressions for an advertisement using the spending, size of the targeted age bracket, and the amount of days the advertisement was displayed? 

## Data Answer
This analysis conducted a multiple linear regression. The dependent variable was the number of impressions, and the independent variables were the spending, size of targeted age bracket, and number of days.

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Multiple%20Linear%20Regression%20Outcomes/Multiple%20Linear%20Regression%20.png)

The multiple linear regression yielded the following equation: 

Number of Impressions = 3669.276441 (Number of Days) + 5037.776313 (Age Range) + 446.2827378 (Spending) - 492491.6222

The R squared value was 0.708354638, which showed that the equation could explain approximately 71% of the data. All of the p-values for the three independent variables were less than 0.01, and the significance F value was 0. These values demonstrate that the results are statistically significant. As the advertisement's number of days, size of the targeted age range, and spending increases, the number of impressions rise as well. 

![alt text](https://github.com/Daphne-Tang/Predicting-Impressions-From-Snapchat-Election-Advertising-Data-/blob/master/Multiple%20Linear%20Regression%20Outcomes/Data%20-%20How%20Spending%20Impacts%20Number%20of%20Impressions.png)

This data visual shows that there is an approximately linear relationship between spending and the number of impressions. As spending increases, the amount of impressions does so as well. The R squared value of 0.7028 demonstrates that the linear equation captures around 70% of the data points. 

## Business Answer
