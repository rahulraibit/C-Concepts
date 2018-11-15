# Singleton Design pattern

It ensure that only one instance will be created for the class and will be used across the application.

 - steps to create singleton class

 1. singleton class should be sealed, So that no other class can able to inherit it.
 2. Constructor should be private so that new keyword can not be used.
 3. Create a static method which will return the instance of the class.
 4. Sealed also ensure that even nested class inside the singleton class will not able to inherit the upper class.
 5. In multithread environment without lock check singleton concept will fail.


 ```
Singleton.cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
/// <summary>
/// First Singleton version
/// </summary>
namespace SingletonDemo
{
    /*
     *  Sealed ensures the class being inherited and
     *  object instantiation is restricted in the derived class
     */
    public sealed class Singleton
    {
        private static int counter = 0;

        /*
         * Private property initilized with null
         * ensures that only one instance of the object is created
         * based on the null condition
         */
        private static Singleton instance = null;
       
        /*
         * public property is used to return only one instance of the class
         * leveraging on the private property
         */
        public static Singleton GetInstance
        {
            get
            {
                if (instance == null)
                    instance = new Singleton();
                return instance;
            }
        }
        /*
         * Private constructor ensures that object is not
         * instantiated other than with in the class itself
         */
        private Singleton()
        {
            counter++;
            Console.WriteLine("Counter Value " + counter.ToString());
        }
    }

namespace SingletonDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            /*
             * Assuming Singleton is created from employee class
             * we refer to the GetInstance property from the Singleton class
             */
            Singleton fromEmployee = Singleton.GetInstance;
            fromEmployee.PrintDetails("From Employee");
            /*
             * Assuming Singleton is created from student class
             * we refer to the GetInstance property from the Singleton class
             */
            Singleton fromStudent = Singleton.GetInstance;
            fromStudent.PrintDetails("From Student");

            Console.ReadLine();
        }
    }
}

```

*** Lazy vs Eager Initilization ***

*** Lazy Loading ***

1. improves the performance.
2. avoid unnecessary load till the point object is accessed.
3. Reduces the memory footprint on the start up.
4. faster application load.

*** Non Lazy Or Eager Loading ***

1. Pre initiation of the object.
2. commonly used in lower memory footprints.


```

namespace SingletonDemo
{
   
    public sealed class Singleton
    {
        private static int counter = 0;
       
        private Singleton()
        {
            counter++;
            Console.WriteLine("Counter Value " + counter.ToString());
        }
        private static readonly Lazy<Singleton> instance = 
new Lazy<Singleton>(()=>new Singleton());
       
        public static Singleton GetInstance
        {
            get
            {
                return instance.Value;
            }
        }
       
        public void PrintDetails(string message)
        {
            Console.WriteLine(message);
        }       
    }
} 

```

*** Differences between Singleton and static classes ***

1. Static is a keyword and Singleton is a design pattern
2. Static classes can contain only static members
3. Singleton is an object creational pattern with one instance of the class
4. Singleton can implement interfaces, inherit from other classes and it aligns with the OOPS concepts
5. Singleton object can be passed as a reference
6. Singleton supports object disposal
7. Singleton object is stored on heap
8. Singleton objects can be cloned

Static class example - Temperature Converter 
We are pretty sure that the formulas for foreign heat to Celsius conversion and vice versa will not change at all and hence we can use static classes with static methods that does the conversion for us. Please refer to the below code for more details.

*** Real world usage of Singleton : Listed are few real world scenarios for singleton usage ***

1. Exception/Information logging
2. Connection pool management 
3. File management
4. Device management such as printer spooling
5. Application Configuration management
6. Cache management And Session based shopping cart are some of the real world usage of singleton design pattern