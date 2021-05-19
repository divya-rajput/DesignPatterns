# Dependency Inversion Principle
## Definition
* High level module(Service Consumer) should not be dependent lower level module(Service Provider).
* Both should depend on the abstraction.
* So, We end up having 2 dependencies. High level module on abstraction and lower level on the same abstraction.

## Example
```
public interface ICustomerDataAccess
{
    string GetCustomerName(int id);
}
 
public class CustomerDataAccess: ICustomerDataAccess
{
    public CustomerDataAccess() {
    }
 
    public string GetCustomerName(int id) {
        return "Dummy Customer Name";        
    }
}
 
public class CustomerBusinessLogic
{
    ICustomerDataAccess _custDataAccess;
 
    public CustomerBusinessLogic(ICustomerDataAccess custDataAccess))
    {
        _custDataAccess = custDataAccess;
    }
 
    public string GetCustomerName(int id)
    {
        return _custDataAccess.GetCustomerName(id);
    }
}
```

