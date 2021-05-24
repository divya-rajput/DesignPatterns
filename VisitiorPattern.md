# Visitor Design Pattern
* Visitor should know about the object on which it is performing the operation.
* Visitor lets you define a new operation without changing the classes of the elements on which it operates.
* It is use to resolve double dispatch problem.
```
interfce IP{
void AM(IV v);
}
class A : IP
{
   void AM(IV v)
   { 
       v.M(this); 
    }

}
class B:IP
{
    void AM(IV v)
    {
        v.M(this);
    }
}
//Pure Abstract Class
interfce IV
{
   void M(A obj)
   void M(B obj)
}
class C:IV
{
    void M(A obj)
    { 
        obj.AM();
    }
    void M(B obj)
    { 
        obj.AM();
    }
}
class D:IV
{
    void M(A obj)
    { 
        obj.AM();
    }
    void M(B obj)
    {
        obj.AM();
    }
}

IP aptr=new B();
IV cptr=new D();
aptr.AM(cptr); //cptr is D's object

 ```
