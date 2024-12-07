### **Introduction to C#: Basics of Programming**

#### **What is C#?**
C# (pronounced *C-sharp*) is:
- A modern, object-oriented programming language developed by Microsoft.
- Primarily used for Windows applications, but also widely used in Unity for game development.
- Known for being beginner-friendly while offering powerful features for professionals.

#### **Why Learn C# for Unity?**
- Unity uses C# as its primary scripting language.
- It's efficient for developing games, with tools for physics, animations, and real-time rendering.
- Provides a foundation for creating interactive, dynamic gameplay.

---

### **Basic Programming Concepts**
Let’s start with some fundamentals:

#### **1. Writing Your First C# Program**
Here's a simple "Hello, World!" program in C#:

```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
    }
}
```

- **`using System;`**: Includes the System namespace (libraries with useful functions).
- **`class Program`**: Defines a class named `Program` (required in C#).
- **`static void Main`**: Entry point of the program; it runs first.
- **`Console.WriteLine`**: Prints text to the console.

---

#### **2. Variables and Data Types**
Variables store data in a program. Examples of common data types:
- **int**: Stores integers (e.g., `5`, `100`).
- **float**: Stores decimal numbers (e.g., `3.14f`, `-0.9f`).
- **string**: Stores text (e.g., `"Hello"`).
- **bool**: Stores true/false values.

Example:
```csharp
int age = 25;
float height = 5.9f;
string name = "Lulu";
bool isLeader = true;

Console.WriteLine("Name: " + name);
Console.WriteLine("Age: " + age);
Console.WriteLine("Height: " + height);
Console.WriteLine("Leader: " + isLeader);
```

---

#### **3. Operators**
You can perform operations on variables:
- **Arithmetic**: `+`, `-`, `*`, `/`, `%`
- **Relational**: `==`, `!=`, `<`, `>`, `<=`, `>=`
- **Logical**: `&&` (AND), `||` (OR), `!` (NOT)

Example:
```csharp
int x = 10;
int y = 20;

Console.WriteLine(x + y);  // Output: 30
Console.WriteLine(x > y); // Output: False
Console.WriteLine(x != y); // Output: True
```

---

#### **Practice Task**
1. Create a new program that:
   - Declares variables for your name, age, and role (e.g., "Leader").
   - Prints them to the console.
2. Use arithmetic operators to calculate the sum of two numbers and display the result.

Once you're ready, we can move to **Control Flow** (if-else, loops). Let me know if you need help running the code!