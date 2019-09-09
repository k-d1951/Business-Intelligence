-- write your code in SQLite 3.11.0
SELECT plays.id AS id, 
plays.title AS title, 
COALESCE(SUM(reservations.number_of_tickets),0) AS reserved_tickets
FROM plays   
LEFT JOIN reservations
ON plays.id=reservations.play_id
GROUP BY plays.title
ORDER BY reserved_tickets DESC , title DESC
