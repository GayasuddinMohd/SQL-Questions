# SQL Questions

## Problem: Tesla Models

[View Question on AnalystBuilder](https://www.analystbuilder.com/questions/tesla-models-soJdJ)

### Objective
Find the Tesla model with the highest profit, calculated as `(car_price - production_cost) * cars_sold`.

### Solution

```sql
SELECT *
FROM (
    SELECT 
        tesla_model,
        car_price,
        cars_sold,
        production_cost,
        (car_price - production_cost) * cars_sold AS profit
    FROM 
        tesla_models
) AS model_profits
WHERE 
    profit = (SELECT MAX((car_price - production_cost) * cars_sold) FROM tesla_models);
