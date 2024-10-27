## [Tesla Models](https://www.analystbuilder.com/questions/tesla-models-soJdJ)

**Query:**

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
