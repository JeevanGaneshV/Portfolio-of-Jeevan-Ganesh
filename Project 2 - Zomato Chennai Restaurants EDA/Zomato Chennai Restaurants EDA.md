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

**SQL Data Table Columns**

<img src="Images/SQL.png" style="display: block; margin-left: auto; margin-right: auto; width: 400px;height: auto;">


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

1. **Analysis of Chennai Locations with the Highest Number of Restaurants**
<img src="Images/Locations with the Highest Number of Restaurants in Chennai.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Porur, Velachery, Anna Nagar East, Ambattur, and T. Nagar having more than **100** restaurants each highlight them as popular dining spots in Chennai. This indicates a strong preference for dining out, likely due to the concentration of both residential areas and commercial activities in these locations.

2. **Top 10 Highly Rated Restaurant Locations in Chennai**
<img src="Images/Top 10 Locations in Chennai with Restaurants Rated 4 Stars or Above.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Anna Nagar East, Nungambakkam, and Adyar are popular dining areas in Chennai with over 15 highly rated restaurants each, catering to residents who appreciate good food and city life. (We applied filters to ensure that the data includes ratings from over 200 users for both delivery and dining experiences, ensuring reliability)

3. **Restaurants with the Highest Number of 4 Star Ratings or Above**
<img src="Images/Restaurants with the Highest Number of 4 Star Ratings or Above.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Domino's Pizza, Dindigul Thalappakatti, and Sangeetha Veg Restaurant are highly respected in Chennai because they have the most restaurant locations rated 4 stars or higher. Domino's Pizza is well-liked for its reliable service and widespread delivery options, which Chennai residents prefer for convenient pizza choices. Dindigul Thalappakatti is known for its authentic South Indian food, especially its famous biryanis, which are very popular among locals who enjoy rich, traditional dishes. Sangeetha Veg Restaurant is famous for its wide variety of vegetarian dishes and consistent quality, serving Chennai's large vegetarian population well. These restaurants not only have satisfied customers but also reflect Chennai's diverse culinary tastes, highlighting a commitment to high standards and genuine flavors in the city's dining scene. (We applied filters to ensure that the data includes ratings from over 200 users for both delivery and dining experiences, ensuring reliability)

4. **Top 10 Budget Friendly Locations in Chennai with Restaurants Rated 3.6 Stars or Above**
<img src="Images/Top 10 Budget Friendly Locations in Chennai with Restaurants.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Anna Nagar East, Adyar, and Nanganallur are popular in Chennai for affordable dining because they have a variety of restaurants that offer good food at reasonable prices. Anna Nagar East is a family friendly area, Adyar mixes homes with businesses. These areas are top choices for budget conscious diners looking for enjoyable meals without spending too much. (We applied filters to ensure that the data includes ratings from over 200 users for both delivery and dining experiences, ensuring reliability)

5. **Top 10 Affordable Restaurants in Chennai with Ratings of 3.6 Stars or Above**
<img src="Images/Top 10 Affordable Restaurants in Chennai.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- ID, Chai Kings, and The Kati Roll Shop are among Chennai's top 10 affordable restaurants where the food for two cost between Rs. 100 to 300. (We applied filters to ensure that the data includes ratings from over 200 users for both delivery and dining experiences, ensuring reliability)

6. **Areas in Chennai with the Expensive Restaurants**
<img src="Images/Areas in Chennai with the Highest Priced Restaurants.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">

- Nungambakkam, Alwarpet, and Adyar feature expensive restaurants in Chennai, indicating a preference for luxury dining. These areas likely have residents with higher incomes, including professionals and possibly celebrities, who value luxurious dining experiences. The presence of fancy restaurants reflects the demand for premium food and elegant atmospheres in these neighborhoods.

7. **Top 20 Restaurants with the Most Branches in Chennai**
<img src="Images/Most Branches in Chennai.png" style="display: block; margin-left: auto; margin-right: auto; width: 800px;height: auto;">





