# 🧠 Mutable vs Immutable Types in C#



---



## 📌 What Does It Mean?





**Mutability** refers to whether or not the state or content of an object or data structure can be changed after it is created. Understanding whether a piece of data is mutable (can be modified) or immutable (cannot be modified) is crucial in programming, as it influences how data is handled and manipulated.

- **Mutable** objects **can be changed** after creation.

- **Immutable** objects **cannot be changed** — any modification creates a **new instance**.
---



## 🧪 Immutable Types in C#



In .NET, most built-in types such as:



- `string`

- `System.DateTime`

- `System.Guid`



...are **immutable**.



### Example: `string` is Immutable



```csharp

string a = "Hello";
string b = a;
a = a + " World";
Console.WriteLine(b); // Output: "Hello"

```

🔍 `a` was modified, but `b` still holds the original value.

---



## 🔧 Mutable Types in C#



Most **classes** and **structs** that you define yourself are **mutable** by default unless you restrict them.



### Example: Mutable Class



```csharp

class Person
{
    public string Name { get; set; }
}

var p = new Person { Name = "Alice" };
p.Name = "Bob"; // Object modified!

```



---



## 🧱 Structs Are Value Types



- Structs are **copied by value**, but **still mutable** unless made `readonly`.



```csharp

struct Point
{
    public int X;
    public int Y;
}

var pt = new Point { X = 1, Y = 2 };
pt.X = 5; // Mutable

```



---



## 🔐 Creating Immutable Types (Custom)



Use `readonly` and private setters:



```csharp

class ImmutablePerson
{
    public string Name { get; }
    public int Age { get; }
    public ImmutablePerson(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

```



Or use a `record` (C# 9.0+):



```csharp

public record Product(string Name, decimal Price);

```



---



## 📊 Comparison Table



| Feature             | Mutable                           | Immutable                           |
|---------------------|-----------------------------------|--------------------------------------|
| Can change data?    | ✅ Yes                            | ❌ No                                 |
| Thread-safe         | ❌ Usually No                     | ✅ Often Yes                          |
| Memory efficient    | ❌ Modifying may cause issues     | ✅ Reuse and caching possible         |
| Example type        | `List<T>`, `Person` class         | `string`, `DateTime`, `record` types |



---



## 📈 Diagram — Mutation Behavior



```mermaid

sequenceDiagram

    participant Dev as Developer

    participant Obj as Object (Mutable)

    participant ImObj as Object (Immutable)



    Dev->>Obj: Change value

    Obj-->>Dev: Value updated in place



    Dev->>ImObj: Change value

    ImObj-->>Dev: Creates new object with new value

```



---



## ⚠️ When to Use What?



| Situation                                 | Recommended Type |
|-------------------------------------------|------------------|
| Data that changes often                   | Mutable          |
| Shared state in multithreading            | Immutable         |
| Logging, versioned objects, snapshots     | Immutable         |
| Performance-critical with large updates   | Mutable (carefully)



---



## ✅ Summary



- Immutable types are safer and easier to reason about.

- Mutable types offer flexibility but can introduce bugs if not handled with care.

- Prefer immutable types unless mutation is explicitly required.
