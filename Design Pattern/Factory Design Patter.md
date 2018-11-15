# What is Factory Design Pattern 

Define an interface for creating an object, but let sub-classes decide which class to instantiate. The Factory method lets a class defer instantiation it uses to sub-classes

Factory pattern is one of the most used design patterns in real world applications 

Factory pattern creates object without exposing the creation logic to the client and refer to newly created object using a common interface

 ***We need to choose Factory Pattern when***

The Object needs to be extended to subclasses
The Classes doesn’t know what exact sub-classes it has to create
The Product implementation tend to change over time and the Client remains unchanged

Steps

Simple Factory

1. Create interace or abstract method, which have all the methods that need to be implement.
2. Create different class by implementing the interface as per business requirement.
3. Create Factory class which will return object of required class by returning Interface type object.

Eg. 

Simple Factory Example : Business Requirement

Differentiate employees as permanent and contract and segregate their pay scales as well as bonus based on their employee types

```

IEmployeeManager.cs

public interface IEmployeeManager
    {
        decimal GetBonus();
        decimal GetPay();
    }

    ContractEmployeeManager.cs

    public class ContractEmployeeManager : IEmployeeManager
    {
        public decimal GetBonus()
        {
            return 5;
        }

        public decimal GetPay()
        {
            return 12;
        }
    }

PermanentEmployeeManager.cs

    public class PermanentEmployeeManager : IEmployeeManager
    {
        public decimal GetBonus()
        {
            return 10;
        }

        public decimal GetPay()
        {
            return 8;
        }
    }

    EmployeeManagerFactory.cs

    public class EmployeeManagerFactory
    {
        public IEmployeeManager GetEmployeeManager(int employeeTypeID)
        {
            IEmployeeManager returnValue = null;
            if (employeeTypeID == 1)
            {
                returnValue = new PermanentEmployeeManager();
            }
            else if (employeeTypeID == 2)
            {
                returnValue = new ContractEmployeeManager();
            }
            return returnValue;
        }
    }

```

