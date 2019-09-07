SQL

-SELECT
``SELECT *``

-FROM
``SELECT * FROM movies``

-DISTINCT For unique entries
``SELECT DISTINCT country FROM movies``

-COUNT 
``SELECT COUNT(DISTINCT *) FROM movies``

-WHERE
``
SELECT * 
FROM films 
WHERE language='Spanish' 
``

-WHERE AND
``
SELECT * 
FROM films 
WHERE language='Spanish' 
AND release_year>2000 
AND release_year<2010
``

-WHERE AND OR 
``
SELECT title,release_year 
FROM films 
WHERE (release_year>=1990 AND release_year <2000)
AND (language='French' OR language='Spanish')
AND gross>2000000
``

-BETWEEN is inclusive, meaning the beginning and end values are included in the results
``
SELECT title,release_year 
FROM films
WHERE (release_year BETWEEN 1990 AND 2000)
AND (budget>100000000)
AND (language='Spanish' OR language='French')
``
-IN operator allows you to specify multiple values in a WHERE clause, making it easier and quicker to specify multiple OR conditions
``

``
