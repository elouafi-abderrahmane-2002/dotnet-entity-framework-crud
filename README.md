# 🗄️ .NET Entity Framework Core — CRUD Application

A full-stack web application built with **ASP.NET Core MVC** and **Entity Framework Core**, demonstrating complete CRUD operations with SQL Server, database migrations, and a clean layered architecture.

---

## 🚀 Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | ASP.NET Core 6 / C# |
| ORM | Entity Framework Core 6 |
| Database | SQL Server / LocalDB |
| Frontend | Razor Views / Bootstrap 5 |
| Migrations | EF Core Code-First |

---

## 📁 Project Structure

```
├── Controllers/          # MVC Controllers (CRUD actions)
├── Models/               # Domain entities & ViewModels
├── Data/
│   ├── AppDbContext.cs   # EF Core DbContext
│   └── Migrations/       # Auto-generated migrations
├── Views/                # Razor templates
└── Services/             # Business logic layer
```

---

## ✨ Features

- ✅ Full CRUD (Create, Read, Update, Delete)
- ✅ Entity Framework Core Code-First
- ✅ SQL Server with automatic migrations
- ✅ Model validation & error handling
- ✅ Entity relationships (One-to-Many, Many-to-Many)
- ✅ Pagination & search
- ✅ Bootstrap 5 responsive UI

---

## ⚙️ Getting Started

### Prerequisites
- .NET 6 SDK
- SQL Server or LocalDB
- EF Core CLI: `dotnet tool install --global dotnet-ef`

### Run locally

```bash
# Clone the repo
git clone https://github.com/elouafi-abderrahmane-2002/dotnet-entity-framework-crud.git
cd dotnet-entity-framework-crud

# Update appsettings.json with your connection string
"ConnectionStrings": {
  "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=CrudDb;Trusted_Connection=True;"
}

# Apply migrations
dotnet ef database update

# Run the app
dotnet run
```

Open `http://localhost:5000`

---

## 🗃️ Database Schema

```
Products
├── Id (PK)
├── Name
├── Description
├── Price
├── CategoryId (FK)
└── CreatedAt

Categories
├── Id (PK)
├── Name
└── Products (navigation)
```

---

## 📡 EF Core Key Concepts Used

```csharp
// DbContext configuration
modelBuilder.Entity<Product>()
    .HasOne(p => p.Category)
    .WithMany(c => c.Products)
    .HasForeignKey(p => p.CategoryId);

// Query with include
var products = await _context.Products
    .Include(p => p.Category)
    .ToListAsync();
```

---

## 👤 Author

**Abderrahmane ELOUAFI**  
[LinkedIn](https://www.linkedin.com/in/abderrahmane-elouafi-43226736b/) · [GitHub](https://github.com/elouafi-abderrahmane-2002) · [Portfolio](https://my-first-porfolio-six.vercel.app/)
