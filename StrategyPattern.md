# Startegy design pattern
* In this pattern, a class behavior or its algorithm can be changed at run time. This is a behavioral pattern.
* we create objects which represent various strategies and a object whose behavior varies as per its strategy object.
* It is basically how to seperate and how to abstract.
* YAGNI- You Aren't Gonna Need It 

```
using System;
using System.Collections.Generic;
using System.Text;

namespace Numbers
{

    public interface Strategy
    {
        public int Operation(int number1, int number2);
    }
    public class AddOperation : Strategy
    {
        public int Operation(int number1, int number2)
        {
            return number1 + number2;
        }

    }
    public class SubOperation : Strategy
    {
        public int Operation(int number1, int number2)
        {
            return number1 - number2;
        }

    }
    public class MulOperation : Strategy
    {
        public int Operation(int number1, int number2)
        {
            return number1 * number2;
        }
    }


    public class DivOperation : Strategy
        {
            public int Operation(int number1, int number2)
            {
                return number1 / number2;
            }

        }
    public class Context
    {
        private Strategy strategy;

        public Context(Strategy strategy)
        {
            this.strategy = strategy;
        }
        public int ExecuteStrategy(int num1, int num2)
        {
            return strategy.Operation(num1, num2);
        }
    }
    class StrategyMain
    {
        public static void Main(string[] args)
        {
            Context contextAdd = new Context(new AddOperation()); 
            Console.WriteLine("10 + 5 = {0}" , contextAdd.ExecuteStrategy(10, 5));
            Context contextSub = new Context(new SubOperation());
            Console.WriteLine("10 - 5 = {0}", contextSub.ExecuteStrategy(10, 5));
            Context contextMul = new Context(new MulOperation());
            Console.WriteLine("10 * 5 = {0}", contextMul.ExecuteStrategy(10, 5));
            Context contextDiv = new Context(new DivOperation());
            Console.WriteLine("10 / 5 = {0}", contextDiv.ExecuteStrategy(10, 5));
        }
    }
}

```

