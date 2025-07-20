# 📦 Creating a DLL (Class Library) in C#

---

## 📌 Overview

A **DLL (Dynamic Link Library)** is a compiled library that can be referenced by multiple applications to share reusable code.

In C#, DLLs are created as **Class Library projects**.

---

## 1️⃣ Create a Class Library Project

```bash
dotnet new classlib -o MyLibrary
cd MyLibrary
```

This command creates a new C# class library project with the folder `MyLibrary`.

---

## 2️⃣ Example Class Code (`Calculator.cs`)

```csharp
namespace MyLibrary
{
    public class Calculator
    {
        public int Add(int a, int b) => a + b;

        public int Multiply(int a, int b) => a * b;
    }
}
```

---

## 3️⃣ Build the DLL

```bash
dotnet build -c Release
```

After building, the DLL will be in:

```
MyLibrary/bin/Release/net7.0/MyLibrary.dll
```

---

## 4️⃣ Reference the DLL in Another Project

### a) Create a Console App

```bash
dotnet new console -o MyApp
cd MyApp
```

### b) Add Project Reference (recommended)

If both projects are in the same solution, add a project reference:

```bash
dotnet add reference ../MyLibrary/MyLibrary.csproj
```

### c) Or add DLL reference (less common)

Copy the DLL file and reference it manually:

```bash
dotnet add package <local DLL path>  # Not typical, better use project references
```

---

## 5️⃣ Use the DLL in Code (`Program.cs`)

```csharp
using System;
using MyLibrary;

class Program
{
    static void Main()
    {
        var calc = new Calculator();
        Console.WriteLine(calc.Add(5, 3));       // Output: 8
        Console.WriteLine(calc.Multiply(5, 3));  // Output: 15
    }
}
```

---

## 6️⃣ Run the Application

```bash
dotnet run
```

---

## 📊 Summary

| Step                 | Command / Action                        |
|----------------------|---------------------------------------|
| Create library       | `dotnet new classlib`                  |
| Write code           | Create classes and methods             |
| Build DLL            | `dotnet build -c Release`              |
| Create consumer app  | `dotnet new console`                   |
| Add reference        | `dotnet add reference <path-to-lib>`  |
| Use DLL              | `using` directive + instantiate classes|
| Run app              | `dotnet run`                          |

---

## 📚 References

- [Microsoft Docs - Create a class library](https://learn.microsoft.com/en-us/dotnet/core/tutorials/library-with-visual-studio-code)
- [Project-to-project references](https://learn.microsoft.com/en-us/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
