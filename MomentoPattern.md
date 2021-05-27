# Momento Pattern
* A behavioural design pattern which is used to capture the current state of an object and store it in such a manner that it can be restored at a later time without breaking the rules of encapsulation.
* This pattern is commonly used in the menu systems of many applications such as Editor, IDE, etc.
* 3 classes(Originator, Momento, and Caretaker). Originator - creates a memento object containing a snapshot of the its current state. Momento- has information about the Originator’s saved state. Caretaker- it holds a Memento object for later use.

## Code Example
```
using System;
namespace Momento
{

    class Originator
    {
        private string _state;
        public string State
        {
            get { return _state; }
            set
            {
                _state = value;
                Console.WriteLine("State = " + _state);
            }
        }
        public Memento CreateMemento()
        {
            return (new Memento(_state));
        }
        public void SetMemento(Memento memento)
        {
            Console.WriteLine("Restoring state...");
            State = memento.State;
        }
    }

    class Memento

    {
        private string _state;
        public Memento(string state)
        {
            this._state = state;
        }
        public string State
        {
            get { return _state; }
        }
    }
    class Caretaker

    {
        private Memento _memento;
        public Memento Memento
        {
            set { _memento = value; }
            get { return _memento; }
        }
    }
    class MainProgram
    {
        static void Main()
        {
            Originator o = new Originator();
            o.State = "On";
            Caretaker c = new Caretaker();
            c.Memento = o.CreateMemento();
            o.State = "Off";
            o.SetMemento(c.Memento);
            Console.ReadKey();
        }
    }


}







```
