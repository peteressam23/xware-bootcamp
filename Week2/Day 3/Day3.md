
# Exercise 
## You Are Required To Solve This Problem:
Table: Person
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| personId    | int     |
| lastName    | varchar |
| firstName   | varchar |
+-------------+---------+
- personId is the primary key column for this table.
- This table contains information about the ID of some persons and their first and last names- .
___________________________________________________________________________________________________________
- Table: Address
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| addressId   | int     |
| personId    | int     |
| city        | varchar |
| state       | varchar |
+-------------+---------+
- addressId is the primary key column for this table.
- Each row of this table contains information about the city and state of one person with ID = PersonId.
- Write an SQL query to report the first name, last name, city, and state of each person in the Person table. If the address of a personId is not present in the Address table, report null instead.
- Return the result table in any order.
- The query result format is in the following example.
_________________________________________________________________________________________________
### Example 1:
- Input: 
- Person table:
+----------+----------+-----------+
| personId | lastName | firstName |
+----------+----------+-----------+
| 1        | Wang     | Allen     |
| 2        | Alice    | Bob       |
+----------+----------+-----------+
- Address table:
+-----------+----------+---------------+------------+
| addressId | personId | city          | state      |
+-----------+----------+---------------+------------+
| 1         | 2        | New York City | New York   |
| 2         | 3        | Leetcode      | California |
+-----------+----------+---------------+------------+
- Output: 
+-----------+----------+---------------+----------+
| firstName | lastName | city          | state    |
+-----------+----------+---------------+----------+
| Allen     | Wang     | Null          | Null     |
| Bob       | Alice    | New York City | New York |
+-----------+----------+---------------+----------+
- Explanation: 
There is no address in the address table for the personId = 1 so we return null in their city and state.
addressId = 1 contains information about the address of personId = 2.

_____________________________________________________________________________________________________________

## Solution


```
create table if not exists Person(
	personId serial primary key,
	lastName  varchar(50),
	firstName varchar(50)
);

create table if not exists Address(
	addressId serial primary key,
	city varchar(40),
	state varchar(40),
	
	Person_id int references Person(personId)
);

INSERT INTO Person (personId ,lastName , firstName) VALUEs (1,'Wang' , 'Allen') ,(2 , 'Alice' , 'Bob');

INSERT INTO Address (addressId , Person_id , city , state ) VALUEs (1, 2 ,'New York City','New York') ,(2 , 3 , 'Leetcode' , California);

SELECT Person.personId , lastName , firstName , Address.addressId , city , state from Address FULL OUTER JOIN 
Person ON Address.Person_id = Person.personId ;


```
