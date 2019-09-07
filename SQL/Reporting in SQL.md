SELECT 
	sport, 
    COUNT(DISTINCT event) AS events, 
    COUNT(DISTINCT athlete_id) AS athletes
FROM summer_games
GROUP BY sport;
