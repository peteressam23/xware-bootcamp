# Exercise
- Using College Management System Database With Joins
- Select Subject id, Subject Name, Subject Code, Course Duration in One Query
- Select Subject id, Subject Name, Subject Code, Course Duration, Professor First_name, Professor Last_name, in One Query
- Select All Students With Thier Address In one Query
- Select All Student Name In Every Couse.
____________________________________________________________________________________________________________

## Solution
```
SELECT Subject.id, Code, Duration From Course INNER JOIN Subject ON Course.Subject_id = Subject.id ;
 
SELECT Subject.id, Name, Code, Duration, F_Name, L_Name From Course INNER JOIN Subject ON Course.Subject_id = Subject.id INNER JOIN Professor ON Course.Professor_id = Professor.id;


SELECT Student.id , F_Name , L_Name ,F_Phone , L_Phone ,Birth_Date , Image , 
Address.Governorate , City , line_1Address, line_2Address from Student_Address 
INNER JOIN Student ON Student_Address.Student_id = Student.id
 INNER JOIN Address ON Student_Address.Address_id = Address.id ;


SELECT Student.id , F_Name , L_Name , L_Phone , Birth_Date , Image ,
Course.Duration , Subject_id , Professor_id from Course_Enrolment
 INNER JOIN Student ON Course_Enrolment.Student_id = Student.id 
 INNER JOIN Course ON Course_Enrolment.Course_id = Course.id ;

```
__________________________________________________________________________________________________
