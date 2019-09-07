SQL

-SELECT
``SELECT *``

-FROM
``SELECT * FROM movies``

-DISTINCT - For unique entries
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
