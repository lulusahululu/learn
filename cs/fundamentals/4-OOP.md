### **Object-Oriented Programming (OOP) in C#**

OOP is a programming paradigm based on the concept of "objects," which can contain data (fields) and code (methods). C# is fully object-oriented and provides powerful tools to model real-world entities.

---

### **Core Principles of OOP**

1. **Encapsulation**: Bundling data (fields) and methods (functions) that operate on the data into a single unit (class).  
2. **Abstraction**: Hiding complex implementation details and showing only essential features.  
3. **Inheritance**: Allowing a class to derive from another class, reusing its methods and fields.  
4. **Polymorphism**: Enabling one interface to be used for different data types or methods.

---

### **1. Classes and Objects**

#### **Class**  
A blueprint for creating objects. It defines properties (fields) and behaviors (methods).

#### **Object**  
An instance of a class, representing a specific entity.

#### **Syntax**
```csharp
class ClassName
{
    // Fields (variables)
    public string name;
    public int age;

    // Methods
    public void DisplayInfo()
    {
        Console.WriteLine($"Name: {name}, Age: {age}");
    }
}

// Creating and using an object
ClassName obj = new ClassName();
obj.name = "Lulu";
obj.age = 30;
obj.DisplayInfo();
```

---

### **2. Encapsulation**
Encapsulation ensures that sensitive data is hidden from external access by using **access modifiers** like `private` and `public`.

#### **Example**
```csharp
class Person
{
    private string name; // Private field

    // Public method to set the name
    public void SetName(string newName)
    {
        name = newName;
    }

    // Public method to get the name
    public string GetName()
    {
        return name;
    }
}

// Usage
Person person = new Person();
person.SetName("Lulu");
Console.WriteLine(person.GetName()); // Output: Lulu
```

---

### **3. Inheritance**
Inheritance allows one class (child) to inherit fields and methods from another class (parent).

#### **Syntax**
```csharp
class ParentClass
{
    public void Greet()
    {
        Console.WriteLine("Hello from Parent!");
    }
}

class ChildClass : ParentClass
{
    public void SayHello()
    {
        Console.WriteLine("Hello from Child!");
    }
}

// Usage
ChildClass child = new ChildClass();
child.Greet(); // Inherited from ParentClass
child.SayHello();
```

---

### **4. Polymorphism**
Polymorphism allows methods to be overridden or defined differently in derived classes.

#### **Method Overriding**
A child class can redefine a method from the parent class using the `override` keyword.

```csharp
class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks.");
    }
}

class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks.");
    }
}

// Usage
Animal animal = new Animal();
animal.Speak(); // Output: Animal speaks.

Animal dog = new Dog();
dog.Speak(); // Output: Dog barks.
```

---

### **5. Abstraction**
Abstract classes define common behavior but cannot be instantiated. Concrete classes must provide implementation for abstract methods.

#### **Example**
```csharp
abstract class Shape
{
    public abstract double CalculateArea(); // Abstract method
}

class Circle : Shape
{
    private double radius;

    public Circle(double radius)
    {
        this.radius = radius;
    }

    public override double CalculateArea()
    {
        return Math.PI * radius * radius;
    }
}

// Usage
Circle circle = new Circle(5);
Console.WriteLine("Area of Circle: " + circle.CalculateArea());
```

---

### **6. Interfaces**
An interface defines a contract that implementing classes must fulfill. All methods in an interface are abstract by default.

#### **Example**
```csharp
interface IPlayable
{
    void Play();
}

class Game : IPlayable
{
    public void Play()
    {
        Console.WriteLine("Game is playing...");
    }
}

// Usage
Game game = new Game();
game.Play();
```

---

### **Access Modifiers**
| Modifier   | Description                                                                 |
|------------|-----------------------------------------------------------------------------|
| `public`   | Accessible from anywhere.                                                  |
| `private`  | Accessible only within the same class.                                     |
| `protected`| Accessible within the same class and derived classes.                      |
| `internal` | Accessible within the same assembly (project).                             |

---

### **Practice Tasks**
1. **Create a class** `Car` with fields for brand, model, and year. Add methods to display this information.
2. **Create an inheritance hierarchy** where `Animal` is the parent class and `Dog` and `Cat` are derived classes with their specific `Speak()` methods.
3. **Implement an interface** `IDriveable` with a `Drive()` method and create a class `Truck` that implements it.
4. **Create an abstract class** `Shape` with a method `CalculateArea()`. Derive classes `Rectangle` and `Triangle` to implement it.

Let me know which principle or concept you’d like to explore in more detail!