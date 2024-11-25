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

**Q5-** Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT *
FROM CITY
WHERE COUNTRYCODE = "JPN";
```

**Q6-** Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="300" />

```SQL
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = "JPN";
```

**Q7-** Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT CITY, STATE
FROM STATION;
```

**Q8-** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0;
```

**Q9-** Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT
(
   SELECT COUNT(CITY)FROM STATION) - (SELECT COUNT(DISTINCT CITY)
   FROM STATION
);
```

**Q10-** Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) ASC, CITY
LIMIT 1;

SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY
LIMIT 1;
```

**Q11-** Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(CITY,1,1) IN ('A','E','I','O','U');
```

**Q12-** Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(REVERSE(CITY),1,1) IN ('A','E','I','O','U');
```

**Q13-** Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE 
   SUBSTRING(CITY,1,1) IN ('A','E','I','O','U') 
   AND 
   SUBSTRING(REVERSE(CITY),1,1) IN ('A','E','I','O','U');
```

**Q14-** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="300" />

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0;
```
