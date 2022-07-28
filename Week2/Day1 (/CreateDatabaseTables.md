## Exercise 
* Create ER diagram For The College Management System With following Tables
    * `Faculty` Table With These attributes:
        * `F_id:` Faculty id
        * `F_name:` Faculty Name
    * `Department` Table With These attributes:
        * `D_id:` id
        * `D_Name` Name
        * `F_id` Faculty id
    * `Address` Table With These attributes
        * `A_id` Address id
        * `Gvernorate` Gvernorate
        * `City` City
        * `line_1` Address Line 1 (Required)
        * `line_2` Address Line 2 (Optional)
    * `Student_Address` Table With These attributes
        * `Stu_A_id` id
        * `A_id` Address id
        * `Stu_id` Student id
    * `Student` Table With These attributes
        * `Stu_id` id
        * `F_Name` First Name
        * `L_Name` Last Name
        * `F_Phone` First Phone
        * `L_Phone` Last Phone
        * `Birth_Date` Birth Date
        * `image` Student Image
    * `Professor` Table With These attributes
        * `P_id` id
        * `F_id` Faculty id
        * `D_id` Department id
        * `F_name` First Name
        * `L_Name` Last Name
        * `age` Age
        * `Salary` Salary
        * `image` Student Image
    * `Subjects` Table With These attributes
        * `Sub_id` id
        * `Sub_name` Name
        * `Sub_code` Code (Unique)
        * `F_id` Faculty id
    * `Course` Table With These attributes
        * `C_id` id
        * `Sub_id` Sub_id
        * `Duration` Duration
        * `P_id` Professor id
    * `Course_Enrolment` Table With These attributes
        * `C_E_id` id
        * `C_id` Course id
        * `Stu_id` Student id
    * `Exams` Table With These attributes
        * `E_id` id
        * `C_id` Course id
        * `Date` Exam Date
        * `Time` Exam Time
        * `Duration` Exam Duration

 ________________________________________________________________________________

 ## Solution (Create Tables)       

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

```

_______________________________________________________________________________


