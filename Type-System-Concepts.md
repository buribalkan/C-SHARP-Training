# C# Type System Concepts: `typeof`, `is`, `as`, Boxing, Nullable



---



## 1. `typeof`



The `typeof` operator is used to get the `System.Type` object of a type at compile-time.



```csharp

Type t = typeof(int);
Console.WriteLine(t.FullName); // Output: System.Int32

```



---



## 2. `is`



The `is` operator checks if an object is of a given type. It returns `true` or `false`.



```csharp

object obj = "hello";
if (obj is string)
{
    Console.WriteLine("It's a string");
}

```



### Pattern Matching with `is` (C# 7.0+)



```csharp

if (obj is string s)
{
    Console.WriteLine($"String length: {s.Length}");
}

```



---



## 3. `as`



The `as` operator attempts to cast an object to a specific type. If it fails, it returns `null` instead of throwing an exception.



```csharp

object obj = "hello";
string s = obj as string;

if (s != null)
{
    Console.WriteLine("Cast succeeded");
}

```



---



## 4. Boxing and Unboxing



**Boxing** is the process of converting a value type (e.g., `int`, `bool`) into an `object`.



**Unboxing** is the process of converting the `object` back to a value type.



```csharp

int x = 42;
object boxed = x;         // Boxing
int y = (int)boxed;       // Unboxing

```



🔔 Improper unboxing causes runtime exceptions:



```csharp

object o = 42;
string s = (string)o; // InvalidCastException

```



---



## 5. Nullable Types



Used to represent **value types that can be null**. Defined using `?` or `Nullable<T>`.



```csharp

int? a = null;

if (a.HasValue)
{
    Console.WriteLine(a.Value);
}
else
{
    Console.WriteLine("No value");
}

```



✅ Useful for optional value fields like database columns, UI input, etc.



---



## 🔁 Summary Table



| Feature        | Description                                 | Example                    |
|----------------|---------------------------------------------|----------------------------|
| `typeof`       | Get type at compile-time                    | `typeof(int)`              |
| `is`           | Check object type safely                    | `if (obj is string)`       |
| `as`           | Safe cast, returns null if fails            | `obj as string`            |
| Boxing         | Value type to `object`                      | `object o = 42`            |
| Unboxing       | `object` to value type                      | `int x = (int)o`           |
| Nullable types | Value types that allow `null`               | `int? a = null`            |



---







---



## 🧪 Common Mistakes



- Using `as` with value types → ❌ `int x = obj as int` is invalid

- Forgetting null check on nullable types

- Unboxing to wrong type → throws `InvalidCastException`



---



## ✅ Best Practices



- Prefer pattern matching with `is`

- Use `as` only when null checks are acceptable

- Be cautious when boxing/unboxing in performance-critical code
