# Chain Of Responsiblity
* This pattern is used to process a list or chain of various types of request and each of them may be handled by a different handler.
* This pattern decouples sender and receiver of a request based on the type of request.
* Each receiver (handler) contains a reference to another receiver.

## Code Example
```
using System;
using System.Collections.Generic;
using System.Text;

namespace ChainOfResponsblity
{
    public abstract class Processes
    {
        Processes process;
        public void setProcess(Processes process)
        {
            this.process = process;
        }
        public void execute()
        {

        }
    }
    class ProcessA : Processes
    {
        Processes process;
        public void execute()
        {
            //Console.WriteLine("Process A is initiated......");
            process.execute();
        }
    }
    class ProcessB : Processes
    {
        Processes process;
        public void execute()
        {
            //Console.WriteLine("Process B is initiated......");
            process.execute();
        }
    }
    class ProcessC : Processes
    {
        Processes process;
        public void execute()
        {
            //Console.WriteLine("Process C is initiated......");
            process.execute();
        }
    }
    class MainProgram1
    {
        public static void main(string[] args)
        {
            Processes A = new ProcessA();
            Processes B = new ProcessB();
            Processes C = new ProcessC();
            A.setProcess(B);
            B.setProcess(C);
            A.execute();
        }
    }


}

```
