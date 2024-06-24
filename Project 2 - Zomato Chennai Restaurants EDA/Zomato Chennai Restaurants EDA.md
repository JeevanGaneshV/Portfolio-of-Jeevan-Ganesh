# Project 2 - Zomato Chennai Restaurants EDA

## Project Overview:

This data analysis project explores the dining preferences and trends of Chennai residents using data from Zomato, a popular food delivery app that also offers detailed information about restaurants, including menus, reviews, and ratings. The goal is to identify patterns in Chennai's food scene by looking at aspects like prices, cuisine types, top-selling dishes, and user ratings.

The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/phiitm/chennai-zomato-restaurants-data/data), includes vital information such as the cost for two people, the types of cuisines each restaurant offers, top-selling dishes, Zomato ratings, and the number of users that contribute to those ratings. For this project we are only looking at restaurants that provide both dining and delivery options.

This project can provide several valuable insights:
- Analyzing price distribution across different areas can infer the economic status of various neighborhoods and understand the affordability of dining options.
- Identifying the popularity of different cuisines in various parts of Chennai can highlight cultural influences and preferences.
- Examining the correlation between ratings, votes, and prices can offer insights into what makes a restaurant successful in Chennai.
- By linking dining trends with areas undergoing urban changes, we can understand the impact of these changes on the local food culture.

## Data Exploration and Cleaning

**INSERT SQL_DATA_TABLE**

- Checking for any duplicate rows by using address as primary key.
 ```sql
SELECT 
	address, 
	COUNT(*) AS count
FROM world.zomato
GROUP BY
	address
HAVING count>1;
```

- Removing unused columns such as zomato_url
 ```sql
ALTER TABLE world.zomato
DROP COLUMN zomato_url;
```


- Formatting strings to remove brackets from cuisine, top_dishes and features
```sql
UPDATE world.zomato
SET cuisine = REPLACE(REPLACE(REPLACE(cuisine, '[', ''), ']', ''), ', ', ', ')
WHERE address IS NOT NULL;
```
```sql
UPDATE world.zomato
SET top_dishes = REPLACE(REPLACE(REPLACE(top_dishes, '[', ''), ']', ''), ', ', ', ')
WHERE address IS NOT NULL;
```
```sql
UPDATE world.zomato
SET features = REPLACE(REPLACE(REPLACE(features, '[', ''), ']', ''), ', ', ', ')
WHERE address IS NOT NULL;
```

- Exporting the cleaned dataset
```sql
SELECT * 
FROM world.zomato
INTO OUTFILE 'C:/ProgramData/MySQL/MySQL Server 8.0/Uploads/cleaned_zomato_dataset.csv'     
FIELDS TERMINATED BY ','    
OPTIONALLY ENCLOSED BY '"'    
LINES TERMINATED BY '\r\n';  
```

## Data Analysis

**Observations are made in bullet points**

1. 
