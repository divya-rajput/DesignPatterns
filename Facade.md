# Facade Design Pattern
## Definition
* It is a structural design pattern. The complex system is divided into multiple sub systems based on the responsiblity.
* A facade is a class that provides a simple interface to a complex subsystem which contains lots of moving parts. 
* Advantage is we can isolate our code from the complexity of a subsystem. 
```
using System;
using System.Collections.Generic;
using System.Text;

namespace FacadePattern
{
    interface IDownloader
    {
        public void download();

    }
    interface ISave
    {
        public void save();
    }
    class downloadFile : IDownloader
    {
        public void download()
        {
            Console.WriteLine("Downloading file.......");
        }
    }
    class saveFile : ISave
    {
        public void save()
        {
            Console.WriteLine("Saving file.......");
        }
    }


    class Facade 
    {
        protected downloadFile _DF;
        protected saveFile _SF;
        public Facade(downloadFile DF, saveFile SF)
        {
            this._DF = DF;
            this._SF = SF;

        }
        public void Download()
        {
            _DF.download();
            _SF.save();
        }
    }

    class MainProg
    {
        public static void Main(String[] args)
        {
            downloadFile df = new downloadFile();
            saveFile sf = new saveFile();
            Facade fac = new Facade(df,sf);
            fac.Download();
        }
    }
}
```

