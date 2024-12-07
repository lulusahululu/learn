### **Control Flow in C#: Making Decisions and Repeating Tasks**

Control flow allows your program to make decisions and execute specific sections of code based on conditions or repeat tasks until certain conditions are met.

---

### **1. If-Else Statements**
Used to make decisions based on conditions.

#### **Syntax**
```csharp
if (condition)
{
    // Code to execute if condition is true
}
else if (anotherCondition)
{
    // Code to execute if anotherCondition is true
}
else
{
    // Code to execute if all conditions are false
}
```

#### **Example**
```csharp
int score = 85;

if (score >= 90)
{
    Console.WriteLine("Grade: A");
}
else if (score >= 75)
{
    Console.WriteLine("Grade: B");
}
else
{
    Console.WriteLine("Grade: C");
}
```

---

### **2. Switch Statements**
Used for selecting one of many possible code blocks to execute, based on the value of a variable.

#### **Syntax**
```csharp
switch (variable)
{
    case value1:
        // Code to execute for value1
        break;
    case value2:
        // Code to execute for value2
        break;
    default:
        // Code to execute if no cases match
        break;
}
```

#### **Example**
```csharp
string role = "Leader";

switch (role)
{
    case "Leader":
        Console.WriteLine("You are a leader!");
        break;
    case "Member":
        Console.WriteLine("You are a team member.");
        break;
    default:
        Console.WriteLine("Unknown role.");
        break;
}
```

---

### **3. Loops**
Loops are used to repeat a block of code multiple times.

#### **a. For Loop**
Repeats a block of code a specific number of times.

#### **Syntax**
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Count: " + i);
}
```

#### **Example**
```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine("Step: " + i);
}
```

---

#### **b. While Loop**
Repeats as long as a condition is true.

#### **Syntax**
```csharp
while (condition)
{
    // Code to execute while condition is true
}
```

#### **Example**
```csharp
int count = 1;
while (count <= 3)
{
    Console.WriteLine("Count: " + count);
    count++;
}
```

---

#### **c. Do-While Loop**
Executes the code at least once, then repeats while the condition is true.

#### **Syntax**
```csharp
do
{
    // Code to execute
} while (condition);
```

#### **Example**
```csharp
int num = 1;
do
{
    Console.WriteLine("Number: " + num);
    num++;
} while (num <= 3);
```

---

### **4. Break and Continue**
- **Break**: Exits the loop immediately.
- **Continue**: Skips the current iteration and moves to the next.

#### **Example**
```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
    {
        continue; // Skip printing 3
    }
    Console.WriteLine(i);
}
```

---

### **Practice Task**
1. Write an if-else program to check if a number is positive, negative, or zero.
2. Use a `for` loop to print numbers from 1 to 10.
3. Create a `while` loop that keeps running until the user enters a specific keyword (e.g., "exit").
4. Use a `switch` statement to print different messages for different roles (e.g., "Leader," "Member," "Guest").

Let me know when you're ready or if you have questions!