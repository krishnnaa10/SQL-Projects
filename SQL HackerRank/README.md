# SQL HackerRank

Q1- Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY
WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";
```
