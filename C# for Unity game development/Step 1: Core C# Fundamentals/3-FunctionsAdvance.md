### **Advanced Concepts in Functions and Methods in C#: Deep Dive**

Functions (also called methods in C#) are the building blocks of a program. In advanced programming, we focus on how to structure, organize, and utilize methods efficiently. This section explores advanced topics in **functions and methods** step by step.

---

### **Topics Breakdown**
1. **Method Overloading**
2. **Optional and Named Parameters**
3. **Extension Methods**
4. **Anonymous Functions**
5. **Lambda Expressions**
6. **Delegates**
7. **Func, Action, and Predicate**
8. **Asynchronous Methods (Async/Await)**

Let’s dive into each topic.

---

### **1. Method Overloading**

**Definition**: Method overloading allows multiple methods with the same name but different parameter lists (types, numbers, or order). It enables methods to perform similar tasks but with different inputs.

#### **Example**
```csharp
using System;

class Program
{
    // Overloaded Add methods
    static int Add(int a, int b)
    {
        return a + b;
    }

    static double Add(double a, double b)
    {
        return a + b;
    }

    static int Add(int a, int b, int c)
    {
        return a + b + c;
    }

    static void Main(string[] args)
    {
        Console.WriteLine(Add(2, 3));          // Calls Add(int, int)
        Console.WriteLine(Add(2.5, 3.5));      // Calls Add(double, double)
        Console.WriteLine(Add(1, 2, 3));       // Calls Add(int, int, int)
    }
}
```

**Key Points**:
- Differentiated by the number/type/order of parameters.
- Return type alone cannot differentiate overloaded methods.

---

### **2. Optional and Named Parameters**

**Optional Parameters** allow you to specify default values for method parameters.

**Named Parameters** let you specify arguments by parameter name, making the method call more readable.

#### **Example**
```csharp
using System;

class Program
{
    static void Greet(string name, string message = "Welcome!") // Optional parameter
    {
        Console.WriteLine($"{message}, {name}");
    }

    static void Main(string[] args)
    {
        Greet("Alice");                       // Uses default value for message
        Greet("Bob", "Hello");                // Overrides default value
    }
}
```

#### **Named Parameters Example**
```csharp
using System;

class Program
{
    static void DisplayInfo(string name, int age, string city)
    {
        Console.WriteLine($"{name} is {age} years old and lives in {city}.");
    }

    static void Main(string[] args)
    {
        DisplayInfo(name: "Alice", city: "Paris", age: 25); // Named parameters
    }
}
```

---

### **3. Extension Methods**

**Definition**: Extension methods allow you to add new methods to existing types without modifying their definition. They are defined as `static` methods in a static class.

#### **Example**
```csharp
using System;

public static class StringExtensions
{
    public static int WordCount(this string str)
    {
        return str.Split(new[] { ' ', '\t', '\n' }, StringSplitOptions.RemoveEmptyEntries).Length;
    }
}

class Program
{
    static void Main(string[] args)
    {
        string sentence = "Hello, this is an extension method example!";
        Console.WriteLine($"Word count: {sentence.WordCount()}");
    }
}
```

**Key Points**:
- Use `this` keyword before the first parameter to define the type being extended.
- Cannot override existing methods.

---

### **4. Anonymous Functions**

Anonymous functions are methods without a name. They include **lambda expressions** and **anonymous delegates**.

#### **Example: Anonymous Delegate**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Func<int, int> square = delegate (int x)
        {
            return x * x;
        };

        Console.WriteLine(square(5)); // Output: 25
    }
}
```

---

### **5. Lambda Expressions**

**Definition**: Lambda expressions are shorthand for defining anonymous methods. Syntax: `(parameters) => expression`.

#### **Example**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Func<int, int> square = x => x * x;   // Lambda expression
        Console.WriteLine(square(6));        // Output: 36
    }
}
```

#### **Lambda with Multiple Parameters**
```csharp
Func<int, int, int> add = (a, b) => a + b;
Console.WriteLine(add(2, 3));  // Output: 5
```

---

### **6. Delegates**

**Definition**: Delegates are type-safe function pointers used to pass methods as parameters.

#### **Example**
```csharp
using System;

class Program
{
    delegate int Operation(int a, int b);

    static int Add(int a, int b) => a + b;
    static int Multiply(int a, int b) => a * b;

    static void Main(string[] args)
    {
        Operation op = Add;
        Console.WriteLine(op(3, 4));   // Output: 7

        op = Multiply;
        Console.WriteLine(op(3, 4));   // Output: 12
    }
}
```

---

### **7. Func, Action, and Predicate**

These are predefined generic delegates:
- **Func**: Returns a value (e.g., `Func<int, int> square`).
- **Action**: No return value (e.g., `Action<string> greet`).
- **Predicate**: Returns a boolean (e.g., `Predicate<int> isEven`).

#### **Example**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Func<int, int> square = x => x * x;
        Console.WriteLine(square(5));   // Output: 25

        Action<string> greet = name => Console.WriteLine($"Hello, {name}!");
        greet("Alice");                 // Output: Hello, Alice!

        Predicate<int> isEven = x => x % 2 == 0;
        Console.WriteLine(isEven(4));   // Output: True
    }
}
```

---

### **8. Asynchronous Methods (Async/Await)**

**Definition**: Async methods allow for non-blocking, responsive applications.

#### **Example**
```csharp
using System;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        Console.WriteLine("Start");
        await PrintMessageAsync();
        Console.WriteLine("End");
    }

    static async Task PrintMessageAsync()
    {
        await Task.Delay(2000); // Simulates an asynchronous operation
        Console.WriteLine("Async Message");
    }
}
```

**Key Points**:
- Use `async` keyword for methods that return `Task` or `Task<T>`.
- Use `await` to wait for asynchronous operations.

---

### **Practice Tasks**
1. Create overloaded methods for calculating the area of a rectangle and a circle.
2. Write an extension method to reverse a string.
3. Implement a delegate that takes two numbers and performs addition, subtraction, and multiplication.
4. Write an asynchronous method to simulate downloading a file.

Let me know which sub-topic you'd like to dive deeper into! 🚀