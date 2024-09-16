# Examples of requests using data Grouping and the Aggregations

**- ``` GROUP BY ```**
```
SELECT rating,
       AVG(rental_rate)
FROM film
GROUP BY rating
```


**- ``` MIN(), MAX(), AVG() ```**
```
SELECT 
MIN(rental_duration)AS min_rental_duration,
MAX(rental_duration)AS max_rental_duration,
AVG(rental_duration)AS Average_rental_duration 
FROM film
```

**- ``` MODE() WITHIN GROUP (ORDER BY ) ```**
```
SELECT 
MODE() WITHIN GROUP (ORDER BY special_features)
AS mode_from_special_features,

MODE() WITHIN GROUP (ORDER BY rating)
AS mode_from_ratings
FROM film;
```
