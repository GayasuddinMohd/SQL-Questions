**1. Tesla Models**

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

**2. Heart Attack Risk**

SELECT *
FROM patients
WHERE age > 50 AND cholesterol >= 240 AND weight >= 200
ORDER BY cholesterol DESC;

