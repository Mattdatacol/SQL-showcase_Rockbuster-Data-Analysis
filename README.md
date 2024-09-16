# SQL-showcase_Rockbuster-Data-Analysis

## Context

The fictional Rockbuster Stealth LLC is a movie rental company that used to have stores around the world. Facing stiff competition from streaming services such as Netflix and Amazon Prime, the Rockbuster Stealth management team is planning to use its existing movie licenses to launch an online video rental service in order to stay competitive.

Working as a data analyst in Rockbuster Stealth’s business intelligence (BI) department, the mission is to help with the launch strategy for the new online video service.

## Key questions leading the project

- Which movies contributed the most/least to revenue gain?
- What was the average rental duration for all videos?
- Which countries are Rockbuster customers based in?
- Where are customers with a high lifetime value based?
- Do sales figures vary between geographic regions?
 
## Data set & tools

- Source: [postgresqltutorial.com](http://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip)

- RDBMS: [PostgreSQL](https://www.postgresql.org/) and [DbVisualizer](https://www.dbvis.com/)

- ERD:

Simplified organic ERD to see the schema of the database:
![Simplified organic ERD:](https://github.com/Mattdatacol/SQL-showcase_Rockbuster-Data-Analysis/blob/400f740a577129c7ecdbd7973538b36a76631f14/images/ERD-Rockbuster-Organic.png)
There are two main snowflakes, the primary around the rental table and then a secondary around the film table

Full ERD with all tables and variables:
![Full ERD](https://github.com/Mattdatacol/SQL-showcase_Rockbuster-Data-Analysis/blob/400f740a577129c7ecdbd7973538b36a76631f14/images/ERD%20Rockbuster.png)
The Entity Relationship Diagram accounts for all 15 tables and promary keys used.


## Links to the SQL queries
- Data cleaning
- grouping/Aggregations
- Subqueries
- CTEs
> [!NOTE]
> No database manipulation other than selections were used since the data was already clean


## [Link to Tableau with the graphs and Choropleth maps created from the queries](https://public.tableau.com/views/3_10Rockbusterfinal/Story1?:language=fr-FR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
