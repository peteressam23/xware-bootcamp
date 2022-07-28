
# College Data Data_Base

```

create table if not exists Faculty(
	id serial primary key ,
    name varchar(60) not null default 'Faculty'
);

create table if not exists Departement(
	id serial primary key ,
    name varchar(60) not null default 'Departement',
	
	
	Faculty_id int references Faculty (id)
);

create table if not exists Address(
	
    id serial primary key ,
	Governorate varchar(60)  null default 'Governorate',
    City varchar(60) null default 'City',
	line_1Address varchar(80)  null default 'Line_1',
	line_2Address varchar(80)  null default 'Line_2'
);

create table if not exists Student(

	
	id serial primary key,
	F_Name varchar(40) not null default 'F_Name',
	L_Name varchar(40) not null default 'L_Name',
	
	F_Phone int not null,
	L_Phone int not null,
	
	Birth_Date int not null,
	Image bytea null default 'Image'

);

ALTER TABLE Student DROP F_Phone;
ALTER TABLE Student DROP L_Phone;


create table if not exists Student_Phone(
	id serial primary key,
	F_Phone int not null,
	L_Phone int not null,
	
	Student_id int references Student(id)
);





create table if not exists Student_Address(
	id serial primary key,	

	Address_id int references Address (id),
	Student_id int references Student (id)
	
);


create table if not exists Professor(
	id serial primary key,
	
	F_Name varchar(40) not null default 'F_Name',
	L_Name varchar(40) not null default 'L_Name',
	Age int not null,
	Salary int not null,
	Image bytea null default 'Image',
	
	
	Faculty_id int references Faculty (id),
	Departement_id int references Departement (id)
	
);



ALTER TABLE Professor DROP F_Name;
ALTER TABLE Professor DROP L_Name;


create table if not exists Professor_Name(
	id serial primary key,
	F_Name varchar(40),
	L_Name varchar(40),
	
	Professor_id int references Professor(id)
);


create table if not exists Subject(
	id serial primary key,
	Name varchar(60) not null default 'Sub_Name',
	Code varchar(40) not null unique default 'Sub_Code',
	
	Faculty_id int references Faculty (id)
);



create table if not exists Course(
	id serial primary key,
	Duration int not null,
	
	Subject_id int references Subject (id),
	Professor_id int references Professor (id)
		
);

create table if not exists Course_Enrolment(
	id serial primary key,
	
	Course_id int references Course (id),
	Student_id int references Student (id)
);



create table if not exists Exams(
	id serial primary key,
	Date_Exam int not null,
	Time_Exam int not null,
	Duration int not null,
	
	Course_id int references Course (id)
);

/*Operations ON Data_Base*/

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
	
	
/*Trasaction*/	
	
	
begin ;

SELECt *from Faculty;
SELECT * from Departement;

INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id , Departement_id)
VALUES('Beshoy', 'Hany', 56 , 500000 , 'Not Have Image', 1 , 1);

INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUES
('Ahmed' , 'Omar' , 0100005555 , 0122258663 , 8-8-2008 , 'Not Have Image');

SELECT * from Professor;
SELECT * from Student;

DELETE FROM Professor where Salary > 20000 ;

ROllback;

begin ;

INSERT INTO Professor(F_Name, L_Name, Age, Salary, Image , Faculty_id ,  Departement_id)
VALUES('Fady', 'Botros', 25, 250000 , 'Not Have Image' , 1 , 2);

INSERT INTO Student (F_Name , L_Name , F_Phone , L_Phone , Birth_Date , Image) VALUEs 
('Bebo' , 'Osama' , 0100005555 , 0122258663 , 2008 , 'Not Have Image');
   
   
commit ;   


/*Join*/

SELECT Subject.id, Code, Duration From Course INNER JOIN Subject ON Course.Subject_id = Subject.id ;
 
SELECT Subject.id, Name, Code, Duration, F_Name, L_Name From Course INNER JOIN Subject ON Course.Subject_id = Subject.id INNER JOIN Professor ON Course.Professor_id = Professor.id;


SELECT Student.id , F_Name , L_Name ,F_Phone , L_Phone ,Birth_Date , Image , 
Address.Governorate , City , line_1Address, line_2Address from Student_Address INNER JOIN Student ON Student_Address.Student_id = Student.id INNER JOIN Address ON Student_Address.Address_id = Address.id ;


SELECT Student.id , F_Name , L_Name , L_Phone , Birth_Date , Image ,
Course.Duration , Subject_id , Professor_id from Course_Enrolment INNER JOIN Student ON Course_Enrolment.Student_id = Student.id INNER JOIN Course ON Course_Enrolment.Course_id = Course.id ;



```
