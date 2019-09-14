### 2nd Highest Salary
     SELECT MAX(Salary) AS SecondHighestSalary
     FROM Employee
     WHERE Salary NOT IN (SELECT MAX(Salary) AS SecondHighestSalary
     FROM Employee)

### student class >= 5
    SELECT class
    FROM courses
    GROUP BY class 
    HAVING COUNT(DISTINCT student) >=  5 
    
### display the ones with nulls in other joined table
    SELECT Customers.Name AS Customers
    FROM Customers
    LEFT join Orders
    ON Customers.Id=Orders.CustomerId
    WHERE Orders.CustomerId IS NULL

### join 2 tables
    SELECT p.FirstName, p.LastName, Address.City, Address.State
    FROM Person p
    LEFT JOIN Address
    ON p.PersonId=Address.PersonId
    
### Even Odd
    SELECT *
    FROM cinema
    WHERE id%2 !=0 and description != 'boring'
    ORDER BY rating DESC
