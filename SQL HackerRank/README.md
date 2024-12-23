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

**Q26-** Query a count of the number of cities in CITY having a Population larger than.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT COUNT(POPULATION)
FROM CITY
WHERE POPULATION > 100000;
```

**Q27-** Query the total population of all cities in CITY where District is California.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT SUM(POPULATION)
FROM CITY
WHERE DISTRICT = 'California';
```

**Q28-** Query the average population of all cities in CITY where District is California.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT AVG(POPULATION)
FROM CITY
WHERE DISTRICT = 'California';
```

**Q29-** Query the average population for all cities in CITY, rounded down to the nearest integer.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT ROUND(AVG(POPULATION))
FROM CITY;
```

**Q30-** Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT SUM(POPULATION)
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```

**Q31-** Query the difference between the maximum and minimum populations in CITY.

The CITY table is described as follows:

![1449729804-f21d187d0f-CITY](https://github.com/user-attachments/assets/628ff322-82e8-40c5-be74-33c45703380c)

```SQL
SELECT (MAX(POPULATION) - MIN(POPULATION))
FROM CITY;
```

**Q32-** Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's 0 key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.: *actual -- miscalculated* average monthly salaries), and round it up to the next integer.

The EMPLOYEES table is described as follows:

![1443817108-adc2235c81-1](https://github.com/user-attachments/assets/f348043e-882c-4bbb-9e15-b48a5a4a9bf1)

Note: Salary is per month.

Constraints

1000 < Salary < 100000

```SQL
SELECT CEIL(AVG(Salary) - AVG(REPLACE(Salary, '0', '')))
FROM EMPLOYEES;
```

**Q33-** We define an employee's total earnings to be their monthly *salary * months* worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

The Employee table containing employee data for a company is described as follows:

![1458557872-4396838885-ScreenShot2016-03-21at4 27 13PM](https://github.com/user-attachments/assets/5d2f852e-f377-492c-a97b-e140e32f004e)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

```SQL
SELECT MAX(salary * months), COUNT(*)
FROM Employee
WHERE (salary * months) >= (SELECT MAX(Salary * months) FROM Employee);
```

**Q34-** Query the following two values from the STATION table:

The sum of all values in LAT_N rounded to a scale of 2 decimal places.
The sum of all values in LONG_W rounded to a scale of 2 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(SUM(LAT_N),2), ROUND(SUM(LONG_W),2)
FROM STATION;
```

**Q35-** Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(SUM(LAT_N),4)
FROM STATION
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```

**Q36-** Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(MAX(LAT_N),4)
FROM STATION
WHERE LAT_N < 137.2345;
```

**Q37-** Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(LONG_W,4)
FROM STATION
WHERE LAT_N < 137.2345
ORDER BY LAT_N DESC
LIMIT 1;
```

**Q38-** Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(LAT_N,4)
FROM STATION
WHERE LAT_N > 38.7780
ORDER BY LAT_N ASC
LIMIT 1;
```

**Q39-** Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780. Round your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(LONG_W,4)
FROM STATION
WHERE 
   LAT_N = (SELECT MIN(LAT_N) 
            FROM STATION 
            WHERE LAT_N> 38.7780);
```

**Q40-** Consider p1(a,b) and p2(c,d) to be two points on a 2D plane.

 + a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
 + b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
 + c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
 + d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points p1 and p2 and round it to a scale of 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(ABS(MIN(LAT_N) - MAX(LAT_N)) + ABS(MIN(LONG_W) - MAX(LONG_W)),4)
FROM STATION;
```

**Q41-** Consider p1(a,c) and p2(b,d) to be two points on a 2D plane where (a,b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points p1 and p2 and format your answer to display 4 decimal digits.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(SQRT(POW(MAX(LAT_N)-MIN(LAT_N),2) + POW(MAX(LONG_W)-MIN(LONG_W),2)),4)
FROM STATION;
```

**Q42-** A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to 4 decimal places.

The STATION table is described as follows:

![wheretwr](https://github.com/user-attachments/assets/7d19fe97-0fb8-440e-8afe-8ee00dd50bc7)

where LAT_N is the northern latitude and LONG_W is the western longitude.

```SQL
SELECT ROUND(LAT_N, 4)
FROM(
   SELECT ROW_NUMBER() 
   OVER(ORDER BY LAT_N ASC) AS rnk, LAT_N 
   FROM STATION
   )a    
WHERE rnk = (
   SELECT ROUND(COUNT(*)/2) 
   FROM STATION);
```

**Q43-** Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

The CITY and COUNTRY tables are described as follows:

![CITY](https://github.com/user-attachments/assets/cb519107-c425-4f31-ac9e-bad7259cddca)

![COUNTRY](https://github.com/user-attachments/assets/4e71c8b0-2b30-4c2a-b989-6a45e12be8fe)

```SQL
SELECT SUM(a.POPULATION)
FROM CITY a, COUNTRY b
WHERE a.COUNTRYCODE = b.CODE AND b.CONTINENT = 'ASIA';
```

**Q44-** Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

The CITY and COUNTRY tables are described as follows:

![CITY](https://github.com/user-attachments/assets/cb519107-c425-4f31-ac9e-bad7259cddca)

![COUNTRY](https://github.com/user-attachments/assets/4e71c8b0-2b30-4c2a-b989-6a45e12be8fe)

```SQL
SELECT a.NAME
FROM CITY a, COUNTRY b
WHERE a.COUNTRYCODE = b.CODE AND b.CONTINENT = 'AFRICA';
```

**Q45-** Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

The CITY and COUNTRY tables are described as follows:

![CITY](https://github.com/user-attachments/assets/cb519107-c425-4f31-ac9e-bad7259cddca)

![COUNTRY](https://github.com/user-attachments/assets/4e71c8b0-2b30-4c2a-b989-6a45e12be8fe)

```SQL
SELECT b.CONTINENT, FLOOR(AVG(a.POPULATION)) AS avg_population
FROM CITY a
JOIN COUNTRY b ON a.COUNTRYCODE = b.CODE
GROUP BY b.CONTINENT;
```

**Q46-** You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

![1443818166-a5c852caa0-1](https://github.com/user-attachments/assets/b44e75a8-b977-4eb4-94f1-f28ff190dda6)

Grades contains the following data:

![1443818137-69b76d805c-2](https://github.com/user-attachments/assets/cd21e6ef-def9-45a6-a3b5-3f0fdb00a7cd)

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

```SQL
SELECT CASE
   WHEN g.Grade < 8 THEN 'NULL'
   ELSE s.Name
   END
, g.Grade, s.Marks
FROM Students AS s, Grades AS g
WHERE s.Marks >= g.Min_Mark AND s.Marks <= g.Max_Mark
ORDER BY g.Grade DESC, s.Name ASC, s.Marks ASC;
```

**Q47-** Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores in same number of challenges, then sort them by ascending hacker_id.

The following tables contain contest data:

Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker. 

![HACKERS](https://github.com/user-attachments/assets/1e6ecc4b-585d-4279-9e82-60d6c99653c1)

Difficulty: The difficult_level is the level of difficulty of the challenge, and score is the score of the challenge for the difficulty level. 

![DIFF](https://github.com/user-attachments/assets/22f249f1-c49d-463c-a1aa-e32bddadfa84)

Challenges: The challenge_id is the id of the challenge, the hacker_id is the id of the hacker who created the challenge, and difficulty_level is the level of difficulty of the challenge. 

![CHALL](https://github.com/user-attachments/assets/2d92887e-163f-4e6c-9a26-6d8287f80625)

Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge that the submission belongs to, and score is the score of the submission.

![SUBM](https://github.com/user-attachments/assets/744e038e-9121-489e-af3c-012ad96d3fe2)

```SQL
SELECT 
   h.hacker_id,
   h.name
FROM Submissions s
   INNER JOIN Challenges c ON s.challenge_id = c.challenge_id
   INNER JOIN Difficulty d ON d.difficulty_level = c.difficulty_level
   INNER JOIN Hackers h ON s.hacker_id = h.hacker_id
WHERE d.score = s.score
GROUP BY h.hacker_id, h.name
HAVING COUNT(s.hacker_id) > 1
ORDER BY COUNT(s.challenge_id) DESC, s.hacker_id;
```

**Q48-** Harry Potter and his friends are at Ollivander's with Ron, finally replacing Charlie's old broken wand.

Hermione decides the best way to choose is by determining the minimum number of gold galleons needed to buy each non-evil wand of high power and age. Write a query to print the id, age, coins_needed, and power of the wands that Ron's interested in, sorted in order of descending power. If more than one wand has same power, sort the result in order of descending age.

The following tables contain data on the wands in Ollivander's inventory:

Wands: The id is the id of the wand, code is the code of the wand, coins_needed is the total number of gold galleons needed to buy the wand, and power denotes the quality of the wand (the higher the power, the better the wand is). 

![1458538092-b2a8163a74-ScreenShot2016-03-08at12 13 39AM](https://github.com/user-attachments/assets/d45cccb3-6a98-44e6-ae79-2dd791802dbe)

Wands_Property: The code is the code of the wand, age is the age of the wand, and is_evil denotes whether the wand is good for the dark arts. If the value of is_evil is 0, it means that the wand is not evil. The mapping between code and age is one-one, meaning that if there are two pairs, (code1, age1) and (code2, age2), then code1 ≠ code2 and age1 ≠ age2.

![1458538221-18c4092b7d-ScreenShot2016-03-08at12 13 53AM](https://github.com/user-attachments/assets/e0634cf6-0f30-4fa1-8160-aa45c0aebc7f)

```SQL
SELECT x.id, y.age, x.coins_needed, x.power
FROM Wands AS x
JOIN Wands_Property AS y ON x.code = y.code
JOIN(SELECT age AS a, MIN(coins_needed) AS c, power AS p
FROM Wands AS x1
JOIN Wands_Property AS y1 ON x1.code = y1.code
WHERE is_evil = 0
GROUP BY power, age) AS q ON y.age = a AND x.coins_needed = c AND x.power = p
ORDER BY x.power DESC, y.age DESC
```
