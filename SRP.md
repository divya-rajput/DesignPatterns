# Single responsiblity principle(SRP)
## What is a SRP?
* There should be a proper Segregation of responsiblities in every level of programming(Module, Interfaces, Classes, Functions, Methods, Objects).
* This principle helps us to build a code with is more understandable, has good unit testing, and  maintainability qualities.
* This is one step towards achieving proper programming paradigm.

## How SRP can be achieved?
* SRP can be achieved by various ways like proper naming conventions used for Module, Interfaces, Classes, Functions, Methods and Objects and also their proper encapsulation.
* Here, based on the roles the responsiblity should be divided. Example: There should be a different class of a Manager(), TeamLead() and, an Employee(). Since, their Roles are different although being a part of same organization.
* Similarly, Module, Interfaces, Functions, Methods and Objects should be seperated based on the their responsiblities.
* In UI based applications SRP can be achieved by using various models like MVC(Model View Controller) and MVVM (Model View-View Model).

## What happens when SRP is violated?
* If SRP is not followed in the code, one will end up in writing complex code which is hard to understand by anyone else.

## SRP code examples
* The code which violates the SRP
```
class BaseTransform{
  public void transform(){
    if (data.format == "care")
    //transform care data code
    else if(data.format == "Demographics")
    //transform demographics data code
    else if(data.format == "vital-sign")
    //transform vital-sign data code
    else if(data.format == "Payer")
    //transform Payer data code
    else if(data.format == "Immunization")
    //transform Immunization data code
    else{
    //Some error with data format provided
    }
   } 
}
```
In the above example, the responsiblities of care, demographics,payer,vital-sign and Immunization are different as they will contain different kind of data. But still keeping them in one class is violation of SRP. Let's try to seperate their responsiblities and try to achieve SRP.

* The code after achieving SRP

```
Interface BaseTransform{
  public void Transform();
  }
 class CareDataTransform : BaseTransform{
          public void Transform(){
          //Transform care Data
          }
  }
  class DemographicsDataTransform : BaseTransform{
          public void Transform(){
          //Transform Demographics Data
          }
  }
  class VitalSignDataTransform : BaseTransform{
          public void Transform(){
          //Transform VitalSign Data
          }
  }
  class PayerDataTransform : BaseTransform{
          public void Transform(){
          //Transform Payer Data
          }
  }
  class ImmunizationDataTransform : BaseTransform{
          public void Transform(){
          //Transform Immunization Data
          }
  }
class MainClass{
      public static void Main(){
      CareDataTransform CareObj = new CareDataTransform();
      CareObj.Transform();
      DemographicsDataTransform DemoObj = new DemographicsDataTransform();
      DemoObj.Transform();
      }
 }
           
```
