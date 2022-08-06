


# Exercises
- Using The Previous Program, Split The Program Into
- Main File Called main.py That Intialize The Program
- Module Called college, That Will Have All The Functionality Of The College Management System, This Module Will Have Several Files
- Fuculity.py file Which Will Have All Functions Related To:
 Creating Faculty
Reading Faculty Info
Update Faculty Info
Link Professors To Faculty
Link Departments To Faculty
- Department.py file Which Will Have All Functions Related To:
Creating Department
Reading All Departments Info
Reading Specific Department Info
Update Specific Department Info
- Subject.py file Which Will Have All Functions Related To:
Creating Subject
Reading All Subjects Info
Reading Specific Subject Info
Update Specific Subject Info
Link Course To Subject
Link Professor To Subject
- Course.py file Which Will Have All Functions Related To:
Creating Course
Reading All Courses Info
Reading Specific Course Info
Update Specific Course Info
Link Professor To Course
Link Exams To Course
- Exams.py file Which Will Have All Functions Related To:
Creating Exams
Reading All Exams Info
Reading Specific Exam Info
Update Specific Exam Info
- Student.py file Which Will Have All Functions Related To:
Creating Student
Reading All Students Info
Reading Specific Student Info
Update Specific Student Info
- Professor.py
Creating Professor
Reading All Professor Info
Reading Specific Professor Info
Update Specific Professor Info








## solution
```
list_Faculty =[]
list_Depar = []
list_Subje = []
list_Cour = []
list_Exa = []

def Creating_Faculty():
    
    
    while True:
        try:
            Faculty ={}
            Id = int(input("Enter Id Of Your Faculty: "  ))
            F_Name = input("Enter The Name Of Your Faculty: ")
            Faculty['Id']    = Id
            Faculty['F_Name']= F_Name 
            list_Faculty.append(Faculty)   
            print()
            print() 
    
            break
        
            print()
            print()  

        except:
            
             print("Please Enter Valid Integer Id")



def Reading_Faculty_Info():
    print("This Is All Data You Added About Faculities")
    print()
    for element in list_Faculty:
        print('Faculty Id: ' + str(element['Id']))
        print('Faculty Name Has Id '+str(element['Id'])+": " + element['F_Name'])



def Update_Faculty_Info():
    num = int(input("Enter Number Of Faculity Want To Update: "))
    update={}

    Id = int(input("Enter Id Of Your Faculty: "  ))
    F_Name = input("Enter The Name Of Your Faculty: ")

    update['Id']    = Id
    update['F_Name']= F_Name 

    list_Faculty[num-1] = update 




def Creating_Department():
        
    while True:
        try:
            Department ={}
            Id = int(input("Enter Id Of Your Department: "  ))
            D_Name = input("Enter The Name Of Your Department: ")
            P_Id = int(input("Enter Id Of professor In This Department: "  ))
            Department['Id']    = Id
            Department['D_Name']= D_Name 
            Department['P_Id']= P_Id 
            list_Depar.append(Department)   
            print()
            print() 
    
            break
        
            print()
            print()  

        except:
            
             print("Please Enter Valid Integer Id")



    
  

def Reading_All_Department_Info():
    print("This Is All Data You Added About Department")
    print()
    for element in list_Depar:
        print('Department Id: ' + str(element['Id']))
        print('Department Name Has Id '+str(element['Id'])+": " + element['D_Name'])
        print('Professor Id In '+ element['D_Name'] + ' Department : ' +str(element['P_Id']))






def Reading_Specific_Department_Info():

    num = int(input('Enter Number Of Specific Department To see Info: '))
    dep = list_Depar[num -1]
    for key, value in dep.items():
        print('Department ' + key + ': ' + str(value))



def Update_Department():          
       
    num = int(input("Enter Number Of Depatrtment Want To Update: "))
    update={}
    Id = int(input("Enter Id Of Your Department: "  ))
    D_Name = input("Enter The Name Of Your Department: ")
    P_Id = int(input("Enter Id Of professor In This Department: "  ))

    update['Id']    = Id
    update['D_Name']= D_Name 
    update['P_Id']= P_Id 

    list_Depar[num-1] = update 










def Creating_Subjects():
    while True:
        try:
            Subjects ={}
            Id = int(input("Enter Id Of Your Subject: "  ))
            S_Name = input("Enter The Name Of Your Subject: ")
            Code = input("Enter Subject Code: "  )
            Subjects['Id']    = Id
            Subjects['S_Name']= S_Name 
            Subjects['Code']= Code 
            list_Subje.append(Subjects)   
            print()
            print() 
    
            break
        
            print()
            print()  

        except:
            
             print("Please Enter Valid Integer Id")






def Reading_Subject_Info():
    print("This Is All Data You Added About Subjects")
    print()
    for element in list_Subje:
        print('Subject Id: ' + str(element['Id']))
        print('Subject Name Has Id '+str(element['Id'])+": " + element['S_Name'])
        print('Subject Code : ' + element['Code'])




def Reading_Specific_Subject_Info():

    num = int(input('Enter Number Of Specific Subject To see Info: '))
    sub = list_Subje[num -1]
    for key, value in sub.items():
        print('Subject ' + key + ': ' + str(value))





def Update_Subjects():          
       
    num = int(input("Enter Number Of Subject Want To Update: "))
    update={}
    Id = int(input("Enter Id Of Your Subject: "  ))
    S_Name = input("Enter The Name Of Your Subject: ")
    Code = input("Enter Subject Code: "  )

    update['Id']    = Id
    update['S_Name']= S_Name 
    update['Code']= Code 

    list_Subje[num-1] = update 










def Creating_Course():
    while True:
        try:
            Courses ={}
            Id = int(input("Enter Id Of Your Course: "  ))
            Duration = input("Enter The Duration Of Your Course: ")
            
            Courses['Id']    = Id
            Courses['Duration']= Duration 
            
            list_Cour.append(Courses)   
            print()
            print() 
    
            break
        
            print()
            print()  

        except:
            
             print("Please Enter Valid Integer Id")






def Reading_Course_Info():
    print("This Is All Data You Added About Courses")
    print()
    for element in list_Cour:
        print('Course Id: ' + str(element['Id']))
        print('Course Duration : ' + element['Duration'])



def Reading_Specific_Course__Info():

    num = int(input('Enter Number Of Specific Course To see Info: '))
    cour = list_Cour[num -1]
    for key, value in cour.items():
        print('Course ' + key + ': ' + str(value))




def Update_Cousre():
    num = int(input("Enter Number Of Course Want To Update: "))
    update={}
    Id = int(input("Enter Id Of Your Course: "  ))
    Duration = input("Enter The Duration Of Your Course: ")
   

    update['Id']    = Id
    update['Duration']= Duration 
  
    list_Cour[num-1] = update 








def Creating_Exames():
    while True:
        try:
            Exames ={}
            Id = int(input("Enter Id Of Your Exame: "  ))
            Date = input("Enter The Date Your Exame: ")
            Time = input("Enter The Time Of Your Exame: ")
            Duration = input("Enter The Duration Of Your Exame: ")
            
            Exames['Id']    = Id
            Exames['Date']= Date 
            Exames['Time']= Time 
            Exames['Duration']= Duration 
            
            list_Exa.append(Exames)   
            print()
            print() 
    
            break
        
            print()
            print()  

        except:
            
             print("Please Enter Valid Integer Id")






def Reading_Exames_Info():
    print("This Is All Data You Added About Exames")
    print()
    for element in list_Exa:
        print('Exame Id : ' + str(element['Id']))
        print('Exame Num  ' + str(element['Id']) + ' Date : ' + element['Date'])
        print('Exame Num  ' + str(element['Id']) + ' Time : ' + element['Time'])
        print('Exame Num  ' + str(element['Id']) + ' Duration : ' + element['Duration'])




def Reading_Specific_Exame__Info():

    num = int(input('Enter Number Of Specific Exame To see Info: '))
    Exa = list_Exa[num -1]
    for key, value in Exa.items():
        print('Exame ' + key + ': ' + str(value))




def Update_Exame():
    num = int(input("Enter Number Of Exame Want To Update: "))
    update={}

    Id = int(input("Enter Id Of Your Exame: "  ))
    Date = input("Enter The Date Your Exame: ")
    Time = input("Enter The Time Of Your Exame: ")
    Duration = input("Enter The Duration Of Your Exame: ")

    update['Id']    = Id
    update['Date']= Date 
    update['Time']= Time 
    update['Duration']= Duration 

  
    list_Exa[num-1] = update 

















################################### ##############################################################



while True:
    print("For Facilities Functionalities Enter 1")
    print("For Department Functionalities Enter 2")
    print("For Subjects Functionalities Enter 3")
    print("For Courses Functionalities Enter 4")
    print("For Exams Functionalities Enter 5")
    print("For Students Functionalities Enter 6")
    print("For Department Functionalities Enter 7")
    
    print()
    print()

    num_of_choice = int(input("Enter Your Choice: "))

    if num_of_choice == 1:
        while True:

            print()
            print()

            print("For Creating Faculty Data Base Enter 1")
            print("For Reading Faculty  Info Enter 2")
            print("For Update Faculty Info Enter 3")
            print("To Know Professors In Any Faculty Enter 4")
            print("To Know Department In Faculty Enter 5")
            print("To End Faculity Functionalities Enter 6")


            print()
            print()

            num_choice_For_Faculty = int(input("Enter Your Choice: "))
           

            print()
            print()  

            if num_choice_For_Faculty == 1:
                Creating_Faculty()

            elif num_choice_For_Faculty == 2:
                Reading_Faculty_Info() 

            elif num_choice_For_Faculty == 3:
                Update_Faculty_Info()  

            else:
                break      



    elif num_of_choice == 2:
        while True:

            print()
            print()

            print("For Creating Department Data Base Enter 1")
            print("For Reading Department  Info Enter 2")
            print("For Reading Specific Department  Info Enter 3")
            print("For Update Specific Department  Enter 4")
            print("For End Department Functionalities Enter 5")


            print()
            print()

            num_Choice_For_Depart = int(input("Enter Your Choice: "))

            print()
            print() 


            if num_Choice_For_Depart== 1:
                Creating_Department()

            elif num_Choice_For_Depart == 2:
                Reading_All_Department_Info()

            elif num_Choice_For_Depart == 3:
                Reading_Specific_Department_Info()  

            elif num_Choice_For_Depart == 4:
                Update_Department()  
    

            else:
                break   


    elif num_of_choice == 3:

        while True:

            print()
            print()

            print("For Creating Subjects Data Base Enter 1")
            print("For Reading Subjects  Info Enter 2")
            print("For Reading Specific Subject  Info Enter 3")
            print("For Update Specific Department  Enter 4")
            print("For End Department Functionalities Enter 5")


            print()
            print()

            num_Choice_For_Subj = int(input("Enter Your Choice: "))

            print()
            print() 


            if num_Choice_For_Subj== 1:
                Creating_Subjects()

            elif num_Choice_For_Subj == 2:
                Reading_Subject_Info()

            elif num_Choice_For_Subj == 3:
                Reading_Specific_Subject_Info()  

            elif num_Choice_For_Subj == 4:
                Update_Subjects()  
    

            else:
                break   


    elif num_of_choice == 4:

        while True:

            print()
            print()

            print("For Creating Courses Data Base Enter 1")
            print("For Reading Course  Info Enter 2")
            print("For Reading Specific Course  Info Enter 3")
            print("For Update Specific Course  Enter 4")
            print("For End Courses Functionalities Enter 5")


            print()
            print()

            num_Choice_For_Cour = int(input("Enter Your Choice: "))

            print()
            print() 


            if num_Choice_For_Cour== 1:
                Creating_Course()

            elif num_Choice_For_Cour == 2:
                Reading_Course_Info()

            elif num_Choice_For_Cour == 3:
                Reading_Specific_Course__Info()  

            elif num_Choice_For_Cour == 4:
                Update_Cousre()  
    

            else:
                break          


    elif num_of_choice == 5:

        while True:

            print()
            print()

            print("For Creating Exames Data Base Enter 1")
            print("For Reading Exames  Info Enter 2")
            print("For Reading Specific Exame  Info Enter 3")
            print("For Update Specific Exame  Enter 4")
            print("For End Exames Functionalities Enter 5")


            print()
            print()

            num_Choice_For_Exame = int(input("Enter Your Choice: "))

            print()
            print() 


            if num_Choice_For_Exame== 1:
                Creating_Exames()

            elif num_Choice_For_Exame == 2:
                Reading_Exames_Info()

            elif num_Choice_For_Exame == 3:
                Reading_Specific_Exame__Info()  

            elif num_Choice_For_Exame == 4:
                Update_Exame()  
    

            else:
                break          

```
___________________________________________________________________________________________________
    


