# 📚 Indexers in C#

In C#, an **indexer** allows an object to be indexed like an array using square brackets `[]`. This is useful when your class stores a collection of values and you want intuitive, array-like access to them.

---

## 🔧 Syntax

```csharp
public class ClassName
{
    private Type[] items = new Type[Size];

    public Type this[int index]
    {
        get { return items[index]; }
        set { items[index] = value; }
    }
}
```

---

## ✅ Simple Example

```csharp
public class Week
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public string this[int index]
    {
        get { return days[index]; }
        set { days[index] = value; }
    }
}
```

### 🧪 Usage

```csharp
Week week = new Week();

Console.WriteLine(week[0]); // Output: Sun
week[0] = "Sunday";
Console.WriteLine(week[0]); // Output: Sunday
```

---

## 🔄 Indexer with String Key

You can overload the indexer to work with different key types like `string`:

```csharp
public class PhoneBook
{
    private Dictionary<string, string> contacts = new();

    public string this[string name]
    {
        get => contacts.ContainsKey(name) ? contacts[name] : "Not Found";
        set => contacts[name] = value;
    }
}
```

### 🧪 Usage

```csharp
var book = new PhoneBook();
book["Alice"] = "555-1234";
Console.WriteLine(book["Alice"]);     // Output: 555-1234
Console.WriteLine(book["Bob"]);       // Output: Not Found
```

---

## 🧠 Key Points

- Indexers **do not have a name** (like methods do), they're defined using the `this` keyword.
- Can be **overloaded** (e.g., `this[int index]`, `this[string key]`).
- Useful for creating **custom collections** or **wrapping arrays/lists**.

---

## 🧱 Real-World Use Case

### Custom collection wrapper:

```csharp
public class TemperatureLog
{
    private Dictionary<DateTime, double> data = new();

    public double this[DateTime date]
    {
        get => data.ContainsKey(date) ? data[date] : double.NaN;
        set => data[date] = value;
    }
}
```

```csharp
var log = new TemperatureLog();
log[DateTime.Today] = 36.6;
Console.WriteLine(log[DateTime.Today]); // Output: 36.6
```

---

## 🚫 Common Mistakes

| Mistake | Why it’s wrong |
|--------|----------------|
| Using indexer without initializing array/dictionary | Will throw `NullReferenceException` |
| Not checking for key existence in dictionary-based indexer | Might throw `KeyNotFoundException` |

---

## 🧾 Summary

| Feature        | Indexer                |
|----------------|------------------------|
| Uses `this`    | ✅ Yes                  |
| Return Type    | Defined by developer   |
| Parameters     | One or more indexes    |
| Overloadable   | ✅ Yes                  |
| Real-world use | Custom collections     |

---
