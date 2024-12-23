# Netflix Movies and TV Shows Data Analysis using SQL

## Overview

This project involves a comprehensive analysis of Netflix's movies and TV shows data using SQL. The goal is to extract valuable insights and answer various business questions based on the dataset. The following README provides a detailed account of the project's objectives, business problems, solutions, findings, and conclusions.

## Objectives

- Analyze the distribution of content types (movies vs TV shows).
- Identify the most common ratings for movies and TV shows.
- List and analyze content based on release years, countries, and durations.
- Explore and categorize content based on specific criteria and keywords.

## Dataset

The data for this project is sourced from the Kaggle dataset:

- **Dataset Link:** [Movies Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows?resource=download)

## Schema

```sql
CREATE TABLE netflix
(
   show_id VARCHAR(10),
   type VARCHAR(15),
   title VARCHAR(150),
   director VARCHAR(220),
   casts VARCHAR(1000),
   country VARCHAR(150),
   data_added VARCHAR(50),
   release_year INT,
   rating VARCHAR(10),
   duration VARCHAR(15),
   listed_in VARCHAR(100),
   description VARCHAR(300)
);

SELECT * FROM netflix;
```

## 15 Business Problems and Solutions

### 1. Count the Number of Movies vs TV Shows

```sql
SELECT
   type,
   count(*) as total_count
FROM netflix
GROUP BY type;
```


### 2. Find the Most Common Rating for Movies and TV Shows

```sql
SELECT 
   type,
   rating
FROM
(
   SELECT 
      type, 
      rating,
      COUNT(*),
      RANK() OVER(PARTITION BY type ORDER BY COUNT(*) DESC) as ranking
   FROM netflix
   GROUP BY 1, 2
)as t1
WHERE
   ranking = 1;
```

### 3. List All Movies Released in a Specific Year (e.g., 2020)

```sql
SELECT * 
FROM netflix
WHERE type='Movie' AND release_year=2020;
```

### 4. Find the Top 5 Countries with the Most Content on Netflix

```sql
SELECT 
   UNNEST(STRING_TO_ARRAY(country, ','))as new_country,
   COUNT(show_id) as total_count
FROM netflix
GROUP BY 1
ORDER BY 2 DESC
LIMIT 5;
```

### 5. Identify the Longest Movie

```sql
SELECT * 
FROM netflix
WHERE type='Movie' AND duration = (SELECT MAX(duration)FROM netflix);
```

### 6. Find Content Added in the Last 5 Years

```sql
SELECT * 
FROM netflix
WHERE
   TO_DATE(data_added, 'Month DD, YYYY') >= CURRENT_DATE - INTERVAL '5 Years';
```

### 7. Find All Movies/TV Shows by Director 'Rajiv Chilaka'

```sql
SELECT * 
FROM netflix
WHERE director ILIKE '%Rajiv Chilaka%';
```

### 8. List All TV Shows with More Than 5 Seasons

```sql
SELECT *
FROM netflix
WHERE 
   type = 'TV Show' 
   AND
   SPLIT_PART(duration, ' ', 1)::numeric > 5;
```

### 9. Count the Number of Content Items in Each Genre

```sql
SELECT 
   UNNEST(STRING_TO_ARRAY(listed_in, ',')) as genre,
   COUNT(show_id) as total_count
FROM netflix
GROUP BY 1;
```

### 10. Find each year and the average numbers of content release in India on netflix. Return top 5 year with highest avg content release

```sql
SELECT 
   EXTRACT(YEAR FROM TO_DATE(data_added, 'Month DD, YYYY')) as year,
   COUNT(*) as yearly_content,
   ROUND(COUNT(*)::numeric/(SELECT COUNT(*) FROM netflix WHERE country='India') * 100
   ,2)as avg_content_per_year
FROM netflix
WHERE country = 'India'
GROUP BY 1
LIMIT 5;
```

### 11. List All Movies that are Documentaries

```sql
SELECT *
FROM netflix
WHERE listed_in ILIKE '%documentaries%';
```

### 12. Find All Content Without a Director

```sql
SELECT *
FROM netflix
WHERE director IS NULL;
```

### 13. Find How Many Movies Actor 'Salman Khan' Appeared in the Last 10 Years

```sql
SELECT *
FROM netflix
WHERE 
   casts ILIKE '%Salman Khan%'
   AND
   release_year > EXTRACT(YEAR FROM CURRENT_DATE) - 10;
```

### 14. Find the Top 10 Actors Who Have Appeared in the Highest Number of Movies Produced in India

```sql
SELECT 
   UNNEST(STRING_TO_ARRAY(casts, ',')) as actors,
   COUNT(*) as total_count
FROM netflix
WHERE country ILIKE '%India%'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;
```

### 15. Categorize Content Based on the Presence of 'Kill' and 'Violence' Keywords

```sql
WITH new_table 
as
(
   SELECT
      *,
      CASE
      WHEN
         description ILIKE '%Kill%' OR description ILIKE '%Violence%' THEN 'Bad Content'
      ELSE 'Good Content'
      END category
   FROM netflix
)
   SELECT 
      category,
      COUNT(*) as total_count
   FROM new_table
   GROUP BY 1;
```
