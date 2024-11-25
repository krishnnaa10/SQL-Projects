# SQL HackerRank

**Q1-** Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY
WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";
```

**Q2-** Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT NAME
FROM CITY
WHERE POPULATION > 120000 AND COUNTRYCODE = "USA";
```

**Q3-** Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY;
```

**Q4-** Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY
WHERE ID = 1661;
```

**Q4-** Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY
WHERE COUNTRYCODE = "JPN";
```
