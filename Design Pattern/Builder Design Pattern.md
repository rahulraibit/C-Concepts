# Builder design Pattern

It gives a common method to construct the real model from the different objects.

http://csharp-video-tutorials.blogspot.com/2017/09/builder-design-pattern-implementation.html

Eg.

```

public interface ISystemBuilder
    {
        void AddMemory(string memory);
        void AddDrive(string size);

        void AddKeyBoard(string type);
        void AddMouse(string type);

        void AddTouchScreen(string enabled);
        ComputerSystem GetSystem();
    }

public class DesktopBuilder : ISystemBuilder
    {
        ComputerSystem desktop = new ComputerSystem();
        public void AddDrive(string size)
        {
            desktop.HDDSize = size;
        }
        public void AddKeyBoard(string type)
        {
            desktop.KeyBoard = type;
        }
        public void AddMemory(string memory)
        {
            desktop.RAM = memory;
        }
        public void AddMouse(string type)
        {
            desktop.Mouse = type;
        }
        public void AddTouchScreen(string enabled)
        {
            return;
        }
        public ComputerSystem GetSystem()
        {
            return desktop;
        }
    }

    public class LaptopBuilder : ISystemBuilder
    {
        ComputerSystem laptop = new ComputerSystem();
        public void AddDrive(string size)
        {
            laptop.HDDSize = size;
        }

        public void AddKeyBoard(string type)
        {
            return;
        }

        public void AddMemory(string memory)
        {
            laptop.RAM = memory;
        }

        public void AddMouse(string type)
        {
           return;
        }

        public void AddTouchScreen(string enabled)
        {
            laptop.TouchScreen = enabled;
        }

        public ComputerSystem GetSystem()
        {
            return laptop;
        }
    }
 
    // Note 
    public class ConfigurationBuilder
    {
        public void BuildSystem(ISystemBuilder systembuilder
            , NameValueCollection collection)
        {
            systembuilder.AddDrive(collection["Drive"]);
            systembuilder.AddMemory(collection["RAM"]);
            systembuilder.AddMouse(collection["Mouse"]);
            systembuilder.AddKeyBoard(collection["Keyboard"]);
            systembuilder.AddTouchScreen(collection["TouchScreen"]);
        }
    }
```