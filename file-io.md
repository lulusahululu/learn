
### File I/O Overview

File Input/Output (I/O) is a fundamental concept in C# programming that allows you to read and write data to files. C# provides several classes and methods to perform file operations, including reading, writing, creating, deleting, and copying files.

### File Streams

In C#, a file stream is a sequence of bytes that can be read or written to a file. There are several types of file streams, including:

*   `FileStream`: A stream that reads and writes files on disk.
*   `MemoryStream`: A stream that reads and writes data to memory.
*   `BufferedStream`: A stream that reads and writes data to a buffer.

### Reading from a File

To read from a file in C#, you can use the `File` class or the `FileStream` class.

#### Using the `File` Class

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Read all text from the file
        string fileContent = File.ReadAllText(filePath);

        // Display the file content
        Console.WriteLine(fileContent);
    }
}
```

#### Using the `FileStream` Class

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Create a file stream to read from the file
        using (FileStream fileStream = new FileStream(filePath, FileMode.Open))
        {
            // Create a binary reader to read the file
            using (BinaryReader binaryReader = new BinaryReader(fileStream))
            {
                // Read all bytes from the file
                byte[] fileBytes = new byte[fileStream.Length];
                binaryReader.Read(fileBytes, 0, (int)fileStream.Length);

                // Convert the bytes to a string
                string fileContent = System.Text.Encoding.UTF8.GetString(fileBytes);

                // Display the file content
                Console.WriteLine(fileContent);
            }
        }
    }
}
```

### Writing to a File

To write to a file in C#, you can use the `File` class or the `FileStream` class.

#### Using the `File` Class

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Specify the content to write to the file
        string fileContent = "Hello, World!";

        // Write the content to the file
        File.WriteAllText(filePath, fileContent);
    }
}
```

#### Using the `FileStream` Class

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Specify the content to write to the file
        string fileContent = "Hello, World!";

        // Create a file stream to write to the file
        using (FileStream fileStream = new FileStream(filePath, FileMode.Create))
        {
            // Create a binary writer to write to the file
            using (BinaryWriter binaryWriter = new BinaryWriter(fileStream))
            {
                // Write the content to the file
                binaryWriter.Write(System.Text.Encoding.UTF8.GetBytes(fileContent));
            }
        }
    }
}
```

### Copying a File

To copy a file in C#, you can use the `File` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the source file path
        string sourceFilePath = @"C:\Example.txt";

        // Specify the destination file path
        string destinationFilePath = @"C:\CopiedExample.txt";

        // Copy the file
        File.Copy(sourceFilePath, destinationFilePath);
    }
}
```

### Deleting a File

To delete a file in C#, you can use the `File` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Delete the file
        File.Delete(filePath);
    }
}
```

### Checking if a File Exists

To check if a file exists in C#, you can use the `File` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Check if the file exists
        if (File.Exists(filePath))
        {
            Console.WriteLine("The file exists.");
        }
        else
        {
            Console.WriteLine("The file does not exist.");
        }
    }
}
```

### Getting File Information

To get file information in C#, you can use the `FileInfo` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the file path
        string filePath = @"C:\Example.txt";

        // Create a FileInfo object to get file information
        FileInfo fileInfo = new FileInfo(filePath);

        // Display file information
        Console.WriteLine("File Name: " + fileInfo.Name);
        Console.WriteLine("File Extension: " + fileInfo.Extension);
        Console.WriteLine("File Length: " + fileInfo.Length);
        Console.WriteLine("File Creation Time: " + fileInfo.CreationTime);
        Console.WriteLine("File Last Write Time: " + fileInfo.LastWriteTime);
        Console.WriteLine("File Last Access Time: " + fileInfo.LastAccessTime);
    }
}
```

### Creating a Directory

To create a directory in C#, you can use the `Directory` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\ExampleDirectory";

        // Create the directory
        Directory.CreateDirectory(directoryPath);
    }
}
```

### Deleting a Directory

To delete a directory in C#, you can use the `Directory` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\ExampleDirectory";

        // Delete the directory
        Directory.Delete(directoryPath);
    }
}
```

### Checking if a Directory Exists

To check if a directory exists in C#, you can use the `Directory` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\ExampleDirectory";

        // Check if the directory exists
        if (Directory.Exists(directoryPath))
        {
            Console.WriteLine("The directory exists.");
        }
        else
        {
            Console.WriteLine("The directory does not exist.");
        }
    }
}
```

### Getting Directory Information

To get directory information in C#, you can use the `DirectoryInfo` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\ExampleDirectory";

        // Create a DirectoryInfo object to get directory information
        DirectoryInfo directoryInfo = new DirectoryInfo(directoryPath);

        // Display directory information
        Console.WriteLine("Directory Name: " + directoryInfo.Name);
        Console.WriteLine("Directory Parent: " + directoryInfo.Parent);
        Console.WriteLine("Directory Root: " + directoryInfo.Root);
        Console.WriteLine("Directory Creation Time: " + directoryInfo.CreationTime);
        Console.WriteLine("Directory Last Write Time: " + directoryInfo.LastWriteTime);
        Console.WriteLine("Directory Last Access Time: " + directoryInfo.LastAccessTime);
    }
}
```

### Enumerating Files and Directories

To enumerate files and directories in C#, you can use the `Directory` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\";

        // Enumerate files in the directory
        string[] files = Directory.GetFiles(directoryPath);
        foreach (string file in files)
        {
            Console.WriteLine(file);
        }

        // Enumerate directories in the directory
        string[] directories = Directory.GetDirectories(directoryPath);
        foreach (string directory in directories)
        {
            Console.WriteLine(directory);
        }
    }
}
```

### Watching for File System Changes

To watch for file system changes in C#, you can use the `FileSystemWatcher` class.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        // Specify the directory path
        string directoryPath = @"C:\";

        // Create a file system watcher to watch for changes
        FileSystemWatcher fileSystemWatcher = new FileSystemWatcher(directoryPath);

        // Set the filter to watch for all files
        fileSystemWatcher.Filter = "*.*";

        // Set the notification filter to watch for all changes
        fileSystemWatcher.NotifyFilter = NotifyFilters.FileName | NotifyFilters.LastWrite;

        // Set the event handler for the changed event
        fileSystemWatcher.Changed += new FileSystemEventHandler(OnChanged);

        // Start watching for changes
        fileSystemWatcher.EnableRaisingEvents = true;

        // Wait for changes
        Console.WriteLine("Watching for changes...");
        Console.ReadLine();
    }

    static void OnChanged(object source, FileSystemEventArgs e)
    {
        Console.WriteLine("File changed: " + e.FullPath);
    }
}
```

This is a comprehensive overview of the file I/O capabilities in C#. With the provided examples and explanations, you should be able to perform various file operations, including reading, writing, copying, deleting, and watching for changes.
Exception: 'ChatCompletion' object has no attribute 'save'