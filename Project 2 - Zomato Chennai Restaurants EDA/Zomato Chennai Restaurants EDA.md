# Project 2 - Zomato Chennai Restaurants EDA

## Project Overview:

This data analysis project explores the dining preferences and trends of Chennai residents using data from Zomato, a popular food delivery app that also offers detailed information about restaurants, including menus, reviews, and ratings. The goal is to identify patterns in Chennai's food scene by looking at aspects like prices, cuisine types, top-selling dishes, and user ratings.

The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/phiitm/chennai-zomato-restaurants-data/data), includes vital information such as the cost for two people, the types of cuisines each restaurant offers, top-selling dishes, Zomato ratings, and the number of users that contribute to those ratings. 

This project can provide several valuable insights:
- Analyzing price distribution across different areas can infer the economic status of various neighborhoods and understand the affordability of dining options.
- Identifying the popularity of different cuisines in various parts of Chennai can highlight cultural influences and preferences.
- Examining the correlation between ratings, votes, and prices can offer insights into what makes a restaurant successful in Chennai.
- By linking dining trends with areas undergoing urban changes, we can understand the impact of these changes on the local food culture.

## Data Exploration and Cleaning

**INSERT SQL_DATA_TABLE**

- Checking for any duplicate rows by using restaurant_name as primary key.
 ```sql
SELECT 
	restaurant_name, 
	COUNT(*) AS count
FROM world.zomato_chennai
GROUP BY
	restaurant_name
HAVING count>1;
```

- Removing unused columns such as zomato_url and address
 ```sql
ALTER TABLE world.zomato_chennai
DROP COLUMN zomato_url;
```

```sql
ALTER TABLE world.zomato_chennai
DROP COLUMN address;
```

- Formatting strings to remove brackets from cuisine, top_dishes and features
```sql
UPDATE world.zomato_chennai
SET cuisine = REPLACE(REPLACE(REPLACE(cuisine, '[', ''), ']', ''), ', ', ', ')
WHERE restaurant_name IS NOT NULL;
```
```sql
UPDATE world.zomato_chennai
SET top_dishes = REPLACE(REPLACE(REPLACE(top_dishes, '[', ''), ']', ''), ', ', ', ')
WHERE restaurant_name IS NOT NULL;
```
```sql
UPDATE world.zomato_chennai
SET features = REPLACE(REPLACE(REPLACE(features, '[', ''), ']', ''), ', ', ', ')
WHERE restaurant_name IS NOT NULL;
```


