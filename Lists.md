# 📚 List in C#

A **List<T>** in C# is a generic collection class from `System.Collections.Generic` that allows dynamic resizing and provides various useful methods for working with ordered data.

---

## 🧱 Declaration

```csharp
// Empty list of integers
List<int> numbers = new List<int>();

// List with initial values
var fruits = new List<string> { "Apple", "Banana", "Orange" };
```

---

## ✅ Basic Operations

| Operation         | Code Example |
|------------------|--------------|
| Add item         | `list.Add("Mango");` |
| Access by index  | `list[0];` |
| Update by index  | `list[1] = "Peach";` |
| Insert at index  | `list.Insert(1, "Grape");` |
| Remove by value  | `list.Remove("Banana");` |
| Remove by index  | `list.RemoveAt(0);` |
| Count elements   | `list.Count;` |
| Check existence  | `list.Contains("Apple");` |

---

## 🧪 Example

```csharp
var colors = new List<string>();

colors.Add("Red");
colors.Add("Green");
colors.Add("Blue");

Console.WriteLine(colors[0]); // Output: Red

colors[1] = "Yellow"; // Update
colors.Remove("Red"); // Remove item

foreach (var color in colors)
{
    Console.WriteLine(color);
}
```

---

## 🔄 Iteration

```csharp
foreach (var item in list)
{
    Console.WriteLine(item);
}
```

Or using `for` loop:

```csharp
for (int i = 0; i < list.Count; i++)
{
    Console.WriteLine(list[i]);
}
```

---

## 🔍 Searching & Filtering

```csharp
var numbers = new List<int> { 5, 10, 15, 20 };

// Find first match
int result = numbers.Find(n => n > 10); // 15

// Find all matches
var filtered = numbers.FindAll(n => n > 10); // [15, 20]
```

---

## 🧠 Key Features

| Feature            | Description                            |
|--------------------|----------------------------------------|
| Index-based access | ✅ Yes                                 |
| Dynamic size       | ✅ Grows and shrinks as needed         |
| Type-safe          | ✅ Uses generics                       |
| Ordered            | ✅ Maintains insertion order           |

---

## 🚫 Common Mistakes

| Mistake                        | Why it's a problem                    |
|--------------------------------|---------------------------------------|
| Accessing invalid index        | Throws `ArgumentOutOfRangeException` |
| Modifying list while iterating | Can cause runtime errors             |

---

## 📦 Real-World Use Case

### Store and Process Usernames

```csharp
var usernames = new List<string>();

while (true)
{
    Console.Write("Enter a username (or 'exit'): ");
    string input = Console.ReadLine();
    if (input == "exit") break;
    usernames.Add(input);
}

Console.WriteLine("Registered users:");
foreach (var user in usernames)
{
    Console.WriteLine(user);
}
```

---

## 🧾 Summary

| Feature         | Description                   |
|------------------|-------------------------------|
| Access by index  | ✅ Yes                        |
| Dynamic resizing | ✅ Yes                        |
| Duplicates       | ✅ Allowed                    |
| Sorting          | ✅ Use `list.Sort()`          |
| Filtering        | ✅ Use LINQ or `FindAll()`    |

---
