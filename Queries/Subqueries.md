# Example of a joined subquery

**- Where are customers with a high lifetime value based?**

```
SELECT
  B.customer_id,
  E.country,
  D.city,
  SUM(A.amount) AS total_amount_paid
FROM payment A
INNER JOIN customer B ON A.customer_id = B.customer_id
INNER JOIN address C ON B.address_id = C.address_id
INNER JOIN city D ON C.city_id = D.city_id
INNER JOIN country E ON D.country_id = E.country_id
WHERE D.city IN (
  SELECT D.city
  FROM customer B
  JOIN address C ON B.address_id = C.address_id
  JOIN city D ON C.city_id = D.city_id
  JOIN country E ON D.country_id = E.country_id
  WHERE E.country IN (
    SELECT E.country
    FROM customer B
    JOIN address C ON B.address_id = C.address_id
    JOIN city D ON C.city_id = D.city_id
    JOIN country E ON D.country_id = E.country_id
    GROUP BY E.country
    ORDER BY COUNT(B.customer_id) DESC
    LIMIT 10
  )
  GROUP BY E.country, D.city
  ORDER BY COUNT(B.customer_id) DESC
  LIMIT 10
)
GROUP BY B.customer_id, E.country, D.city
ORDER BY SUM(A.amount) DESC
```
