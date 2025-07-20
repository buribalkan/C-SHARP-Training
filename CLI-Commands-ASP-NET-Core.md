# 🛠️ .NET EF CLI & ASP.NET Core Project Commands

---

## ⚙️ Installing `dotnet ef` Tool

```bash
dotnet tool install --global dotnet-ef
```

_Update the tool later with:_

```bash
dotnet tool update --global dotnet-ef
```

---

## 📦 Adding EF Core Packages to Your Project

```bash
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

---

## 🔧 Common `dotnet ef` Commands

| Command                              | Description                                         | Example                                  |
|------------------------------------|-----------------------------------------------------|-----------------------------------------|
| `dotnet ef migrations add <Name>`  | Create a new migration                              | `dotnet ef migrations add InitialCreate` |
| `dotnet ef migrations list`         | List existing migrations                            | `dotnet ef migrations list`              |
| `dotnet ef migrations remove`       | Remove the last migration                           | `dotnet ef migrations remove`            |
| `dotnet ef database update`         | Apply migrations to database                        | `dotnet ef database update`              |
| `dotnet ef database drop`           | Drop the database                                  | `dotnet ef database drop`                |
| `dotnet ef dbcontext info`          | Show DbContext info                                | `dotnet ef dbcontext info`               |
| `dotnet ef dbcontext scaffold`      | Scaffold models from existing DB                    | `dotnet ef dbcontext scaffold "<connection-string>" Microsoft.EntityFrameworkCore.SqlServer -o Models` |

---

## 🌐 ASP.NET Core Project Creation Commands

| Command                                | Description                                      | Example                                  |
|--------------------------------------|-------------------------------------------------|-----------------------------------------|
| `dotnet new webapi`                   | Create a new ASP.NET Core Web API project       | `dotnet new webapi -o MyWebApi`          |
| `dotnet new mvc`                      | Create a new ASP.NET Core MVC web app            | `dotnet new mvc -o MyMvcApp`              |
| `dotnet new razor`                    | Create a new Razor Pages web app                  | `dotnet new razor -o MyRazorApp`          |
| `dotnet new blazorserver`             | Create a Blazor Server app                        | `dotnet new blazorserver -o MyBlazorApp` |
| `dotnet new blazorwasm`               | Create a Blazor WebAssembly app                   | `dotnet new blazorwasm -o MyBlazorWasm`  |

---

## 🧰 Example Workflow: Create ASP.NET Core + EF Core

```bash
# Create new Web API project
dotnet new webapi -o MyApiApp
cd MyApiApp

# Add EF Core packages
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer

# Add initial migration
dotnet ef migrations add InitialCreate

# Update database
dotnet ef database update

# Run the app
dotnet run
```

---

## 📚 References

- [EF Core CLI Tools](https://learn.microsoft.com/en-us/ef/core/cli/dotnet)
- [ASP.NET Core project templates](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new)
- [Create ASP.NET Core apps](https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api)
