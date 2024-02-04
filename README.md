# CAR_PORTFOLIO_PROJECT

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

1.Toyota brand has more mileage for each year of production


2.The price difference between the most expensive and cheapest car is 17000


3.There should be more production of cars in los angeles while dallas has the most profitable production


4.Hyundai brand car are way more profitable car


5.High production of white cars would be a plus and generate more money for the company


6.Hyundai has more coefficient variation of car brand


7.Production of honda and ford car in 2017 and 2018, Generate more sales in those stated year


8.2019 and 2017 has more production of cars in each year


9.Red color has more price above the average price for car


10.Toyota,chevrolet,Hyundai,Ford and Honda has the top five most expensive car brands


11.2019 has the highest sales of cars in each year


12.Hyundai palisade is the most expensive car in san francisco


13.Silver color has more car mileage in each year


14.Honda brand has most total mileage used in each year


15.Dallas generate the highest sales in each location




### Recommendations 
Based on my analysis, I recommend the following actions;

1.Production of Toyota car brand should be encouraged for each year


2.Expensive cars generate more money


3.Los Angeles production will increase more car sales, while dallas is more favourable


4.Hyundai brand are good car one could make alot of profit


5.White cars would be a plus and generate more money for the company


6.Toyota,Chevrolet,Hyundai,Ford and Honda should has high rate of production across each location



🚗
💻









    
