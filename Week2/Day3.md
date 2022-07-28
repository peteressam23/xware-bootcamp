

# Solution Exercise 1 (Normalize)

## Student, Professor Tables In My Data Base with making  Normalize 

```
create table if not exists Student(


id serial primary key,
F_Name varchar(40) not null default 'F_Name',
L_Name varchar(40) not null default 'L_Name',

F_Phone int not null,
L_Phone int not null,

Birth_Date int not null,
Image bytea not null default 'Image'

 );
 ```
_______________________________________________________________________________
 
 ```
create table if not exists Student_Phone(
id serial primary key ,
F_Phone int not null,
L_Phone int not null,

Student_id int references Student (id)
);
```
_______________________________________________________________________________

```
 ALTER TABLE Student DROP F_Phone;
 ALTER TABLE Student DROP L_Phone;
    
```
_______________________________________________________________________________   
   

```
create table if not exists Professor(
id serial primary key,
F_Name varchar(40) not null default 'F_Name',
L_Name varchar(40) not null default 'L_Name',
Age int not null,
Salary int not null,
Image bytea not null default 'Image',


Faculty_id int references Faculty (id),
Departement_id int references Departement (id)

);
```

________________________________________________________________________________
  
  ```
   ALTER TABLE Professor ADD Salary int ;       //this is because i make drop by mistake
   ALTER TABLE Professor ADD Image Bytea ;     //this is because i make drop by mistake
  ```
_________________________________________________________________________________  

 ```
create table if not exists Professor_Name(
id serial primary key,
F_Name varchar(40) not null default 'F_Name',
L_Name varchar(40) not null default 'L_Name',

Professor_id int references Professor (id)
);

```
_______________________________________________________________________________

```
   ALTER TABLE Professor DROP F_Name;
   ALTER TABLE Professor DROP L_Name;

```
_________________________________________________________________________________   

## Insert Data

```

INSERT INTO Student_Phone (F_Phone , L_Phone , Student_id) VALUEs (0106662 ,5521,1) , (555323, 5633, 2);

INSERT INTO Professor_Name(F_Name , L_Name , Professor_id) VALUEs ('karem' , 'sayed', 1) , ('Mamdoh' , 'Fathy' , 2);

select Student.id , F_Name , L_Name , Birth_Date , Image , Student_phone.id AS PP , F_Phone , L_Phone from Student_Phone FULL OUTER JOIN Student ON Student_Phone.Student_id = Student.id ;

select Professor.id , Age ,Salary , , Image , Professor_Name.id AS PP , F_Name , L_Name from Professor_Name FULL OUTER JOIN Professor ON Professor_Name.Professor_id = Professor.id ;

```
___________________________________________________________________________________

# Solution Ecercis 2 


`INSERT INTO Person (PersonId ,first_name , last_name) VALUEs (1,'Allen' , 'Wang') ,(2 , 'Bob' , 'Alice');`

`INSERT INTO Address (Address_Id , city , state , person_Id) VALUEs (1, 'New york City','New york' , 2) ,(2 , 'Leetcode' , 'california' , 1);`

`select Person.personId , last_name , first_name , Address.address_Id , city , state from Address FULL OUTER JOIN Person ON Address.person_Id = Person.personId ;`
