# Examples of joining tables

**- Top 10 countries for Rockbuster in terms of customer numbers**

```
SELECT
  D.country AS country,
  COUNT(A.customer_id) AS number_of_customers

FROM Customer A
  INNER JOIN address B ON A. adress_ID = B.address_id
  INNER JOIN city C ON B.city_id = C.city_id
  INNER JOIN country D ON C.country_id = D.country_id

GROUP BY D.country
ORDER BY number_of_customers DESC
LIMIT 10
```


**- Top 5 customers from the top 10 cities who’ve paid the highest total amounts to Rockbuster**

```
SELECT
  A.customers_id,
  A.first_name,
  A.last_name,
  D.country,
  C.city,
  SUM(E.amount) AS Total_amount_paid

FROM Customer A
  INNER JOIN address B ON A. adress_ID = B.address_id
  INNER JOIN city C ON B.city_id = C.city_id
  INNER JOIN country D ON C.country_id = D.country_id
  INNER JOIN payment E ON A.customer_id = E.customer_id

WHERE city IN ('Aurora', 'Atlantico', 'Xintai', 'Adoni', 'Dhule (Dhulia)', 'Kurashiki', 'Pingxiang', 'SIvas', 'Celaya', So Leoplodo')

GROUP BY A.customer_id, D.country, C.city
ORDER BY Total_amount_paid DESC
LIMIT 5
```
