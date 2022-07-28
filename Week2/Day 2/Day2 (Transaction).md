# Exercise
- Create a new transaction then:
- Insert a new record into the Professor table
- Insert a new record into the Student table
- Select all the Professors and students
- Open another session and select all the Professors and students. What is the difference?
- Return to the first session and delete the Professors with the salary greater than 20000
- Open another session and select all the Professors and students. What is the difference?
- Return to the first session and rollback the transaction
- Open another session and select all the Professors and students. What is the difference?
- Return to the first session Start a new transaction
- nsert a new record into the Professor table
- Insert a new record into the Student table
- Commit the transaction
- Open another session and select all the Professors and students. What is the difference?
- Return to the first session start a new transaction
- Insert a new record into the Professor table with a duplicated id. What happens?
- Try to insert a new record into the Student table with a duplicated id. What happens?
- Try to commit the transaction. What happens?
- Try to rollback the transaction. What happens?

_______________________________________________________________________________________

## Solution

```	
	begin ;

	SELECt *from Faculty;
	SELECT * from Departement;

	INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id , Departement_id)
	VALUES('Beshoy', 'Hany', 56 , 500000 , 'Not Have Image', 1 , 1);

	INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUES
	('Ahmed' , 'Omar' , 0100005555 , 0122258663 , 8-8-2008 , 'Not Have Image');

	SELECT * from Professor;
	SELECT * from Student;
    
	(When Open New Session And Select All Professors & Students Not occur Any Thing Difference)

    DELETE FROM Professor where Salary > 20000 ;

	When Open New Session And Select All Professors & Students Not occur Any Thing Difference)

	ROllback;


    When Open New Session And Select All Professors & Students Not occur Any Thing Difference)


	begin ;

	INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id ,  Departement_id)
	VALUES('Fady', 'Botros', 25, 250000 , 'Not Have Image' , 1 , 2);

	INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUEs 
	('Bebo' , 'Osama' , 0100005555 , 0122258663 , 2008 , 'Not Have Image');
	
   commit ;  


   When Open New Session And Select All Professors & Students I Look Difference In Tables)


   When Insert New Records Into Professor & Student With Duplicated Id 
   I Found Error Becaus Can't Duplicate Primary Key 

```
   ________________________________________________________________________________________
