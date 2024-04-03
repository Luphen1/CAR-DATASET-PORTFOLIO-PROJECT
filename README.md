
🚗# CAR_PORTFOLIO_PROJECT

#### Table Of Contents
------------

-  [Project Overviews](#Project_Overview)

-  [Data Sources](#Data_Sources)

-  [Tools](#Tools)

-  [Data Cleaning/Preparation](#Data_cleaning/Preparation) 

-  [Exploration Data Analysis](#Recommendation)

-  [Data Analysis](#Data_Analysis)

-  [Results/Findings](#Results/Finding)

-  [Recommendations](#Recommendations)


### Project Overview
The data project aims to provide an insights about the performances of cars over the past few years. By analyzing various aspects of the car dataset, I was able to make data-driven recommendation and gaining proficient understanding for each car performances.

![Car Dashboard Report](https://github.com/Luphen1/CAR-DATASET-PORTFOLIO-PROJECT/assets/140397207/4a472ab1-3faa-4824-9cef-938fe13816cd)



### Data Sources
Car Data:The primary database used for this analysis is the "car_data.cvs" file from kaggle, Containing detailed information about each Car_Id,brand,model,year,color,mileage,price and location

### Tools 
- Excel - Data cleaning to check if there are missing values and duplicate records  [Download Here      https://www.kaggle.com/datasets](https)
- MYSQL - Data Analysis
- Power BI - Creating Reports

### Data Cleaning/Preparation
In the initial data preparation, i performed the following task;
1. Data loading and inspection
2. Handling for missing values
3. Checking for duplicate values
4. Convert each headers to the right data type
5. Outlier Detection and Handling
6. Handling Inconsistent Data and Typos

### Exploration Data Analysis
EDA involved exploring the car data to answer key questions such as;

1.Find the total mileage of cars by color?

2.Which car brand has the top five average price?

3.How many cars of each brand are manufacture in each year?

4.What is the most common car color in the database?

5.How many cars were manufactured in each year?

6.Fetch brand with the total mileage in each year?

7.What is the total price of cars sold in each year?

8.How many cars of each color have a price above the average price of all cars?

9.What is the top five expensive cars in each location?

10.Fecth brand and average mileage per year?

11.What is the total price of cars sold in each location?

12.What car brand has price to mileage ratio?

13.Calculate the coefficient of variation of a car prices for each brands.

14.What is the price difference between the cheapest and the most expensive cars

15.What is the average price and mileage of cars in each location?

16.What is the car brand and model price that are above average?

### Data Analysis
Include some interesting code/features worked with
```
SELECT color,SUM(mileage) AS total_mileage
FROM cars
GROUP BY color
ORDER BY total_mileage DESC;
```

```
SELECT brand,ROUND(AVG(price),2) AS avg_price
FROM cars
GROUP BY brand
ORDER BY avg_price DESC
LIMIT 5;
```

```
SELECT brand,year,COUNT(*) AS num_of_brand
FROM cars
GROUP BY year,brand
ORDER BY num_of_brand DESC;
```


 ```
 SELECT
    color,
    COUNT(*) AS color_count,
    DENSE_RANK() OVER (ORDER BY COUNT(*) DESC) AS color_rank
  FROM cars
  GROUP BY color;
```
 
```
SELECT year,count(*) AS num_of_cars
FROM cars
GROUP BY year;
```

```
 SELECT year,brand,sum(mileage) AS sum_mileage
FROM cars
GROUP BY year,brand;
```

```
SELECT year, SUM(price) AS total_price_car
FROM cars
GROUP BY year
ORDER BY total_price_car DESC;
```

```
SELECT color,COUNT(*) AS num_of_car
 FROM 
 cars WHERE price > (SELECT AVG(price) FROM cars) 
 GROUP BY color;
```
 
```
 SELECT location,brand,model,MAX(price) AS exp_car
 FROM cars
 GROUP BY location,brand,model
 ORDER BY exp_car DESC
 LIMIT 5;
```
 
```
 SELECT year,brand,ROUND(AVG(mileage),2) AS avg_mileage
FROM cars
GROUP BY brand,year
ORDER BY  avg_mileage DESC;
```
 
```
 SELECT location,SUM(price) AS total_sold_car
FROM cars
GROUP BY location
ORDER BY total_sold_car DESC;
```

```
 SELECT brand,ROUND(MAX(price/mileage),2) AS price_mileage_ratio
FROM cars
GROUP BY brand
ORDER BY price_mileage_ratio DESC;
```

```
SELECT brand, ROUND(stddev(price)/AVG(price),2) coefficient_of_variation 
FROM cars
GROUP BY brand;
```

```
SELECT MAX(price) - MIN(price) AS pricedifference
FROM cars;
```

```
SELECT location,ROUND(AVG(Price),2) AS avg_price,ROUND(AVG(Mileage),2) AS avg_mileage
FROM cars
GROUP BY location
ORDER BY avg_price DESC,avg_mileage DESC;
```

```
SELECT brand,model,price
FROM cars
WHERE price > (SELECT AVG(price) AS avg_price FROM cars);
```

### Results/Findings

The analysis results are summarized as follows:

1. Toyota brand has higher mileage for each year of production.
   
2. The price difference between the most expensive and cheapest car is $17,000.
	
3. There should be more production of cars in Los Angeles, while Dallas has the most profitable production.
   
4. Hyundai brand cars are significantly more profitable.
   
5. High production of white cars would be advantageous and generate more revenue for the company.
	
6. Hyundai has a higher coefficient of variation among car brands.
   
7. Production of Honda and Ford cars in 2017 and 2018 generated more sales in those years.

8. Each of the years 2019 and 2017 individually had more car production compared to other years,
   The combined production of cars in 2019 and 2017 was higher than the combined production of cars in other years.

9. Cars in red color tended to have prices above the average price for a car.

10. The top five most expensive car brands were Toyota, Chevrolet, Hyundai, Ford, and Honda.

11. The year 2019 had the highest sales of cars compared to other years.

12. The Hyundai Palisade was identified as the most expensive car in San Francisco.

13. Cars in silver color had higher mileage in each year.

14. The Honda brand had the most total mileage used in each year.

15. Dallas consistently generated the highest sales in each location




### Recommendations 
Based on my analysis, I recommend the following actions:

1. Encourage the production of Toyota car brand for each year.
	
2. Focus on producing more expensive cars as they generate higher revenue.
   
3. Increase production in Los Angeles to boost car sales, while maintaining a favorable production level in Dallas.
   
4. Emphasize Hyundai brand cars as they are profitable products to generate revenue.
	
5. Prioritize the production of white cars, as they have the potential to generate more revenue for the company.
    
6. Implement a strategy to increase production rates of Toyota, Chevrolet, Hyundai, Ford, and Honda across all locations







🚗
💻









    

💻









    
