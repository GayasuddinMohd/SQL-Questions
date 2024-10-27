## [1.Tesla Models](https://www.analystbuilder.com/questions/tesla-models-soJdJ)

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

## [Heart Attack Risk](https://www.analystbuilder.com/questions/heart-attack-risk) <!-- Replace with the correct link if available -->


```sql
SELECT *
FROM patients
WHERE age > 50 AND cholesterol >= 240 AND weight >= 200
ORDER BY cholesterol DESC;
