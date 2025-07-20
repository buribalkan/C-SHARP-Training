# 🛠️ `dotnet ef` CLI Commands & Installation Guide

---

## 📌 What is `dotnet ef`?

`dotnet ef` is the **Entity Framework Core CLI tool** used for managing EF Core migrations, database updates, scaffolding, and more — all from the command line.

---

## ⚙️ Installation

### 1. Install the EF Core CLI tool globally

```bash
dotnet tool install --global dotnet-ef
```

> To update the tool later, use:
>
> ```bash
> dotnet tool update --global dotnet-ef
> ```

### 2. Add EF Core packages to your project

At minimum, add the EF Core design package and the database provider (e.g., SQL Server):

```bash
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

---

## 🔧 Common `dotnet ef` Commands

| Command                          | Description                                             | Example                              |
|---------------------------------|---------------------------------------------------------|-------------------------------------|
| `dotnet ef migrations add <Name>` | Create a new migration                                 | `dotnet ef migrations add InitialCreate` |
| `dotnet ef migrations list`      | List existing migrations                                | `dotnet ef migrations list`          |
| `dotnet ef migrations remove`    | Remove the last migration                               | `dotnet ef migrations remove`        |
| `dotnet ef database update`      | Apply migrations to database                            | `dotnet ef database update`          |
| `dotnet ef database drop`        | Drop the database                                      | `dotnet ef database drop`            |
| `dotnet ef dbcontext info`       | Show info about the DbContext                          | `dotnet ef dbcontext info`           |
| `dotnet ef dbcontext scaffold`   | Reverse engineer database to generate models (scaffold) | `dotnet ef dbcontext scaffold "YourConnectionString" Microsoft.EntityFrameworkCore.SqlServer -o Models` |

---

## 🧰 Example Workflow

```bash
# Install EF Core CLI tool globally (once)
dotnet tool install --global dotnet-ef

# Add EF Core packages to your project
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer

# Add a migration named 'InitialCreate'
dotnet ef migrations add InitialCreate

# Update the database to latest migration
dotnet ef database update

# List migrations
dotnet ef migrations list

# Remove last migration (if needed)
dotnet ef migrations remove

# Scaffold models from existing database
dotnet ef dbcontext scaffold "Server=.;Database=MyDb;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -o Models
```

---

## 📝 Notes

- Run these commands **inside your project folder** where your `.csproj` exists.
- Connection strings for scaffold commands should be properly escaped or quoted.
- You can specify the startup project or project explicitly via options like:
  - `--project <PROJECT_PATH>`
  - `--startup-project <STARTUP_PROJECT_PATH>`

---

## 📚 References

- [EF Core Tools Documentation](https://learn.microsoft.com/en-us/ef/core/cli/dotnet)
- [Installing EF Core CLI tools](https://learn.microsoft.com/en-us/ef/core/cli/dotnet#installing-the-tools)
- [Reverse Engineering (Scaffolding)](https://learn.microsoft.com/en-us/ef/core/managing-schemas/scaffolding)
