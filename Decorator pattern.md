## Decorator pattern 
# Definition
* Pattern which allow an instance of a class to create at run time without affecting the structure of a class or the other instances of the same class.
* Adding new behaviour to an instance without changing other instances.

```
using System;
using System.Collections.Generic;
using System.Text;

namespace Numbers
{
    interface ITask
    {
        public void Execute();
    }
    class Task : ITask
    {
        public void Execute()
        {
            //Execute task
        }
    }
    class LogTask : ITask
    {
        ITask taskref;
        public LogTask(ITask task)
        {
            this.taskref = task;
        }
        public void Execute()
        {
            taskref.Execute();
        }
     }
    class PerformanceMeasureTask : ITask
    {
        ITask taskref;
        public PerformanceMeasureTask(ITask task)
        {
            this.taskref = task;
        }
        public void Execute()
        {
            taskref.Execute();
        }

    }
    class MainProgram
    {
        public static void Main(String[] args)
        {
            ITask t1 = new Task();
            t1 = new LogTask(new PerformanceMeasureTask(t1));

        }
    }
}
```
