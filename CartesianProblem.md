### Requirement- Every shape should be printed in every printer.
```
interface Shape{

}

interface Printer{
    public void print(Shape shape);
}

class Inkjet : Printer{
    public void print(Shape _shape){
        //Print shape
    }
}
class Laser : Printer{
    public void print(Shape _shape){
        //Print shape
    }
}
class DotMatrix : Printer{
    public void print(Shape _shape){
        //Print shape
    }
}

class Rectangle : Shape{
    public string shapeName;
    public Rectangle(){
        this.shapeName = shapeName;
    }
}
class Square : Shape{
    public string name;
    public Square(){
        this.name = name;
    }
}
class Circle : Shape{
    public string identity;
    public Circle(){
        this.identity = identity;
    }
}
class Picture : Shape,Printer{
    public List<Shape> shapes;
    public List<Printer> printers;
    public printAll(){
        foreach (Printer printer in printers)
        {
            foreach (Shape shape in Shapes)
            {
                printer.Print(shape);
            }
        }

    }
}
```
