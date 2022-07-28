


# Exercise 

- Create a SQL database for the Above ER diagram.
- Insert Data Into These Tables.
- Insert One Faculty
- Insert Three Departments Into This Faculty
- Insert Three Subjects In Every Department
- Insert Courses With Defferent Durations
- Insert Atleast Five Students In Every Department
- Insert Exams For Every Course
- Select Data From Thse Tables.
- Select all Students, Professor, Subjects, Courses, Exams, Departments
- Select all Professors with the Age is 40
- Select all Professors with the salary greater than 10000
- Order the Professors by the salary
- Order the students by the Birth_Date
- Get the average salary of the Professors
- Update the salary of the Professors with the salary greater than 10000 to 20000
- Delete the Professors with the salary greater than 20000
- Update These Tables
- Set Students Line 2
- Add Age Column in Student Table
- Set Students Age
- Check All Exams Have Different Date And Time And If So Change These So Every Exam Have Different Date And Time


_______________________________________________________________________________
## solution

```
INSERT INTO Faculty(name) VALUES('Computers and Information Technology');

INSERT INTO Departement(name, Faculty_id) VALUES('CS', 1), ('IS', 1), ('IT',1);

Insert Into Address(Governorate, City, Line_1Address, Line_2Address)
	   Values('Cairo', 'Giza', 'Faisal', 'Not HAve');
	   
INSERT INTO Student(F_Name, L_Name, F_Phone, L_Phone, Birth_Date, Image)
	   VALUES('Peter', 'Essam', 01097968890, 01097968806, 1-1-1999, 'No Have Image');
	  
INSERT INTO Student(F_Name, L_Name, F_Phone, L_Phone, Birth_Date, Image)
	   VALUES('Mahmoud', 'Omar', 0103365, 01036782 , 4-8-1970, 'No Have ImageNo Have Image'),
	   		 ('Khaled', 'Mustafa', 01236587, 011235882, 7-3-1988, 'No Have Image'),
			 ('Abdelrahman', 'Tarek', 01236587, 01236587, 8-8-1992, 'No Have Image');
			
INSERT INTO Student(F_Name, L_Name, F_Phone, L_Phone, Birth_Date, Image)
	   VALUES('Mustafa', 'Mahmoud', 012564321, 010654962, 5-5-1995, 'No Have Image');
			
INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image)
	   VALUES('Karem', 'Mousa', 25, 5000.0, 'No Have Image');
	   
INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image)
	   VALUES('Tarek', 'Mahmoud', 40 , 20000.0 , 'No Have Image'), ('Salah', 'Ali', 37, 15000.0 , 'No Have Image'),
	         ('Zain', 'Ahmed', 45, 30000.0 , 'No Have Image'), ('Omar', 'Fakhry', 47, 35000.0 , 'No Have Image');
			 
INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image)
	   VALUES('Hosny', 'Hassan', 42, 35000.0, 'No Have Image');

INSERT INTO Subject(Name, Code, Faculty_id)
		VALUES('Programming Language', 'swe1', 1 ), ('Algorithms and DS', 'swe2', 1),
		('Software Engineering', 'swe3', 1), ('Mathematics', 'swe4', 1),
		('Business computer applications', 'swe5', 1),
		('Information and internet technology', 'swe6', 1),
		('Networking', 'swe7', 1), ('Computer Graphics and Multimedia', 'swe8', 1),
		('Data Mining', 'swe9', 1);
		
INSERT INTO Student_Address(Address_id, Student_id)
		VALUES(1,1);

INSERT INTO Course(Duration, Subject_id, Professor_id)
		VALUES(2, 1, 1), (2, 2, 2), (3,3,3), (2,4,4), (6,5,5);
		
INSERT INTO Course_Enrolment(Course_id, Student_id)
	   VALUES(1,1), (2,2), (3,3), (4,4), (5,5);
	  
INSERT INTO Exams(Date_Exam, Time_Exam, Duration, Course_id)
	   VALUES(2015, 8, 2, 1), (2016, 8, 2, 2), (2017, 8, 2, 3),
	         (2018, 8, 2, 4), (2019, 8, 2, 5);

SELECT * from Student;
SELECT * from Professor;
SELECT * from Subject;
SELECT * from Course;
SELECT * from Exams;
SELECT * from Departement;
Select * from Professor where Age =40;
SELECT * from Professor where Salary > 10000;
SELECT * from Professor ORDER BY Salary;
SELECT * from Student ORDER BY Birth_Date;
SELECT *, AVG(Salary)
	FROM Professor
	GROUP BY id;
	
UPDATE Professor
	SET Salary = 20000 Where Salary > 10000;
DELETE FROM Professor
	Where Salary > 20000;

ALTER TABLE Student
	ADD COLUMN Age VARCHAR;
	
UPDATE Student
	SET Age =22
	Where id =1;
	
UPDATE Student
	SET Age =22
	Where id =2;
	
UPDATE Student
	SET Age =22
	Where id =3;
	
UPDATE Student
	SET Age =22
	Where id =4;
	
UPDATE Student
	SET Age =22
	Where id =5;
	
UPDATE Exams
	SET Time_Exam = 6
	Where id = 2;
	
UPDATE Exams
	SET Time_Exam = 5
	Where id = 3;
	
UPDATE Exams
	SET Time_Exam = 4
	Where id = 4;
	
UPDATE Exams
	SET Time_Exam = 3
	Where id = 5;

```
_________________________________________________________________________________     
