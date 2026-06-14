Experiment 1: Employee Salary Management System (Long Program)
Problem Statement
Develop a Python program to maintain employee records. Accept Employee ID, Name, Basic Salary and calculate HRA, DA, PF, Gross Salary, and Net Salary.
class Employee:

    def __init__(self, eid, name, basic):
        self.eid = eid
        self.name = name
        self.basic = basic

    def calculate_salary(self):

        hra = self.basic * 0.20
        da = self.basic * 0.10
        pf = self.basic * 0.05

        gross = self.basic + hra + da
        net = gross - pf

        return hra, da, pf, gross, net

    def display(self):

        hra, da, pf, gross, net = self.calculate_salary()

        print("\nEmployee Details")
        print("Employee ID :", self.eid)
        print("Name        :", self.name)
        print("Basic Salary:", self.basic)
        print("HRA         :", hra)
        print("DA          :", da)
        print("PF          :", pf)
        print("Gross Salary:", gross)
        print("Net Salary  :", net)

employees = []

n = int(input("Enter Number of Employees: "))

for i in range(n):

    eid = input("Enter Employee ID: ")
    name = input("Enter Employee Name: ")
    basic = float(input("Enter Basic Salary: "))

    emp = Employee(eid, name, basic)

    employees.append(emp)

for emp in employees:
    emp.display()
________________________________________
Experiment 2
Student Record Management System
Problem Statement
Develop a Student Record Management System using Functions, File Handling, Classes, and Objects.
class Student:

    def __init__(self, roll, name, marks):
        self.roll = roll
        self.name = name
        self.marks = marks

    def percentage(self):
        return sum(self.marks)/len(self.marks)

    def grade(self):

        per = self.percentage()

        if per >= 75:
            return "A"
        elif per >= 60:
            return "B"
        elif per >= 50:
            return "C"
        else:
            return "Fail"

def add_student():

    roll = input("Enter Roll No: ")
    name = input("Enter Name: ")

    marks = []

    for i in range(5):
        m = int(input("Enter Subject Marks: "))
        marks.append(m)

    s = Student(roll, name, marks)

    file = open("student.txt", "a")

    file.write(
        roll + "," +
        name + "," +
        str(s.percentage()) + "," +
        s.grade() + "\n"
    )

    file.close()

    print("Record Added Successfully")

def display_student():

    file = open("student.txt", "r")

    print("\nStudent Records")

    for line in file:
        print(line)

    file.close()

while True:

    print("\n1.Add Student")
    print("2.Display Student")
    print("3.Exit")

    ch = int(input("Enter Choice: "))

    if ch == 1:
        add_student()

    elif ch == 2:
        display_student()

    elif ch == 3:
        break
________________________________________
Experiment 3
Bank Management System (Inheritance + Polymorphism)
Problem Statement
Develop a Bank Management System using Constructor, Inheritance, Class Methods, Static Methods, and Polymorphism.
class Account:

    bank = "State Bank"

    def __init__(self, accno, name, balance):
        self.accno = accno
        self.name = name
        self.balance = balance

    @classmethod
    def bank_info(cls):
        print("Bank Name:", cls.bank)

    @staticmethod
    def welcome():
        print("Welcome To Banking System")

    def display(self):
        print(self.accno, self.name, self.balance)


class SavingAccount(Account):

    def calculate_interest(self):
        return self.balance * 0.04

    def display(self):

        print("\nSaving Account")
        print("Account No :", self.accno)
        print("Name       :", self.name)
        print("Balance    :", self.balance)
        print("Interest   :", self.calculate_interest())


class CurrentAccount(Account):

    def calculate_interest(self):
        return self.balance * 0.02

    def display(self):

        print("\nCurrent Account")
        print("Account No :", self.accno)
        print("Name       :", self.name)
        print("Balance    :", self.balance)
        print("Interest   :", self.calculate_interest())


Account.welcome()
Account.bank_info()

s = SavingAccount(101, "Rahul", 50000)
c = CurrentAccount(102, "Amit", 70000)

s.display()
c.display()

Experiment 4
Problem Statement
Experiment 2: Control Flow (Advanced Prime Number Program)
Problem Statement
Write a Python program to check whether a given number is Prime or Not. The program should:
•	Accept a number from the user. 
•	Validate the input. 
•	Count the total factors of the number. 
•	Display all factors of the number. 
•	Determine whether the number is Prime or Composite. 
•	Allow the user to check multiple numbers using a menu-driven approach. 
Python Program
while True:

    print("\n===== PRIME NUMBER ANALYZER =====")
    print("1. Check Prime Number")
    print("2. Exit")

    choice = int(input("Enter Your Choice: "))

    if choice == 1:

        num = int(input("Enter a Number: "))

        if num <= 1:
            print(num, "is Neither Prime Nor Composite")

        else:

            factors = []
            count = 0

            print("\nFactors of", num, ":")

            for i in range(1, num + 1):

                if num % i == 0:
                    factors.append(i)
                    count += 1

            print(factors)
            print("Total Factors =", count)

            if count == 2:
                print(num, "is a PRIME Number")
            else:
                print(num, "is a COMPOSITE Number")

    elif choice == 2:
        print("Program Terminated")
        break

    else:
        print("Invalid Choice")
________________________________________


Experiment 5
Problem Statement
Write a Python program to demonstrate inheritance using Student and Result classes.
Program
class Student:

    def __init__(self, roll, name):
        self.roll = roll
        self.name = name

class Result(Student):

    def __init__(self, roll, name, marks):
        super().__init__(roll, name)
        self.marks = marks

    def display(self):
        print("Roll No:", self.roll)
        print("Name:", self.name)
        print("Marks:", self.marks)

r = Result(101, "Rahul", 85)
r.display()
________________________________________
Experiment 6
Problem Statement
Write a Python program to demonstrate classes, objects, constructors, class methods, and static methods.
Program
class Employee:

    company = "ABC Pvt Ltd"

    def __init__(self, eid, name):
        self.eid = eid
        self.name = name

    @classmethod
    def company_name(cls):
        print("Company:", cls.company)

    @staticmethod
    def welcome():
        print("Welcome Employee")

e = Employee(1, "Amit")

e.welcome()
e.company_name()

print("ID:", e.eid)
print("Name:", e.name)
________________________________________
Experiments 7
Develop a Library Management System that:
•	Adds books to a list. 
•	Searches books by title. 
•	Stores book records in a file. 
•	Displays all books. 
•	Uses String Operations, Lists, and File Handling. 
Python Program
books = []

while True:

    print("\n===== LIBRARY MANAGEMENT SYSTEM =====")
    print("1. Add Book")
    print("2. Search Book")
    print("3. Display Books")
    print("4. Exit")

    choice = int(input("Enter Choice: "))

    if choice == 1:

        title = input("Enter Book Title: ")
        author = input("Enter Author Name: ")

        record = title + "," + author

        books.append(record)

        file = open("library.txt", "a")
        file.write(record + "\n")
        file.close()

        print("Book Added Successfully")

    elif choice == 2:

        search = input("Enter Book Title to Search: ")

        found = False

        for book in books:

            data = book.split(",")

            if data[0].lower() == search.lower():

                print("\nBook Found")
                print("Title :", data[0])
                print("Author:", data[1])

                found = True

        if found == False:
            print("Book Not Found")

    elif choice == 3:

        print("\n----- Book Records -----")

        file = open("library.txt", "r")

        for line in file:
            data = line.strip().split(",")

            print("Title :", data[0])
            print("Author:", data[1])
            print("---------------------")

        file.close()

    elif choice == 4:
        print("Program Ended")
        break

    else:
        print("Invalid Choice")


Experiments 8: Student Performance Analysis using Data Types and Operators
Problem Statement
Develop a Python program to analyze the academic performance of engineering students. The program should:
1.	Accept student details (Roll No, Name, Marks of 5 subjects). 
2.	Use different data types (int, float, str, list). 
3.	Perform arithmetic operations to calculate Total, Percentage, and Average Marks. 
4.	Use comparison and logical operators to determine Pass/Fail status. 
5.	Display the result in a formatted manner. 
Python Program
# Student Performance Analysis

roll_no = int(input("Enter Roll Number: "))
name = input("Enter Student Name: ")

marks = []

for i in range(5):
    mark = float(input(f"Enter Marks of Subject {i+1}: "))
    marks.append(mark)

# Arithmetic Operators
total = sum(marks)
average = total / 5
percentage = (total / 500) * 100

# Comparison and Logical Operators
if average >= 40 and min(marks) >= 35:
    result = "PASS"
else:
    result = "FAIL"

# Display Result
print("\n===== STUDENT RESULT =====")
print("Roll Number :", roll_no)
print("Name        :", name)
print("Marks       :", marks)
print("Total Marks :", total)
print("Average     :", round(average, 2))
print("Percentage  :", round(percentage, 2), "%")
print("Result      :", result)


Experiment 9: Employee Salary Management System (Long Program)
Problem Statement
Develop a Python program to maintain employee records. Accept Employee ID, Name, Basic Salary and calculate HRA, DA, PF, Gross Salary, and Net Salary.
class Employee:

    def __init__(self, eid, name, basic):
        self.eid = eid
        self.name = name
        self.basic = basic

    def calculate_salary(self):

        hra = self.basic * 0.20
        da = self.basic * 0.10
        pf = self.basic * 0.05

        gross = self.basic + hra + da
        net = gross - pf

        return hra, da, pf, gross, net

    def display(self):

        hra, da, pf, gross, net = self.calculate_salary()

        print("\nEmployee Details")
        print("Employee ID :", self.eid)
        print("Name        :", self.name)
        print("Basic Salary:", self.basic)
        print("HRA         :", hra)
        print("DA          :", da)
        print("PF          :", pf)
        print("Gross Salary:", gross)
        print("Net Salary  :", net)

employees = []

n = int(input("Enter Number of Employees: "))

for i in range(n):

    eid = input("Enter Employee ID: ")
    name = input("Enter Employee Name: ")
    basic = float(input("Enter Basic Salary: "))

    emp = Employee(eid, name, basic)

    employees.append(emp)

for emp in employees:
    emp.display()


