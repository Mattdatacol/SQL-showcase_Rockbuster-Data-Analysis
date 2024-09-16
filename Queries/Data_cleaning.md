# Examples of data cleaning requests used on the customers' table

**- Check for duplicate rows**

```
SELECT customer_id, store_id, first_name, last_name, email, address_id, activebool,create_date, last_update, active,
COUNT(*)
FROM customer
GROUP BY customer_id, store_id, first_name, last_name, email, address_id, activebool,create_date, last_update, active
HAVING COUNT(*) > 1
```

**- Check for missing values**

```
SELECT *
FROM customer
WHERE customer_id IS NULL
OR store_id IS NULL
OR first_name IS NULL
OR last_name IS NULL
OR email IS NULL
OR address_id IS NULL
OR activebool IS NULL
OR create_date IS NULL
OR last_update IS NULL
OR active IS NULL;
```

**- Check for non-uniform data in last name and first name**

```
SELECT last_name, first_name, 
COUNT(*)
FROM customer
WHERE last_name LIKE '% %'
AND last_name LIKE '%1%'
AND last_name LIKE '%2%'
AND last_name LIKE '%3%'
AND last_name LIKE '%4%'
AND last_name LIKE '%5%'
AND last_name LIKE '%6%'
AND last_name LIKE '%7%'
AND last_name LIKE '%8%'
AND last_name LIKE '%9%'
AND last_name LIKE '%0%'

AND first_name LIKE '% %'
AND first_name LIKE '%1%'
AND first_name LIKE '%2%'
AND first_name LIKE '%3%'
AND first_name LIKE '%4%'
AND first_name LIKE '%5%'
AND first_name LIKE '%6%'
AND first_name LIKE '%7%'
AND first_name LIKE '%8%'
AND first_name LIKE '%9%'
AND first_name LIKE '%0%'
GROUP BY customer_id
```
