# 📚 Dictionaries in C#

A **Dictionary** in C# is a generic collection that stores **key-value pairs**. It allows **fast lookups**, additions, and deletions using a unique key.

---

## 🧱 Declaration

```csharp
// Using string as key and int as value
Dictionary<string, int> ages = new Dictionary<string, int>();
```

You can also use shorthand syntax with target-typed new (C# 9.0+):

```csharp
var scores = new Dictionary<string, double>
{
    { "Math", 95.5 },
    { "Science", 89.0 }
};
```

---

## ✅ Basic Operations

| Operation         | Code Example |
|------------------|--------------|
| Add item         | `dict.Add("Tom", 30);` |
| Get value        | `int age = dict["Tom"];` |
| Update value     | `dict["Tom"] = 31;` |
| Check existence  | `dict.ContainsKey("Tom");` |
| Remove item      | `dict.Remove("Tom");` |

---

## 🧪 Example

```csharp
var phoneBook = new Dictionary<string, string>();

phoneBook.Add("Alice", "555-1234");
phoneBook["Bob"] = "555-5678";  // Add or update

Console.WriteLine(phoneBook["Alice"]); // Output: 555-1234

if (phoneBook.ContainsKey("Charlie"))
{
    Console.WriteLine(phoneBook["Charlie"]);
}
else
{
    Console.WriteLine("Not found.");
}
```

---

## 🔁 Iterating Over Dictionary

```csharp
foreach (var entry in phoneBook)
{
    Console.WriteLine($"{entry.Key}: {entry.Value}");
}
```

---

## 🚫 Common Mistakes

| Mistake                                 | Why it's wrong                           |
|-----------------------------------------|-------------------------------------------|
| Accessing a key that doesn't exist      | Throws `KeyNotFoundException`             |
| Adding duplicate keys                   | Throws `ArgumentException`                |
| Using mutable objects as keys           | May cause unexpected lookup behavior      |

---

## 🛡️ Safe Lookup

Instead of accessing directly, use `TryGetValue`:

```csharp
if (phoneBook.TryGetValue("Dave", out string number))
{
    Console.WriteLine($"Dave's number: {number}");
}
else
{
    Console.WriteLine("Dave not found.");
}
```

---

## 🧠 Key Features

| Feature           | Description                           |
|-------------------|---------------------------------------|
| Fast lookup       | O(1) average-case lookup time         |
| Unique keys       | No duplicate keys allowed             |
| Generic           | Can use any type for key/value        |
| Not ordered       | No guarantee of order                 |

---

## 📦 Real-World Use Case

### Counting Words in a Sentence

```csharp
string text = "hello world hello code";
var wordCounts = new Dictionary<string, int>();

foreach (var word in text.Split(' '))
{
    if (wordCounts.ContainsKey(word))
        wordCounts[word]++;
    else
        wordCounts[word] = 1;
}

foreach (var pair in wordCounts)
{
    Console.WriteLine($"{pair.Key}: {pair.Value}");
}
```

Output:
```
hello: 2  
world: 1  
code: 1
```

---

## 🧾 Summary

| Feature               | Description                     |
|------------------------|---------------------------------|
| Lookup by key          | ✅ Yes                          |
| Allows duplicates      | ❌ Keys must be unique          |
| Ordered                | ❌ No (use `SortedDictionary`)  |
| Fast performance       | ✅ On average                   |
| Null keys allowed?     | ❌ Not for reference types      |

---
