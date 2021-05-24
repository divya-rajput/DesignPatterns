# Visitor Design Pattern
* Visitor should know about the object on which it is performing the operation.
```
interfce IP{

 

void AM(IV v);
}
class A : IP
{
   void AM(IV v){ v.M(this); }

 

}

 

class B:IP{

 

void AM(IV v){
    v.M(this);
}

 

}

 

//Pure Abstract Class

 

interfce IV{
   void M(A obj)
   void M(B obj)
}
class C:IV{

 


void M(A obj){ obj.AM();}
void M(B obj){ obj.AM();}

 

}

 

class D:IV{

 

void M(A obj){ obj.AM();}
void M(B obj){obj.AM();}

 

}

 

A aptr=new B();
C cptr=new D();

 

aptr.AM(cptr);

 ```
