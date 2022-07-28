# Exercise 

- Try To Normalize Student, Professor Table in College Management System. How de we do that?

___________________________________________________________________________________________________

## Solution

```



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

INSERT INTO Student_Phone (F_Phone , L_Phone , Student_id) VALUEs (16106662 ,5521,1) , (555323, 5633, 2);

INSERT INTO Professor_Name(F_Name , L_Name , Professor_id) VALUEs ('karem' , 'sayed', 1) , ('Mamdoh' , 'Fathy' , 2);

select Student.id , F_Name , L_Name , Birth_Date , Image , Student_phone.id AS IDSP , F_Phone , L_Phone from Student_Phone FULL OUTER JOIN Student ON Student_Phone.Student_id = Student.id ;

select Professor.id , Age ,Salary , , Image , Professor_Name.id AS IDPN , F_Name , L_Name from Professor_Name FULL OUTER JOIN Professor ON Professor_Name.Professor_id = Professor.id ;
