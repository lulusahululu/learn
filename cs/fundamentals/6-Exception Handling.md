### **Exception Handling in C#: Ensuring Robust Code**

Exception handling in C# provides a way to gracefully handle runtime errors, ensuring that your application does not crash unexpectedly and can recover or notify the user appropriately.

---

### **What is an Exception?**
An **exception** is an event that occurs during the execution of a program, disrupting its normal flow. Examples include:
- Dividing by zero
- Accessing null objects
- File not found
- Index out of range

---

### **C# Exception Handling Keywords**
1. **`try`**: Defines a block of code to monitor for exceptions.
2. **`catch`**: Defines a block of code to handle specific exceptions.
3. **`finally`**: Defines a block of code that always executes, regardless of whether an exception occurred or not.
4. **`throw`**: Used to raise (throw) an exception.

---

### **Basic Syntax**
```csharp
try
{
    // Code that might throw an exception
}
catch (ExceptionType e)
{
    // Code to handle the exception
}
finally
{
    // Code that always executes (optional)
}
```

---

### **Example: Basic Exception Handling**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        try
        {
            int num1 = 10;
            int num2 = 0;
            int result = num1 / num2; // This will throw a DivideByZeroException
            Console.WriteLine("Result: " + result);
        }
        catch (DivideByZeroException e)
        {
            Console.WriteLine("Error: " + e.Message);
        }
        finally
        {
            Console.WriteLine("Execution completed.");
        }
    }
}
```

**Output:**
```
Error: Attempted to divide by zero.
Execution completed.
```

---

### **Multiple `catch` Blocks**

You can use multiple `catch` blocks to handle different types of exceptions.

#### **Example**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]); // IndexOutOfRangeException
        }
        catch (IndexOutOfRangeException e)
        {
            Console.WriteLine("Index out of range: " + e.Message);
        }
        catch (Exception e)
        {
            Console.WriteLine("General error: " + e.Message);
        }
    }
}
```

---

### **The `finally` Block**
The `finally` block executes whether an exception occurs or not. It is often used for cleanup (e.g., closing files or releasing resources).

#### **Example**
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]);
        }
        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.Message);
        }
        finally
        {
            Console.WriteLine("Cleaning up resources.");
        }
    }
}
```

---

### **Throwing Exceptions**

You can manually raise exceptions using the `throw` keyword.

#### **Example**
```csharp
using System;

class Program
{
    static void Divide(int a, int b)
    {
        if (b == 0)
        {
            throw new DivideByZeroException("Cannot divide by zero.");
        }
        Console.WriteLine("Result: " + (a / b));
    }

    static void Main(string[] args)
    {
        try
        {
            Divide(10, 0);
        }
        catch (Exception e)
        {
            Console.WriteLine("Error: " + e.Message);
        }
    }
}
```

---

### **Custom Exceptions**

You can create custom exceptions by inheriting from the `Exception` class.

#### **Example**
```csharp
using System;

class InvalidAgeException : Exception
{
    public InvalidAgeException(string message) : base(message)
    {
    }
}

class Program
{
    static void CheckAge(int age)
    {
        if (age < 18)
        {
            throw new InvalidAgeException("Age must be 18 or older.");
        }
        Console.WriteLine("Access granted.");
    }

    static void Main(string[] args)
    {
        try
        {
            CheckAge(16);
        }
        catch (InvalidAgeException e)
        {
            Console.WriteLine("Custom Exception: " + e.Message);
        }
    }
}
```

---

### **Exception Hierarchy**

C# exceptions derive from the base class `System.Exception`. Common exceptions include:
- **`System.Exception`**: Base class for exceptions.
- **`System.ApplicationException`**: Used for application-defined exceptions.
- **`System.SystemException`**: Used for system-defined exceptions.
    - **`DivideByZeroException`**
    - **`NullReferenceException`**
    - **`IndexOutOfRangeException`**

---

### **Best Practices for Exception Handling**
1. **Be Specific**: Catch specific exceptions instead of using a generic `catch`.
2. **Avoid Silent Fails**: Do not catch exceptions without handling them or logging the issue.
3. **Use `finally` Wisely**: Use it for cleanup operations like closing files or releasing resources.
4. **Don't Overuse Exceptions**: Use exceptions for exceptional cases, not for normal program flow.
5. **Log Errors**: Always log exceptions for debugging and monitoring purposes.
6. **Rethrow Exceptions**: Use `throw;` inside a `catch` block to preserve the stack trace.

---

### **Practice Tasks**
1. Write a program that accepts two integers from the user and divides them. Handle exceptions like invalid input and divide by zero.
2. Create a custom exception for invalid bank transactions (e.g., withdrawing more than the balance).
3. Write a program to read a file. Handle exceptions if the file is not found or inaccessible.

Let me know which task you'd like to start with! 🚀