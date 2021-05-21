#  Composite Design pattern
## Definition
* Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they were individual objects.
* Tree contains Leaf and composite elements.
Example of an organization:
```
interface Employee
    {
        public void Update(){}
    }
class Developer:Employee
  {
    public void Update(){}
   }
 class Tester : Employee
    {
        public void Update(){}
    }
class Manager : Employee
{
      public List<Employee> EmployeeList;
        public Manager()
        {
            EmployeeList = new List<Employee>();
        }
        public void Update(){
        // Update Employe details
        }
        public void AddEmployee(Employee employee)
        {
        //Add employee
        }
        public void RemoveEmployee(Employee employee)
        {
          // remove employee name
        }
    }
 public class HumanResource : Employee
    {
        public List<Employee> EmployeeList;
        public HR()
        {
            EmployeeList = new List<Employee>();
        }
        public void Update()
        {
          //update employee name
        }
        public void AddEmployee(Employee employee)
        {
            //Add employee
        }
        public void RemoveEmployee(Employee employee)
        {
           Remove employee
        }
    }

    public class Management
    {
      Employee _emp
        public Management(Employee emp)
        {
            _emp= emp;
        }
        public void Update(Employee emp)
        {
            _emp.Update();
        }
    }
```
