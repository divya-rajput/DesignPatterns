# Builder Design Pattern
* It separate the construction of a complex object from its representation so that the same construction process can create different representations.
* It is used to construct a complex object step by step and the final step will return the object.

## Code example
```
using System;
using System.Collections.Generic;
using System.Text;

namespace Builder
{
    class Customer
    {
        string name;
        string pancard;
        string address;
        string contactNumber;
        string emailId;
        string employeerName;
        public string ContactNumber { get; internal set; }
        public string Email { get; internal set; }
        public string Employeer { get; internal set; }
        public Customer(string name, string panCard) { }
        public Customer(string name, string panCard,string Email) { }
        public Customer(string name, string panCard, string address,string Email,string ContactNumber) { }
        public void SetEmailId() { }
    }
    class CustomerBuilder
    {
        Customer obj;
        public CustomerBuilder(string name, string panCard)
        {
            obj = new Customer(name, panCard);
        }
        public CustomerBuilder SetContactNumber(string contactNumber)
        {
            obj.ContactNumber = contactNumber;
            return this;
        }
        public CustomerBuilder SetEmail(string email)
        {
            obj.Email = email;
            return this;
        }
        public CustomerBuilder SetEmployeerName(string employeer)
        {
            obj.Employeer = employeer;
            return this;
        }
        public Customer GetCustomer() { return obj; }
    }
    class MainProgram
    {
        public static void Main(string[] args)
        {
            Customer obj = new CustomerBuilder("Divya", "fffffff").SetEmail("divya.rajput@philips.com").GetCustomer();
            Customer OBJ = new CustomerBuilder("Divya", "fffffff").SetEmail("divya.rajput@philips.com").SetContactNumber("9825006655").GetCustomer();

        }
    }
}







  
```
