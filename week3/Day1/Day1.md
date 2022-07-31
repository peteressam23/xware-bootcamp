
# Exercise 1

- Please Try To Solve This Problem
- Table: Person
+-------------+---------+ | Column Name | Type | +-------------+---------+ | id | int | | email | varchar | +-------------+---------+

- id is the primary key column for this table.
- Each row of this table contains an email. The emails will not contain uppercase letters.
- Write an SQL query to delete all the duplicate emails, keeping only one unique email with the smallest id. Note that you are supposed to write a DELETE statement and not a SELECT one.
- After running your script, the answer shown is the Person table. The driver will first compile and run your piece of code and then show the Person table. The final order of the Person table does not matter.

- The query result format is in the following example.
- Example 1:
- Input:
- Person table: +----+------------------+ | id | email | +----+------------------+ | 1 | john@example.com | | 2 | bob@example.com | | 3 | john@example.com | +----+------------------+

- Output:
+----+------------------+ | id | email | +----+------------------+ | 1 | john@example.com | | 2 | bob@example.com | +----+------------------+ Explanation: john@example.com is repeated two times. We keep the row with the smallest Id = 1.

_________________________________________________________________________________________________________________

## Solution

```
create table if not exists person_table (
		id serial primary key ,
	     email varchar(60)  not null 

	
);

insert into person_table  (email) values (' john@example.com ');

insert into person_table  (email) values (' bob@example.com ');

insert into person_table  (email) values (' john@example.com ');

select * from person_table ;

DELETE FROM person_table a USING person_table b WHERE a.id > b.id AND a.email = b.email;

select * from person_table  ;

```

________________________________________________________________________________________________________________



# Exercise 2

- Table: Logins
+----------------+----------+
| Column Name    | Type     |
+----------------+----------+
| user_id        | int      |
| time_stamp     | datetime |
+----------------+----------+
- (user_id, time_stamp) is the primary key for this table.
- Each row contains information about the login time for the user with ID user_id.
- Write an SQL query to report the latest login for all users in the year 2020. Do not include the users who did not login in 2020.
- Return the result table in any order.
- The query result format is in the following example.
- Example 1:
- Input: 
- Logins table:
+---------+---------------------+
| user_id | time_stamp          |
+---------+---------------------+
| 6       | 2020-06-30 15:06:07 |
| 6       | 2021-04-21 14:06:06 |
| 6       | 2019-03-07 00:18:15 |
| 8       | 2020-02-01 05:10:53 |
| 8       | 2020-12-30 00:46:50 |
| 2       | 2020-01-16 02:49:50 |
| 2       | 2019-08-25 07:59:08 |
| 14      | 2019-07-14 09:00:00 |
| 14      | 2021-01-06 11:59:59 |
+---------+---------------------+
- Output: 
+---------+---------------------+
| user_id | last_stamp          |
+---------+---------------------+
| 6       | 2020-06-30 15:06:07 |
| 8       | 2020-12-30 00:46:50 |
| 2       | 2020-01-16 02:49:50 |
+---------+---------------------+
- Explanation: 
- User 6 logged into their account 3 times but only once in 2020, so we include this login in the result table.
- User 8 logged into their account 2 times in 2020, once in February and once in December. We include only the latest one (December) in the result table.
- User 2 logged into their account 2 times but only once in 2020, so we include this login in the result table.
- User 14 did not login in 2020, so we do not include them in the result table.

__________________________________________________________________________________________________________
 
## Solution

```

create table if not exists login(
	user_id int  ,
	Date_Time timestamp ,
	primary key (user_id , Date_Time)
);

DROP TABLE login ;


INSERT INTO login(user_id, Date_Time) VALUES(6, '2020-06-30 15:06:07' ),
											 (6, '2021-04-21 14:06:06' ),
											 (6, '2019-03-07 00:18:15' ),
											 (8, '2020-02-01 05:10:53' ),
											 (8, '2020-12-30 00:46:50' ),
											 (2, '2020-01-16 02:49:50' ),
											 (2, '2019-08-25 07:59:08' ),
											 (14, '2019-07-14 09:00:00'),
											 (14, '2021-01-06 11:59:59' );
											 
											 
select * from login ;


select user_id,max(Date_Time)
		      as last_stamp from Login
		      WHERE Date_Time >= '2020-01-01'
			   and Date_Time < '2021-01-01'
				group by user_id;

```

______________________________________________________________________________________________________________
