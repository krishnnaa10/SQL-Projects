# SQL HackerRank

**Q1-** Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT *
FROM CITY
WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";
```

**Q2-** Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT NAME
FROM CITY
WHERE POPULATION > 120000 AND COUNTRYCODE = "USA";
```

**Q3-** Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT *
FROM CITY;
```

**Q4-** Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT *
FROM CITY
WHERE ID = 1661;
```

**Q5-** Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT *
FROM CITY
WHERE COUNTRYCODE = "JPN";
```

**Q6-** Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

<img src="https://github.com/user-attachments/assets/00e37002-c8a2-457f-8877-db815c6f26b4" alt="Screenshot" height="200" />

```SQL
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = "JPN";
```

**Q7-** Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT CITY, STATE
FROM STATION;
```

**Q8-** Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0;
```

**Q9-** Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

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

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

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

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(CITY,1,1) IN ('A','E','I','O','U');
```

**Q12-** Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(REVERSE(CITY),1,1) IN ('A','E','I','O','U');
```

**Q13-** Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE 
   SUBSTRING(CITY,1,1) IN ('A','E','I','O','U') 
   AND 
   SUBSTRING(REVERSE(CITY),1,1) IN ('A','E','I','O','U');
```

**Q14-** Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(CITY,1,1) NOT IN ('A','E','I','O','U');
```

**Q15-** Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE SUBSTRING(REVERSE(CITY),1,1) NOT IN ('A','E','I','O','U');
```

**Q16-** Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE 
   SUBSTRING(CITY,1,1) NOT IN ('A','E','I','O','U') 
   OR 
   SUBSTRING(REVERSE(CITY),1,1) NOT IN ('A','E','I','O','U');
```

**Q17-** Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

The STATION table is described as follows:

<img src="https://github.com/user-attachments/assets/899274aa-f264-43ab-9c0b-d8f6e2f7019c" alt="Screenshot" height="200" />

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT DISTINCT CITY
FROM STATION
WHERE 
   SUBSTRING(CITY,1,1) NOT IN ('A','E','I','O','U') 
   AND
   SUBSTRING(REVERSE(CITY),1,1) NOT IN ('A','E','I','O','U');
```

**Q18-** Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

The STUDENTS table is described as follows:

![1443815243-94b941f556-1](https://github.com/user-attachments/assets/516b72fd-8367-437f-9cc7-cf7995edb9d4)

```SQL
SELECT Name
FROM STUDENTS
WHERE Marks > 75
ORDER BY SUBSTRING(Name, -3, 3), ID ASC;
```

**Q19-** Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

The Employee table containing employee data for a company is described as follows:

![1458557872-4396838885-ScreenShot2016-03-21at4 27 13PM](https://github.com/user-attachments/assets/db69b138-5eaf-4b83-bf03-fb074ca7cdcf)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

```SQL
SELECT name
FROM Employee
ORDER BY name ASC;
```

**Q20-** Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

The Employee table containing employee data for a company is described as follows:

![1458557872-4396838885-ScreenShot2016-03-21at4 27 13PM](https://github.com/user-attachments/assets/a2430eb0-d51e-4d98-b2e3-f24e57311edb)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

```SQL
SELECT name
FROM Employee
WHERE salary > 2000 AND months < 10
ORDER BY employee_id ASC;
```

**Q21-** Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with  sides of equal length.
Isosceles: It's a triangle with  sides of equal length.
Scalene: It's a triangle with  sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

The TRIANGLES table is described as follows:

![3](https://github.com/user-attachments/assets/d1065e1d-9a81-409b-b8ad-6bb79b8c3eb9)

Each row in the table denotes the lengths of each of a triangle's three sides.

```SQL
SELECT 
    CASE
        WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
        WHEN A = B AND B = C THEN 'Equilateral'
        WHEN A = B OR B = C OR A = C THEN 'Isosceles'
        ELSE 'Scalene'
    END AS TriangleType
FROM TRIANGLES;
```

**Q22-** Generate the following two result sets:

1.Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).

2.Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

**There are a total of [occupation_count] [occupation]s.**

where **[occupation_count]** is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same **[occupation_count]**, they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

The OCCUPATIONS table is described as follows:

![1443816414-2a465532e7-1](https://github.com/user-attachments/assets/ad357373-90d2-4c37-94a7-b10b8f6fee5d)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

```SQL
SELECT CONCAT(Name,"(",SUBSTRING(Occupation,1,1),")")
FROM OCCUPATIONS
ORDER BY Name ASC;

SELECT CONCAT("There are a total of ", COUNT(Occupation)," ", Lower(Occupation),"s.")
FROM OCCUPATIONS
GROUP BY Occupation
ORDER BY COUNT(Occupation) ASC;
```

**Q23-** Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

Note: Print NULL when there are no more names corresponding to an occupation.

The OCCUPATIONS table is described as follows:

![1443816414-2a465532e7-1](https://github.com/user-attachments/assets/ad357373-90d2-4c37-94a7-b10b8f6fee5d)

Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

```SQL
SELECT 
   MAX(CASE WHEN Occupation = 'Doctor' THEN Name ELSE NULL END)AS Doctor,
   MAX(CASE WHEN Occupation = 'Professor' THEN Name ELSE NULL END)AS Professor,
   MAX(CASE WHEN Occupation = 'Singer' THEN Name ELSE NULL END)AS Singer,
   MAX(CASE WHEN Occupation = 'Actor' THEN Name ELSE NULL END)AS Actor
FROM(
   SELECT 
      Name, 
      Occupation,
         ROW_NUMBER() OVER (PARTITION BY Occupation ORDER BY Name) AS RowNum
   FROM OCCUPATIONS
)AS SortedOccupations
GROUP BY RowNum
ORDER BY RowNum;
```

**Q24-** You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

![1443818507-5095ab9853-1](https://github.com/user-attachments/assets/8d745a50-8d04-48ca-9037-1640fa49a51b)

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.

```SQL
SELECT 
   N, 
   CASE 
      WHEN P IS NULL THEN 'Root'
      WHEN(SELECT COUNT(*) FROM BST WHERE P = b.N) > 0 THEN 'Inner'
      ELSE 'Leaf'
   END
FROM BST b
ORDER BY N;
```

**Q25-** Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

![1458531031-249df3ae87-ScreenShot2016-03-21at8 59 56AM](https://github.com/user-attachments/assets/eaf76a9d-b88d-4032-ae4f-9fbe2eaa41e8)

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

The tables may contain duplicate records.
The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.
Input Format

The following tables contain company data:

Company: The company_code is the code of the company and founder is the founder of the company.

![1458531125-deb0a57ae1-ScreenShot2016-03-21at8 50 04AM](https://github.com/user-attachments/assets/9124021d-5fd3-426c-a372-ed5160054a5c)

Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company. 

![le](https://github.com/user-attachments/assets/0fbabd0d-ecf5-4c2c-b1cc-283996b5db87)

Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![sm](https://github.com/user-attachments/assets/a0e9c8c0-428c-4b88-8150-f8f8be687fb8)

Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![mc](https://github.com/user-attachments/assets/03042e17-11ef-489d-9618-d55bbfaff59d)

Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

![ec](https://github.com/user-attachments/assets/1d1c6b53-a2cf-43db-b031-411d49edb184)

```SQL
SELECT 
   C.company_code,
   C.founder,
   COUNT(DISTINCT L.lead_manager_code),
   COUNT(DISTINCT S.senior_manager_code),
   COUNT(DISTINCT M.manager_code),
   COUNT(DISTINCT E.employee_code)
FROM Company AS C

JOIN lead_manager AS L
ON C.company_code = L.company_code

JOIN senior_manager AS S
ON L.lead_manager_code = S.lead_manager_code

JOIN manager AS M
ON M.senior_manager_code = S.senior_manager_code

JOIN employee AS E
ON E.manager_code = M.manager_code

GROUP BY C.company_code, C.founder
ORDER BY C.company_code;
```
