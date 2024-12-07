### **Functions and Methods in C#: Reusable Blocks of Code**

Functions (also called methods in C#) are blocks of code designed to perform specific tasks. They help make your code reusable and organized.

---

### **1. Defining a Method**
A method consists of:
1. **Return Type**: The type of data the method returns (e.g., `int`, `string`). Use `void` if no value is returned.
2. **Method Name**: The name you call the method by.
3. **Parameters (optional)**: Inputs the method accepts.
4. **Body**: The code block executed when the method is called.

#### **Syntax**
```csharp
returnType MethodName(parameters)
{
    // Code to execute
    return value; // If not void
}
```

#### **Example**
```csharp
// Method with no return value (void)
void Greet()
{
    Console.WriteLine("Hello, Welcome!");
}

// Method with a return value
int AddNumbers(int a, int b)
{
    return a + b;
}
```

---

### **2. Calling a Method**
To execute a method, you "call" it by its name and pass any required arguments.

#### **Example**
```csharp
class Program
{
    static void Main(string[] args)
    {
        Greet(); // Call the Greet method

        int result = AddNumbers(5, 10); // Call AddNumbers and store the result
        Console.WriteLine("Sum: " + result);
    }

    static void Greet()
    {
        Console.WriteLine("Hello, Welcome!");
    }

    static int AddNumbers(int a, int b)
    {
        return a + b;
    }
}
```

---

### **3. Parameters**
Parameters allow you to pass data into methods.

#### **a. Required Parameters**
Parameters that must be provided when calling a method.

```csharp
void PrintName(string name)
{
    Console.WriteLine("Name: " + name);
}

// Call the method
PrintName("Lulu");
```

#### **b. Default Parameters**
Optional parameters with default values.

```csharp
void DisplayInfo(string name, int age = 18)
{
    Console.WriteLine("Name: " + name + ", Age: " + age);
}

// Call the method
DisplayInfo("Lulu"); // Age defaults to 18
DisplayInfo("Sahu", 25); // Age is overridden to 25
```

---

### **4. Method Overloading**
You can define multiple methods with the same name but different parameter types or counts.

#### **Example**
```csharp
int Multiply(int a, int b)
{
    return a * b;
}

float Multiply(float a, float b)
{
    return a * b;
}

// Call the overloaded methods
Console.WriteLine(Multiply(2, 3)); // Calls the int version
Console.WriteLine(Multiply(2.5f, 3.5f)); // Calls the float version
```

---

### **5. Return Values**
A method can return a value using the `return` keyword. The return type must match the declared type.

#### **Example**
```csharp
bool IsEven(int number)
{
    return number % 2 == 0;
}

// Call the method
if (IsEven(4))
{
    Console.WriteLine("Number is even.");
}
else
{
    Console.WriteLine("Number is odd.");
}
```

---

### **6. Static vs Non-Static Methods**
- **Static methods** belong to the class and can be called without creating an object.
- **Non-static methods** require an object instance to call them.

#### **Example**
```csharp
class Calculator
{
    public int Subtract(int a, int b) // Non-static
    {
        return a - b;
    }

    public static int Add(int a, int b) // Static
    {
        return a + b;
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Call static method
        Console.WriteLine(Calculator.Add(5, 3));

        // Call non-static method
        Calculator calc = new Calculator();
        Console.WriteLine(calc.Subtract(5, 3));
    }
}
```

---

### **Practice Tasks**
1. Write a method that takes two numbers as input and returns their product.
2. Create a method that accepts your name and age and prints a personalized greeting.
3. Write a program with overloaded methods for finding the square of an integer and a float.
4. Build a program that checks if a number is prime using a method.

Let me know where you'd like to dive deeper or if you're ready to practice!