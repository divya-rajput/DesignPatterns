# State Design Pattern
* It is a behavioral design pattern which is used when an object changes its behavior based on its internal state.
* Identifying abstraction and implementation is the main task.
* Circuit breaker pattern

```
using System;
using System.Collections.Generic;
using System.Text;

namespace State
{
    interface IAppliance
    {
        public void On();
        public void Off();
    }

    abstract class IControl
    {
        IAppliance appliance;
        public void On() { }
        public void Off() { }
        public void setAppliance() { }
    }


    class TV : IAppliance
    {
        public void On() { }
        public void Off() { }
    }


    class RemoteControl : IControl
    {
        IAppliance appliance;
        public RemoteControl(IAppliance appliance)
        {
            this.appliance = appliance;
        }
        public new void On()
        {
            //When the button is pressed
            appliance.Off();
        }
        public new void Off()
        {
            //when the power off button is pressed
            appliance.Off();

        }
    }
    class Alexa : IControl
    {
        IAppliance appliance;
        public Alexa(IAppliance appliance)
        {
            this.appliance = appliance;
        }
        public new void On()
        {
            //when the voice is on
            appliance.On();
        }
        public new void Off()
        {
            //when the voice in alexa will turn off
            appliance.Off();

        }
    }
    class MainProgram
    {
        public static void Main(string[] args)
        {
            IControl remote = new RemoteControl(new TV());
            remote.On(); 
            remote.Off();
            IControl remoteAlexa = new Alexa(new TV());
            remoteAlexa.On();
            remoteAlexa.Off();

        }
    }
}
```
