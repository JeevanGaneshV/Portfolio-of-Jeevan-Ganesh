# **Project 1 - Analyzing Bellabeat's Smart Device Fitness Data to Enhance their Marketing Strategy (Report)**

## Content
  1. [Scenario](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/blob/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#scenario)
  2. [Business Tasks](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#business-tasks)
  3. [Data Exploration and Data Cleaning](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#business-tasks)
  4. [Data Analysis](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#data-analysis)

      4.1. [Weekday Analysis: Active Hours, Steps, and Calories](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#1-weekday-analysis-active-hours-steps-and-calories)

     4.2. [Understanding How Activity Levels Impact Calories Burned](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#2-understanding-how-activity-levels-impact-calories-burned)
     
     4.3. [Relationship between Physical Activity and Weight](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#3-relationship-between-physical-activity-and-weight)
     
     4.4. [Distribution of total very active minutes, sedentary hours and time spent asleep](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#4-distribution-of-total-very-active-minutes-sedentary-hours-and-time-spent-asleep)
     
     4.5. [Distribution of Users' BMI](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#5-distribution-of-users-bmi)
     
     4.6. [Average of active minutes, steps, sedentary hours and time asleep](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#6-average-of-active-minutes-steps-sedentary-hours-and-time-asleep)
5. [Actions and Recommendations](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#actions-and-recommendations)
6. [Appendix](https://github.com/JeevanGaneshV/Portfolio-of-Jeevan-Ganesh/edit/main/Project%201%20-%20%20Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy/Analyzing%20Smart%20Device%20Fitness%20Data%20to%20Enhance%20Bellabeat's%20Marketing%20Strategy.md#entire-code-of-r)
     
## **Scenario**
Bellabeat, a company known for its stylish health-focused smart devices, offering insights into activity, sleep, stress, and reproductive health. I am tasked with analyzing smart device fitness data to uncover insights that will enhance product strategies. My goal is to explore how consumers interact with smart devices and apply these findings to refine Bellabeat's product offerings and marketing approaches.

## **Business Tasks**
1. Investigate trends in how consumers use Bellabeat smart devices for fitness tracking.
2. Identify how these usage trends can be applied to the Bellabeat app.
3. Use the insights gained to recommend strategic enhancements in Bellabeat's marketing efforts, aligning them with consumer behavior and preferences observed in the data.

#### Data sourced from “FitBit Fitness Tracker Data.” Kaggle, 2 Mar. 2024, www.kaggle.com/datasets/arashnic/fitbit.

## **Data Exploration and Cleaning**
Ignored the irrelevant or not so useful data from the data source and uploaded useful data file for data cleaning.

Data files used are:
- weightLogInfo_merged.csv
- sleepDay_merged.csv
- dailyActivity_merged.csv

##### **weightLogInfo_merged data cleaning**
1. Deleted duplicate rows and changed the data types of column 'date' from chr to POSIXct
2. Cleaned column names
3. Changed the data type of column 'is_manual_report' from chr to logi
##### **sleepDay_merged data cleaning**
1. Deleted duplicate rows and changed the data types of column 'sleep_date' from chr to POSIXct
2. Cleaned column names

##### **dailyActivity_merged data cleaning**
1. Deleted duplicate rows and changed the data types of column 'activity_date' from chr to Date
2. Cleaned column names
3. Deleted rows that has 0 total calories burned and 0 total active hours as it could be due to people not wearing the smart device at that time - 83 rows got deleted

##### **weightLogInfo_merged data manipulation**
1. Deleted the 'fat' column in the table as it provides no information
2. Added column 'status' in the table showing their weight status based on their BMI 

##### **sleepDay_merged data manipulation**
1. Converting total minutes asleep and total minutes in bed to hour and finding the time it takes to fall asleep

##### **dailyActivity_merged data manipulation**
1. Converted sedentary minutes to hours and calculated total amount of active hours
2. Added a column to specify the weekday

# **Data Analysis**

## **4.1. Weekday Analysis: Active Hours, Steps, and Calories**
These visualizations aggregate data collected over the course of a month, **grouped by individual days**. The goal is to analyze user activity patterns and identify days when users are most active. By examining metrics such as total active hours, steps taken, and calories burned.

<img src="Images/Total Very Active Minutes Logged in a Month.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

                                                                                                                           
<img src="Images/Step Count Overview for a Month.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

                                                                                                                           
<img src="Images/Calories burned in a month.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

#### **Observations**
- The data indicates a notable increase in physical activity starting from Sunday, followed by a gradual decline. 
- This trend suggests that motivation levels tend to be higher on weekends, resulting in increased engagement in physical activities.
- Weekdays may lack the motivation or available time for engaging in physical activities.
- The data on calories burned remains steady throughout the week, with a slight increase noted during weekends. This could be because calories continue to be burned even during sedentary periods.

## **4.2. Understanding How Activity Levels Impact Calories Burned**
The goal is to analyze how much correlation is there between the total active hours, steps taken and calories burned.
<img src="Images/Impact of Total Active Hours on Calories Burned.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

                                                                                                                           
<img src="Images/Impact of Total Steps on Calories Burned.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

#### **Observations**
- Here, we see a clear positive trend in the two charts, showing that more time spent in physical activity or walking more steps is associated with higher calorie burn.
- After reaching 32K steps, the trend shows a decline.


## **4.3. Relationship between Physical Activity and Weight**
The goal is to analyze how individuals with varying weights engage in physical activity.
<img src="Images/Correlation of Physical Activity Levels with Weight.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">


#### **Observations**
- We observed that users weighing between 85 kg and 95 kg are the most active users, with a decrease in the number of active users beyond 95 kg.


## **4.4. Distribution of total very active minutes, sedentary hours and time spent asleep**
The goal is to analyze the distribution of active minutes, sedentary hours and time asleep among the users.

<img src="Images/Time spent on rigorous activity distribution.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Most users engage in minimal exercise, the graph shows that only a few users, hardly 95 people exercising for 10-19 minutes.

<img src="Images/Distribution of Sedentary Hours.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Most users spend extended time being sedentary, between 10-13 hours or 17-21 hours.

<img src="Images/Distribution of Total Asleep Hours.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Many users sleep for around 5 to 6.5 hours, which is considered insufficient, while most users get a sufficient amount of sleep, around 7 hours.


## **4.5. Distribution of Users' BMI**
The goal is to see how many users are actually healthy and how many are overweight or underweight based on their BMI. Only 8 people have provided information on their weight.

<img src="Images/BMI Distribution.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

#### **Observations**
- Out of 8 users, 3 are healthy and 5 are overweight, could not find the BMI of other users as I think weight was an optional field to fill.

## **4.6. Average of active minutes, steps, sedentary hours and time asleep**
The goal is to calculate the averages of active minutes, steps, sedentary hours, and time asleep in order to compare them with the recommended amounts.

#### **Observations**
- The average active minutes per day is **23.2 minutes**, which is below the recommended **30 minutes** (according to [source](www.mayoclinic.org/healthy-lifestyle/fitness/expert-answers/exercise/faq-20057916#:~:text=As%20a%20general%20goal%2C%20aim,sitting%20time%20is%20important%2C%20too)). Only **30%** of users are above this average.
- The average number of steps taken per day is about **8,300 steps**, which falls within the recommended range of **5,000 to 8,000 steps**. However, **21%** of users don't reach the minimum of **5,000 steps**.
- The average sedentary time is **15.87 hours** per day, which is much higher than the recommended **6 to 8 hours**.
- The average amount of sleep is **6.98 hours** per night, but about **54%** of users get less than **7 hours** of sleep.

# Actions and Recommendations

1. **Investigate trends in how consumers use Bellabeat smart devices for fitness tracking.**

   From the analysis, we observed several key trends in how consumers use Bellabeat smart devices:
   - Users tend to be more active on weekends, with a noticeable increase in total active hours and steps taken starting from Sunday, followed by a gradual decline throughout the week. This suggests higher motivation levels on weekends due to more available time.
   
   - Users within the 85 kg to 95 kg weight range are the most active, with activity levels decreasing beyond this range.
     
   - Users exhibit high levels of sedentary behavior, averaging 15.87 hours per day, significantly higher than the recommended 6 to 8 hours.
     
   - The average sleep duration is 6.98 hours per night, with 54% of users sleeping less than the recommended 7 hours.

3. **Identify how these usage trends can be applied to the Bellabeat app.**
   
    - Develop personalized activity plans and reminders in the Bellabeat app that motivate users to increase their activity levels on weekdays, addressing the drop in physical activity during this period.
      
    - Introduce weekend challenges or rewards in the app to capitalize on the higher motivation levels during weekends.
      
    - Implement sedentary alerts in app to encourage users to move more frequently and reduce sedentary hours.
      
    - Offer sleep improvement programs and features in the Bellabeat app, providing tips and reminders to help users achieve the recommended 7 hours of sleep.
      
    - Integrate weight management tools in the app that provide tailored activity recommendations for users based on their weight (making weight a mandatory field to be entered), encouraging those in higher weight ranges to increase their activity levels.
      
4. **Use the insights gained to recommend strategic enhancements in Bellabeat's marketing efforts, aligning them with consumer behavior and preferences observed in the data.**
   
    - Launch targeted marketing campaigns that emphasize the importance of staying active during weekdays and highlight the features of Bellabeat devices that support this goal.
      
    - Showcase testimonials and success stories of users who have improved their activity levels and overall wellness using Bellabeat products, particularly those who were able to increase their weekday activity and reduce sedentary time.
      
    - Create and share educational content on social media that explain the benefits of regular physical activity, proper sleep, and reduced sedentary behavior, and how Bellabeat products can assist in achieving these goals.
      
    - Introduce promotional offers and discounts on Bellabeat devices during weekends to use the higher motivation levels and encourage new users to start their wellness journey.


# Appendix
## Entire Code of R


```r
# Installing The Packages
install.packages('lubridate') #To convert from character to date format, functions: as.DATE()
install.packages('skimr') #To provide the statistics of the data, functions: skim()
install.packages('tidyverse') #To use read.csv()
install.packages('janitor') #To check spaces between characters clean_names()
install.packages('ggplot2')

# Loading The Packages
library(lubridate)
library(skimr)
library(tidyverse)
library(janitor)


## Data Exploration and Data Cleaning ##


# Reading the data and naming them into new dataframes
weight <- read.csv("weightLogInfo_merged.csv")
daily_sleep <- read.csv("sleepDay_merged.csv")
daily_activity <- read.csv("dailyActivity_merged.csv")


# To make the columns 
weight <- clean_names(weight)
daily_sleep <- clean_names(daily_sleep)
daily_activity <- clean_names(daily_activity)

# Check for duplicate values and delete it
weight <- unique(weight)
daily_sleep <- unique(daily_sleep)
daily_activity <- unique(daily_activity)
  

# To inspect and format the data types
str(weight)
str(daily_sleep)
str(daily_activity)

skim(weight)
skim(daily_sleep)
skim(daily_activity)


# Converting to appropriate data types
input_formats <- c("%m-%d-%Y %H:%M", "%m/%d/%Y %I:%M:%S %p")
weight$date <- parse_date_time(weight$date, orders = input_formats)
weight$is_manual_report <- as.logical(weight$is_manual_report)

daily_sleep$sleep_day <- parse_date_time(daily_sleep$sleep_day, orders = input_formats)

daily_activity$activity_date <- as.Date(daily_activity$activity_date, format = "%m/%d/%Y")



# Converting Sedentary minutes to hours and calculating Total active hours
daily_activity <- daily_activity %>%
  mutate(sedentary_hours = sedentary_minutes / 60)

daily_activity <- daily_activity %>%
  mutate(total_active_hours = (very_active_minutes + fairly_active_minutes + lightly_active_minutes ) / 60)

# Adding the day of the week to daily activity data
daily_activity <- daily_activity %>%
  mutate(day_of_week = weekdays(activity_date))



# Converting asleep minutes and total in bed minutes to hours 
# calculating the time it takes to fall asleep
daily_sleep <- daily_sleep %>%
  mutate(
    total_asleep_hours = round(total_minutes_asleep / 60, 2),
    total_bed_hours = round(total_time_in_bed / 60, 2),
    time_to_fall_asleep = total_time_in_bed - total_minutes_asleep
  )



# Deleting the fat column in weight
weight <- select(weight,-fat)


# Classifying their weight based on BMI
weight <- weight %>%
  mutate(status = case_when(
    bmi < 18.5 ~ "Underweight",
    bmi >= 18.5 & bmi < 24.9 ~ "Healthy",
    bmi >= 24.9 ~ "Overweight"
  ))


## Outliers
cleaned_daily_activity <- daily_activity %>%
  filter(calories > 0, total_active_hours > 0.00)


# Output and write the csv for visualization in Tableau
write.csv(cleaned_daily_activity, file ='bellabeat_daily_activity.csv')
write.csv(daily_sleep, file = 'bellabeat_sleep.csv')
write.csv(weight, file = 'bellabeat_weight.csv')

```


