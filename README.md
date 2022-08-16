# class-method-and-static-method
from datetime import date
class Employee:
    def __init__(self,name,dob,salary,gender,city):
        self.name = name
        self.dob = dob
        self.salary = salary
        self.gender = gender
        self.city = city
        
    def address(self):
        addr = f'Name : {self.name}\nDOB : {self.dob}\nSalary : {self.salary}\nCity : {self.city}\nGender = {self.gender}'
        return addr
    
    
    def age(self):
        current_year=date.today().year
        return current_year - self.dob
    
    @classmethod
    def current_salary(cls,sal):
        cls.sal=sal
        
    @classmethod
    def emp_data(cls,data):
        name,dob,salary,genter,city = data.split(',')
        return cls(name,dob,salary,genter,city)
    
emp1=Employee('Sangavi',1994,20000,'Female','Chennai')
emp2=Employee('Ragavan',1992,30000,'Male','Chennai')
Employee.current_salary(30200)
print(emp1.sal)

data = 'ram,2001,20300,Male,Theni'
emp3= Employee.emp_data(data)
print(emp3.dob)
