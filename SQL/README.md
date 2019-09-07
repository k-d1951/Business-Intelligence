# SQL

## Selecting Columns and Filtering Rows

- SELECT
``SELECT *``

- FROM
``SELECT * FROM movies``

- DISTINCT For unique entries
``SELECT DISTINCT country FROM movies``

- COUNT 
``SELECT COUNT(DISTINCT *) FROM movies``

- WHERE
``
SELECT * 
FROM films 
WHERE language='Spanish' 
``

- WHERE AND
``
SELECT * 
FROM films 
WHERE language='Spanish' 
AND release_year>2000 
AND release_year<2010
``

- WHERE AND OR 
``
SELECT title,release_year 
FROM films 
WHERE (release_year>=1990 AND release_year <2000)
AND (language='French' OR language='Spanish')
AND gross>2000000
``

- BETWEEN is inclusive, meaning the beginning and end values are included in the results
``
SELECT title,release_year 
FROM films
WHERE (release_year BETWEEN 1990 AND 2000)
AND (budget>100000000)
AND (language='Spanish' OR language='French')
``

- IN operator allows you to specify multiple values in a WHERE clause, making it easier and quicker to specify multiple OR conditions
``
SELECT title,release_year 
FROM films
WHERE release_year IN (1990 ,2000)
AND duration>120
``

- IS NULL is useful when combined with WHERE to figure out what data you're missing
``
SELECT title
FROM films
WHERE budget IS NULL
``

- IS NOT NULL to filter out missing values so you only get results which are not NULL
``
SELECT COUNT(*)
FROM films
WHERE language IS NOT NULL
``

- LIKE operator can be used in a WHERE clause to search for a pattern in a column. %  will match zero, one, or many characters in text. _ will match a single character (also NOT LIKE)
``
SELECT name
FROM people
WHERE name NOT LIKE 'A%'
``

## Aggregate Functions

- SUM
``
SELECT SUM(gross)
FROM films
WHERE release_year>=2000
``

- AVERAGE
``
SELECT AVG(gross)
FROM films
WHERE title LIKE 'A%'
``

- MIN
``
SELECT MIN(gross)
FROM films
WHERE release_year=1994
``

- MAX
``
SELECT MAX(gross)
FROM films
WHERE release_year BETWEEN 2000 AND 2012
``

- AS
``
SELECT title , (duration/60.0) AS duration_hours
FROM films
``

- Percentage
``
SELECT (COUNT(deathdate)*100.0)/count(*) AS percentage_dead
FROM people
``

- Difference
``SELECT (MAX(release_year)-MIN(release_year)) AS difference
FROM films
``

## Sorting, Grouping and Joins

- ORDER BY (ORDER BY always goes after GROUP BY)
``
SELECT title
FROM films 
WHERE release_year IN (2000,2012)
ORDER BY release_year
``

- ORDER BY DESC
``
SELECT imdb_score,film_id
FROM reviews
ORDER BY imdb_score DESC
``

- Multiple column sort
``
SELECT release_year,duration,title
FROM films
ORDER BY release_year,duration
``

- GROUP BY allows you to group a result by one or more columns
``
SELECT release_year, max(budget)
FROM films
GROUP BY release_year
``

