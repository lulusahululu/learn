### **Collections in C#: Managing Groups of Data**

Collections in C# are specialized classes for storing and managing groups of related objects. They provide more flexibility than arrays, allowing dynamic resizing and various operations like adding, removing, and searching items efficiently.

---

### **Types of Collections in C#**

C# collections can be broadly categorized into:
1. **Non-Generic Collections** (System.Collections)
2. **Generic Collections** (System.Collections.Generic)
3. **Concurrent Collections** (System.Collections.Concurrent)
4. **Specialized Collections** (System.Collections.Specialized)

We'll focus on the most common and useful ones.

---

### **Why Use Collections?**
1. **Dynamic Size**: Collections can grow or shrink dynamically.
2. **Ease of Use**: Simplified methods for common operations (e.g., Add, Remove, Sort).
3. **Efficient Management**: Provides optimized performance for data manipulation.

---

### **Non-Generic Collections**

Non-generic collections are legacy and use `object` as their data type. These are less type-safe as they rely on boxing/unboxing.

#### **Common Non-Generic Collections**
1. `ArrayList`: Similar to an array but dynamically resizable.
2. `Hashtable`: Stores key-value pairs.
3. `Queue`: First In First Out (FIFO).
4. `Stack`: Last In First Out (LIFO).

#### **Example: ArrayList**
```csharp
using System;
using System.Collections;

class Program
{
    static void Main(string[] args)
    {
        ArrayList list = new ArrayList();
        list.Add(1);
        list.Add("Two");
        list.Add(3.5);

        foreach (var item in list)
        {
            Console.WriteLine(item);
        }
    }
}
```

> **Limitation**: Non-generic collections should be avoided in modern C# projects due to type-safety concerns. Prefer generic collections.

---

### **Generic Collections**

Generic collections provide type-safety and better performance by avoiding boxing/unboxing.

#### **Common Generic Collections**
1. `List<T>`: A dynamic array that allows duplicate elements.
2. `Dictionary<TKey, TValue>`: A collection of key-value pairs.
3. `Queue<T>`: FIFO data structure.
4. `Stack<T>`: LIFO data structure.
5. `HashSet<T>`: A collection of unique items.
6. `LinkedList<T>`: Doubly linked list.

---

#### **1. List<T>**
A `List<T>` is a dynamic array that can store elements of a specific type.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        List<int> numbers = new List<int>();
        numbers.Add(10);
        numbers.Add(20);
        numbers.Add(30);

        Console.WriteLine("Count: " + numbers.Count);

        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }

        numbers.Remove(20);
        Console.WriteLine("After removing 20:");
        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }
    }
}
```

---

#### **2. Dictionary<TKey, TValue>**
A dictionary stores data in key-value pairs.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        Dictionary<int, string> students = new Dictionary<int, string>();
        students.Add(1, "Alice");
        students.Add(2, "Bob");

        Console.WriteLine("Student with ID 1: " + students[1]);

        foreach (var pair in students)
        {
            Console.WriteLine($"ID: {pair.Key}, Name: {pair.Value}");
        }
    }
}
```

---

#### **3. Queue<T>**
A queue follows the **FIFO** (First In First Out) principle.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        Queue<string> queue = new Queue<string>();
        queue.Enqueue("Task 1");
        queue.Enqueue("Task 2");
        queue.Enqueue("Task 3");

        Console.WriteLine("Dequeued: " + queue.Dequeue());

        foreach (var task in queue)
        {
            Console.WriteLine(task);
        }
    }
}
```

---

#### **4. Stack<T>**
A stack follows the **LIFO** (Last In First Out) principle.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        Stack<string> stack = new Stack<string>();
        stack.Push("Page 1");
        stack.Push("Page 2");
        stack.Push("Page 3");

        Console.WriteLine("Popped: " + stack.Pop());

        foreach (var page in stack)
        {
            Console.WriteLine(page);
        }
    }
}
```

---

#### **5. HashSet<T>**
A `HashSet<T>` stores unique elements.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        HashSet<int> set = new HashSet<int>();
        set.Add(1);
        set.Add(2);
        set.Add(2); // Duplicate, will be ignored

        foreach (var item in set)
        {
            Console.WriteLine(item);
        }
    }
}
```

---

#### **6. LinkedList<T>**
A `LinkedList<T>` is a doubly linked list allowing fast insertion and deletion.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        LinkedList<string> list = new LinkedList<string>();
        list.AddLast("First");
        list.AddLast("Second");
        list.AddFirst("Zeroth");

        foreach (var item in list)
        {
            Console.WriteLine(item);
        }
    }
}
```

---

### **Concurrent Collections**

For multi-threaded applications, C# provides thread-safe collections in the `System.Collections.Concurrent` namespace.

#### **Examples**
1. `ConcurrentBag<T>`
2. `ConcurrentQueue<T>`
3. `ConcurrentDictionary<TKey, TValue>`

---

### **Specialized Collections**

The `System.Collections.Specialized` namespace includes collections like:
1. `NameValueCollection`: Stores key-value pairs where keys and values are strings.
2. `StringCollection`: Stores strings.

---

### **When to Use Which Collection**
| Collection         | Use Case                                                                 |
|---------------------|--------------------------------------------------------------------------|
| **List<T>**         | When you need a dynamic array.                                           |
| **Dictionary<TKey, TValue>** | When you need key-value pair storage.                             |
| **Queue<T>**        | When you need FIFO behavior (e.g., task scheduling).                     |
| **Stack<T>**        | When you need LIFO behavior (e.g., undo functionality).                  |
| **HashSet<T>**      | When you need to store unique elements.                                  |
| **LinkedList<T>**   | When you need efficient insertion/deletion in a list.                   |
| **ConcurrentBag<T>**| When you need thread-safe unordered data storage.                        |

---

### **Practice Tasks**
1. Create a `List<int>` to store and print the first 10 even numbers.
2. Use a `Dictionary<string, string>` to map country names to their capitals.
3. Create a `Queue<string>` to simulate a ticketing system and dequeue customers.
4. Use a `HashSet<string>` to store a list of unique usernames.
5. Implement a `Stack<string>` to manage a browser history feature.

Let me know which area you'd like to explore further! 🚀