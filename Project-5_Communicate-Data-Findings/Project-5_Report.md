# Ford GoBike System Data Exploration


## Dataset

The dataset includes information about individual rides made in a bike-sharing system covering the greaterSan Francisco Bay area.
It has 183,412 observatons with total 16 columns with numerical, categorical, time, and location data.

Data Wrangling Actions:
- Droped all records that has any missing value since we have a lot of data and percentage of missing is less than 5%.
- Converted time fields from object to datetime, id fields from int/float to object, birth_year from float to int.
- Corrected the birth_year value from 1878 to 1978.
- Changed column name of start_time and end_time to start_date_time and end_date_time.
- Seperated date_time columns to two columns.
- Created new fields: age, distance, day_diff and time_diff.

After wrangling and feature engineering, the cleaned dataset has 174,952 observatons with total 24 columns.

## Summary of Findings

During exploration, I have found that there are extreme values in both features of interest (duration and distance) initially from the histogram and then the boxplot which confirmed that. Since these outliers greatly skewed the data, I have used log-scaling on both to have a clear view of the distribution and they showed a normal distribution. It turned out that the most frequent duration is between 300 and 1,000 seconds with most frequent distance between 1,000 and 3,000 meters.

After that, I have investigated the other features and found that male users who are subscribers and don’t go with the bike share service constitute the majority of observations. What's more, customer user type have on average higher trip duration and distance than subscribers. I also looked at the age of users and found that most users are between 24 and 34.

Lastly, I examined the relationship of the numeric variables which are duration, distance, and age. Duration and distance and had to impute outliers in order to extract the relationship. They have a positive linear relationship with each other with correlation of 0.675 and no linear relationship at all with age. In addition, I noticed that time can play as a factor in determining the duration and distance for some categories such as user type and bike share as it introduces some spikes and pattern for the duration and distance features.

## Key Insights for Presentation

The focus will be on factors affecting trip duration and distance.

Starting by demonstrating the distribution of both features by plotting histogram and pointing out to the exreme values that are outliers
by plotting boxplot of each.

Then, I will move to the relationship between all numberic variables by plotting scatterplot matrix and heatmap to indicate the strength of the relationship (correlation factor).

Next, investigating the categorical variables effect on duration and distance using pair grid of boxplots.

Finally, I will show the effect on duration and distance over time by each categorical variables.