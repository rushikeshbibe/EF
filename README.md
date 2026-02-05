ENTITY FRAMEWORK – INTERVIEW NOTES

What is Entity Framework (EF)?
Entity Framework is an ORM (Object-Relational Mapper) in C#.
It allows developers to work with databases using C# objects instead of writing SQL queries.
It acts as a bridge between C# classes and database tables.

Why Entity Framework is used?
Without EF, developers must:
- Write SQL queries
- Open and manage database connections
- Read data row by row
- Manually map database columns to C# objects

Entity Framework handles all these tasks automatically and reduces boilerplate code.

--------------------------------------------------

Main Components of Entity Framework

1. DbContext
- Represents the database
- Manages database connections and queries

Example:
public class AppDbContext : DbContext
{
    public DbSet<User> Users { get; set; }
}

--------------------------------------------------

2. DbSet
- Represents a table in the database
- Used for CRUD operations

Example:
DbSet<User> Users

--------------------------------------------------

3. LINQ
- Used to query data instead of SQL

Example:
var users = db.Users
              .Where(u => u.IsActive)
              .OrderBy(u => u.Name)
              .ToList();

--------------------------------------------------

Approaches in Entity Framework

1. Code First
- Write C# classes
- Entity Framework creates the database

Commands:
Add-Migration InitialCreate
Update-Database

2. Database First
- Database already exists
- Entity Framework generates C# classes

3. Model First
- Design model visually
- Entity Framework generates database and classes
- Rarely used

--------------------------------------------------

Advantages of Entity Framework
- Less SQL code
- Faster development
- Strongly typed (compile-time error checking)
- Easy CRUD operations

--------------------------------------------------

Disadvantages of Entity Framework
- Slight performance overhead
- Less control over generated SQL

--------------------------------------------------

Where Entity Framework is used
- ASP.NET MVC
- ASP.NET Core Web API
- Enterprise applications
- CRUD-based systems

--------------------------------------------------

One-line Interview Answer:
Entity Framework is a C# ORM that allows developers to interact with databases using C# objects instead of writing SQL queries.
