# Commands Ex.1 (Solution)




##Create New Transaction
   ```
   begin ;
   
   ````
##insert New Record into Professor table
  
  ```
  INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id , Departement_id)
  VALUES('Beshoy', 'Hany', 25, 500 , 'Hi', 50 , 1);
  
  ````
  
##Insert New Record into Student table
  ```
   INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUEs
   ('Ahmed' , 'Omar' , 0100005555 , 0122258663 , 2008 , 'hi');
 
  ````
##Select all the Professors and students
  ````
    select * from Professor ;
    select * from Student;
  ````
    
##Open another session and select all the Professors and students. What is the difference?    
   
   ```
    tables Not have any Change (Not add new data)
    ````
##Open another session and select all the Professors and students. What is the difference?
    ```
    DELETE FROM Professor where Salary > 20000 ;
    ````
##Open another session and select all the Professors and students. What is the difference?
     ```
      tables Not have any Change (Not add new data)
      ````
##Return to the first session and rollback the transaction
      ```
      Rollback ;
      ````

##Open another session and select all the Professors and students. What is the difference?
      ````
      tables Not have any Change (Not add new data)   
      ```
      
##Return to the first session Start a new transaction
       ```
       begin ;
       ````
##Insert a new record into the Professor table 
     ``` INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id ,  Departement_id)
       VALUES('Fady', 'Botros', 25, 500 , 'Hi', 50 , 1);
        ````
        
        
##Insert a new record into the Student table    
     ```
     INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUEs 
      ('Bebo' , 'Osama' , 0100005555 , 0122258663 , 2008 , 'hi');
      ````
      
##Commit the transaction
     ```
       commit ;      
      ````
##Open another session and select all the Professors and students. What is the difference?
    ```
    select * from Professor ;
    select * from Student;
      New Recordes have Added in tables
    ````
##Return to the first session start a new transaction
   ```
   begin ;
   ````
##Insert a new record into the Professor table with a duplicated id. What happens?             
  ```
  error (because can't use id for more Row)
 ````
##Try to insert a new record into the Student table with a duplicated id. What happens? 
   ```
   error (because can't use id for more Row)
   ````
##Try to commit the transaction. What happens?
     ```
     commit ;
     ````
##Try to rollback the transaction. What happens?
   ```
   Rollback ;
   
   ````
   
   


# Commands Ex.2 (Solution)   
  
    Note (I Don't UnderStand good Join And  I don't Know The Solution Num 3 & 4) 
    
##Select Subject id, Subject Name, Subject Code, Course Duration in One Query
    ```
    Select Subjects.id, Code, Duration From Course INNER JOIN Subjects ON Course.Subject_id =
     Subjects.id;
     ````

        
##Select Subject id, Subject Name, Subject Code, Course Duration, Professor First_name, Professor Last_name, in One Query
      ```
       Select Subjects.id, Name, Code, Duration, F_Name, L_Name From Course INNER JOIN
       Subjects ON Course.Subject_id = Subjects.id INNER JOIN Professor ON Course.Professor_id
       Professor.id;
    ````
    
    
    
    
    
    
       Select Subjects.id, Code, Duration From Course INNER JOIN Subjects ON
      Course.Subject_id =
     Subjects.id;
     ````

    
    
    
    Select Subjects.id, Name, Code, Duration, F_Name, L_Name From Course INNER JOIN Subjects ON Course.Subject_id = Subjects.id INNER JOIN Professor ON Course.Professor_id = Professor.id;

    
    
    
    select Student.id , F_Name , L_Name , Address.Governorate , city from Student_Address INNER JOIN Student ON Student_Address.Student_id = Student.id INNER JOIN Address ON Student_Address.Address_id = Address.id ;

    
    
    select Student.id , F_Name , L_Name , Course.Duration from Course_Enrolment INNER JOIN Student ON Course_Enrolment.Student_id = Student.id INNER JOIN Course ON Course_Enrolment.Course_id = Course.id ;

    
    
  
  

    
