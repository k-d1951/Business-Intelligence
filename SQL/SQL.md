SQL Query to get total number of tickets booked for a movie theatre schema

    SELECT plays.id AS id, 
    plays.title AS title, 
    COALESCE(SUM(reservations.number_of_tickets),0) AS reserved_tickets
    FROM plays   
    LEFT JOIN reservations
    ON plays.id=reservations.play_id
    GROUP BY plays.title
    ORDER BY reserved_tickets DESC , title DESC
    
SQL Query to get the number of free rooms

    SELECT MAX(rooms_req) AS rooms
    FROM (

    SELECT Count(*)rooms_req 
    FROM meetings a
    LEFT JOIN meetings b
    ON a.start_time BETWEEN b.start_time AND b.end_time
    GROUP BY a.id

    )

    y;


    class Solution {
        public int solution(int A, int B) {
        if (A>B){return 0;}
        int sqrtA=(int)Math.ceil(Math.sqrt(A));
        int sqrtB=(int)Math.floor(Math.sqrt(B));
        if (sqrtA>sqrtB){return 0;}
        return 1+ solution(sqrtA,sqrtB);
    }

    }

