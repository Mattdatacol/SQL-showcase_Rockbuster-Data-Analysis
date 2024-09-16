# Example of a common table expression (CTE)

**- Average number of film rentals by customer and by country in a year**

```
WITH rentals_by_customer_and_country_cte (customer_id, country, nb_rentals_by_customer) AS
	(SELECT 	A.customer_id,
		E.country,
		COUNT(DISTINCT A.payment_id) AS nb_rentals_by_customer

FROM payment A

	INNER JOIN customer B ON A.customer_id = B.customer_id
	INNER JOIN address C ON B.address_id = C.address_id
	INNER JOIN city D ON C.city_id = D.city_id
	INNER JOIN country E ON D.country_id = E.country_id


GROUP BY A.customer_id, E.country_id
ORDER BY nb_rentals_by_customer DESC)

SELECT 	country,
		COUNT(DISTINCT customer_id),
		AVG (nb_rentals_by_customer) AS avg_rentals_by_customer
FROM rentals_by_customer_and_country_cte

GROUP BY country
ORDER BY avg_rentals_by_customer DESC
```
