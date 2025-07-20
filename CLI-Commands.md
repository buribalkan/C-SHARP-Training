# 💻 .NET CLI (Command Line Interface) Commands

---

## 📌 Overview

The .NET CLI (`dotnet`) is a cross-platform tool for developing, building, running, and publishing .NET applications from the command line.

---

## 🔧 Common Commands

| Command                     | Description                                           | Example                              |
|-----------------------------|-------------------------------------------------------|-------------------------------------|
| `dotnet new`                | Create a new project or file                           | `dotnet new console -o MyApp`       |
| `dotnet build`              | Build a project                                        | `dotnet build MyApp.csproj`         |
| `dotnet run`                | Build and run application                             | `dotnet run`                        |
| `dotnet test`               | Run unit tests                                        | `dotnet test`                      |
| `dotnet publish`            | Publish app for deployment                            | `dotnet publish -c Release -o ./out` |
| `dotnet restore`            | Restore dependencies (NuGet packages)                | `dotnet restore`                   |
| `dotnet clean`              | Clean output of previous builds                       | `dotnet clean`                     |
| `dotnet add package`        | Add a NuGet package to a project                      | `dotnet add package Newtonsoft.Json` |
| `dotnet remove package`     | Remove a NuGet package                                | `dotnet remove package Newtonsoft.Json` |
| `dotnet list package`       | List installed NuGet packages                          | `dotnet list package`              |
| `dotnet --version`          | Show .NET SDK version                                 | `dotnet --version`                 |
| `dotnet help`               | Show help information                                 | `dotnet help`                     |

---

## 🛠 Project & Solution Management

| Command                     | Description                                           | Example                              |
|-----------------------------|-------------------------------------------------------|-------------------------------------|
| `dotnet new sln`            | Create a new solution file                            | `dotnet new sln -n MySolution`      |
| `dotnet sln add`            | Add project(s) to a solution                          | `dotnet sln MySolution.sln add MyApp/MyApp.csproj` |
| `dotnet sln remove`         | Remove project from solution                          | `dotnet sln MySolution.sln remove MyApp/MyApp.csproj` |

---

## 🧰 NuGet Package Commands

| Command                     | Description                                           | Example                              |
|-----------------------------|-------------------------------------------------------|-------------------------------------|
| `dotnet add package`        | Add NuGet package to a project                        | `dotnet add package Serilog`        |
| `dotnet remove package`     | Remove NuGet package                                  | `dotnet remove package Serilog`     |
| `dotnet restore`            | Restore all NuGet packages                            | `dotnet restore`                    |
| `dotnet list package`       | List packages installed in a project                  | `dotnet list package`               |

---

## 🔍 Useful Flags

| Flag              | Description                                    |
|-------------------|------------------------------------------------|
| `-o`, `--output`  | Specify output directory                        |
| `-c`, `--configuration` | Build configuration (Debug/Release)       |
| `-f`, `--framework`| Target framework (e.g., net6.0, net7.0)        |
| `--no-restore`    | Skip restoring packages                         |
| `-v`, `--verbosity`| Set verbosity level (quiet, minimal, normal, detailed, diagnostic) |

---

## 📦 Example Workflow

```bash
dotnet new webapi -o MyApi           # Create new Web API project
cd MyApi
dotnet add package Microsoft.EntityFrameworkCore.SqlServer  # Add EF Core package
dotnet build                         # Build project
dotnet run                          # Run the application
dotnet test                         # Run tests
dotnet publish -c Release -o ./publish  # Publish app for deployment
```

---

## 📚 References

- [Official .NET CLI Documentation](https://learn.microsoft.com/en-us/dotnet/core/tools/)
- [Dotnet CLI Commands Summary](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet)
