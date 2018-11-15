***Fluent Interface*** : The idea behind a fluent interface is that one can apply multiple properties to an object by connecting them with dots and without having to re-specify the object each time

C# uses fluent programming extensively in LINQ to build queries using the standard query operators. The implementation is based on extension methods

Fluent Interface Features : Fluent interface is a method for constructing object oriented APIs, where the readability of the source code is close to that of ordinary written prose

Fluent interface is normally implemented by using method cascading (concretely method chaining)

Fluent code is much more readable and allows to vary a product’s internal representation

Fluent Encapsulates code for construction and representation and Provides control over steps of an object construction process

Searching, Sorting, pagination, grouping with a blend of LINQ are some of the real world usage of fluent interface in combination with builder design pattern.

However, it’s not mandatory to implement fluent interfaces with builder design pattern however, the idea of this session is explore and integrate the fluent interface with builder design pattern.

By returning the ISystemBuilder and by using ***this*** as the return statement we are indicating that after assigning the properties of the desktop or  laptop we are returning back the same ISystemBuilder to allow the method chaining

```
public class LaptopBuilder : ISystemBuilder
    {
        ComputerSystem laptop = new ComputerSystem();
        public ISystemBuilder AddDrive(string size)
        {
            laptop.HDDSize = size;
            return this;
        }
        public ISystemBuilder AddKeyBoard(string type)
        {
            return this;
        }

        public ISystemBuilder AddMemory(string memory)
        {
            laptop.RAM = memory;
            return this; // important
        }
        public ISystemBuilder AddMouse(string type)
        {
            return this;
        }
        public ISystemBuilder AddTouchScreen(string enabled)
        {
            laptop.TouchScreen = enabled;
            return this;
        }
        public ComputerSystem GetSystem()
        {
            return laptop;
        }       
    }

    public class ConfigurationBuilder
    {
        public void BuildSystem(ISystemBuilder systembuilder
            , NameValueCollection collection)
        {
            systembuilder.AddDrive(collection["Drive"])
            .AddMemory(collection["RAM"])
            .AddMouse(collection["Mouse"])
            .AddKeyBoard(collection["Keyboard"])
            .AddTouchScreen(collection["TouchScreen"]);
        }
    }

    ```

    
