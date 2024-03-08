# my-project-
project python
class Person:
    faculty= "English commerce"
    semester= "second semester"
    year= 2023
    def _init_ (self, name, NID, phone, program):
         self.name = name
         self.__NID = NID
         self.phone = phone
         self.program = program
    def print_account_details (self):
        print (f"Name:  {self.name}")
        print(f"NID:  {self.__NID}")
        print(f"Phone:  {self.phone}")
        print(f"Program:  {self.program}")
class Doctor(Person):
    def __init__(self, name, NID, phone, program, doctor_code, course, salary, hours_worked=0):
        super().__init__(name, NID, phone, program)
        self.doctor_code = doctor_code
        self.course = course
        self.salary = salary
        self.hours_worked = hours_worked = 0
    def account_creation(self):
        code=int(input("Enter your code"))
        password=input("Enter your password")
        print("Account is created successfully")
    def print_account_details(self):
        super().print_account_details()
        print(f"Faculty of {Person.faculty}")
        print(f"{Person.semester}")
        print(f"Year: {Person.year}")
        print(f"Doctor code: {self.doctor_code}")
        print(f"Course: {self.course}")
        print(f"Salary:  {self.salary}")
        print(f"Hours worked: {self.hours_worked}")
    def check_course(self):
        print(f"Course: {self.course}")
    def change_course(self, new_course):
        self.course= new_course
        print(f"The course changed to {self.course}")
    def check_hours_worked(self):
        print(f"Hours worked: {self.hours_worked}")
    def check_salary(self):
        if self.hours_worked >30:
            overtime= self.hours_worked-30
            overtime_amount= overtime * (self.salary/30)
            total_salary= self.salary + overtime_amount
        else:
            total_salary=self.salary
            print(f"salary: {total_salary}")
    def add_hours_worked(self,hours):
        self.hours_worked=self.hours_worked +hours
        print(f"updated worked hours: {self.hours_worked}")
    def logout(self):
        print("logged out successfully. \n Thank you")
class Student(Person):
    def __init__(self, name, NID, phone, program, student_ID, university_email):
        super().__init__(name, NID, phone, program)
        self.student_ID = student_ID
        self.university_email = university_email
    def account_creation(self):
        code=int(input("Enter your code"))
        password=input("Enter your password")
        print("Account is created successfully")
    def print_account_details(self):
        super().print_account_details()
        print(f"Faculty of {Person.faculty}")
        print(f"{Person.semester} ")
        print(f"Year: {Person.year}")
        print(f"Student ID: {self.student_ID}")
        print(f"University email: {self.university_email}")
    def check_national_ID(self):
        print(f"NID: {self._Person__NID}")
    def change_national_ID(self,new_NID):
        self._Person__NID=new_NID
        print(f"your new NID: {self._Person__NID}")
    def logout(self):
        print("logged out successfully. \n Thank you")
system_type=int(input("\n\t\t please, select to login to the Doctor system or the Student system.\n Enter 1 for Doctor system or 2 for Student system "))
if system_type == 1:
    print("      Welcome to Doctor system      ")
    doc= Doctor("Engy Yehia", "1273", "01098765432","BIS", 1234,"Programming 2", 6500)
    doc.account_creation()
    doc.print_account_details()
    doc.check_course()
    doc.change_course("Database")
    doc.check_hours_worked()
    doc.check_salary()
    doc.add_hours_worked(38)
    doc.logout()
else:
    print("     Welcome to Student system     ")
    student=Student("Alaa Sami","30212120103123","0117467826","BIS",2122014,"Alaa.Sami.2122014@commerce.helwan.edu")
    student.account_creation()
    student.print_account_details()
    student.check_national_ID()
    student.change_national_ID("520849493742")
    student.logout()
