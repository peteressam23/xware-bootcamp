# Exercise - IN Python:
- Install python3 if not installed
- Install pip3 if not installed
- Implement College Management System Database Using CLI.
- The Program Should Be Able To Do These.
- Print Welcome Message To Screen
- Input Faculty Info Like This:
 Please Enter Faculty Name: Then User Can Input The Name
- Input Departments Number
How Many Department in The Faculty: Then User Can Enter Number.
For Every Department User Can Enter It's Info.
- Input Professor Number
Please Enter Professor Number Then User Can Enter Number.
Input Professor Info
Think How Can We Link The Professor With The Departments.
- Input Students Number
Please Enter Student Number Then User Can Enter Number.
Input Every Student Info
Think How Can We Link The Students With The Faculty.
- Input Subjects Number
Please Enter Subjects Number: Then User Can Enter Number.
Input Subjects Info
Think How Can We Link The Subjects With The Department ?
- Input Courses Number
Please Enter Courses Number: Then User Can Enter Number.
Input Courses Info
Think How Can We Link The Professors With The Course ?
Think How Can We Link The Course With The Subject ?
Think How Can We Link The Students With The Course ?
- Input Exams Number
Please Enter Exams Number: Then User Can Enter Number.
Input Exams Info
- After All Of This The Program Should Print The Info In Neat Mannaer
- Then Exit With This String "Made With Love By ( XWARE BOOT CAMP )." in It's New Line

___________________________________________________________________________________________________

## Code
```
Faculty_Name = input("Please Enter Faculty Name : " )


Department_Num = int(input("Please Enter The Number of Departments in Your Faculty: " ))
Dep_All_Information = []
for i in range (Department_Num) :
    Department_Name = input("Enter Department name  " + str(1 + i)  + " :"  )
    Department_ID   = input("Enter Department ID  " + str(1 + i)  + " :"  )

    Dep_All_Information.append([Department_Name , Department_ID])
    

print(Dep_All_Information) 



Professors = dict()
Professor_Num = int(input("Enter Number of Professors :"))
Professor_info = []
for i in range(Professor_Num):
        P_ID         = input("Enter Id of Professor " + str (i+1) + " : ")
        P_F_name     = input("Enter F_Name of Professor "+ str (i+1) + " : ")
        P_L_Name     = input("Enter L_Name of Professor "+ str (i+1) + " : " )
        P_Age        = input("Enter Professor Age "+ str (i+1) + " : ")
        P_Salary     = int(input("Enter Professor Salary "+ str (i+1) + " : " ))
        P_Department = input ("Enter Professor Department ID of Professor Number "+ str (i+1) + " : ")

        Professor_info.append([P_F_name , P_L_Name , P_Age , P_Salary , P_Department])
        Professors[P_ID] = Professor_info


print(Professors)




Students = dict()
Student_Num = int(input("Enter Number of Students :"))
Student_info=[]
for i in range(Student_Num):
        S_ID         = input("Enter Id of Student " + str (i+1) + " : ")
        S_F_name     = input("Enter F_Name of Student "+ str (i+1) + " : ")
        S_L_Name     = input("Enter L_Name of Student "+ str (i+1) + " : " )
        S_F_Phone    = input("Enter F_Phone of Student "+ str (i+1) + " : " )
        S_L_Phone    = input("Enter L_Phone of Student "+ str (i+1) + " : " )
        S_Birth_date = input("Enter Birth_Date of Student "+ str (i+1) + " : " )
        Faculty      = input ("Enter faculty Name of student "+ str (i+1) + " : ")

        Student_info.append([S_F_name , S_L_Name , S_F_Phone , S_L_Phone , S_Birth_date , Faculty])
        Students[S_ID] = Student_info


print (Students)



Subjects = dict()
Subjects_Num = int(input("Enter Number of Stubjects :"))
Subjects_info=[]
for i in range(Subjects_Num):
        Sub_ID             = input("Enter Id of Stubject " + str (i+1) + " : ")
        Sub_Name           = input("Enter Name of Stubject "+ str (i+1) + " : ")
        Sub_Code           = input("Enter The Code of Subject "+ str (i+1) + " : " )
        Sub_In_Department  = input ("Enter ID Of Department belong to Subject Num  "+ str (i+1) + " : ")
       
        Subjects_info.append([Sub_Name , Sub_Code , Sub_In_Department ])
        Subjects[Sub_ID] = Subjects_info


print (Subjects)



Courses = dict()
Courses_Num = int(input("Enter Number of Courses :"))
Courses_info=[]
for i in range(Courses_Num):
        C_ID               = input("Enter Id of Course " + str (i+1) + " : ")
        C_Duration         = input("Enter Duration of Course "+ str (i+1) + " : ")
        P_Course_ID        = input ("Enter Professor Course ID of Professor Number "+ str (i+1) + " : ")
        Sub_Course_ID      = input("Enter Id of Stubject Belong To This Course " + str (i+1) + " : ")
        Dep_Course_ID    = input ("Enter ID Of Department belong to Course Num  "+ str (i+1) + " : ")

        
        Courses_info.append([C_Duration , P_Course_ID  , Sub_Course_ID , Dep_Course_ID])
        Courses[C_ID] = Courses_info


print (Courses)


Exames = dict()
Exames_Num = int(input("Enter Number of Exames :"))
Exames_info=[]
for i in range(Exames_Num):
        E_ID               = input("Enter Id of Exame " + str (i+1) + " : ")
        E_Duration         = input("Enter Duration of Exame "+ str (i+1) + " : ")
        E_Date             = input ("Enter Date Of Exame "+ str (i+1) + " : ")
        Sub_Exame_ID      = input("Enter Id of Stubject Belong To This Exame " + str (i+1) + " : ")
        

        
        Exames_info.append([E_Duration , E_Date  , Sub_Exame_ID ])
        Exames[E_ID] = Exames_info


print (Exames)



print(Dep_All_Information) 
print(Professors)
print (Students)
print (Subjects)
print (Courses)
print (Exames)

```
