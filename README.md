# Product Management System

Aplikasi ini adalah implementasi CRUD (Create, Read, Update, Delete) sederhana menggunakan **.NET 10 MVC**, dibuat untuk memenuhi persyaratan seleksi di **PT. Akarsa Garment Indonesia**.

## Fitur Utama
- **Full CRUD**: Pengelolaan data produk (Create, Read, Update, Delete).
- **Search Function**: Fitur pencarian produk berdasarkan nama.
- **Responsive UI**: Menggunakan Bootstrap 5.
- **Portable Database**: Menggunakan SQLite (Database berbasis file), memudahkan review tanpa perlu setup SQL Server.
- **Data Validation**: Validasi input di sisi server dan client.
- **Stock Status Indicator**: Indikator visual untuk status stok (hijau/kuning/merah).

![Dashboard Product Management](Image%201/Dashboard%20Product%20Management.png)

![Add Product](Image%201/Add%20Product.png)

![Delete](Image%201/Delete.png)

![Hasil](Image%201/Hasil.png)

## Teknologi
- .NET 10 SDK
- Entity Framework Core (ORM)
- SQLite
- Bootstrap 5
- ASP.NET Core MVC

## Cara Menjalankan Aplikasi

Live demo : https://product-management-test-kappa.vercel.app/

### Prerequisites:
1. **Install .NET 10 SDK** dari: https://dotnet.microsoft.com/download/dotnet/10.0

### Steps:
1. **Clone atau Download repository ini**
   ```bash
   git clone https://github.com/lilbuu-glitch/product-management-test.git
   cd product-management-test
   ```

2. **Restore dependencies**
   ```bash
   dotnet restore
   ```

3. **Jalankan aplikasi**
   ```bash
   dotnet run
   ```

4. **Akses melalui browser**
   - Buka browser dan kunjungi: `http://localhost:5000`
   - Atau port lain yang muncul di terminal

*Database SQLite akan otomatis ter-generate saat aplikasi pertama kali dijalankan dengan nama `products.db`.*

## Fitur Detail

### 1. Product List (Index)
- Menampilkan semua produk dalam bentuk tabel
- Search bar untuk mencari produk berdasarkan nama
- Indikator stok dengan warna:
  - 🟢 Hijau: Stok > 10
  - 🟡 Kuning: Stok 5-10
  - 🔴 Merah: Stok < 5
- Tombol aksi untuk View, Edit, Delete

### 2. Create Product
- Form dengan validasi input
- Required fields: Name, Price, Stock
- Optional: Description
- Auto-generate CreatedAt dan UpdatedAt

### 3. Edit Product
- Pre-populated form dengan data existing
- Update UpdatedAt otomatis
- Validasi yang sama dengan Create

### 4. Product Details
- Tampilan detail lengkap produk
- Status stok dengan badge berwarna
- Timestamp untuk CreatedAt dan UpdatedAt

### 5. Delete Product
- Konfirmasi dialog sebelum delete
- Tampilan data yang akan dihapus

## Sample Data
Aplikasi secara otomatis membuat 3 sample products saat pertama kali dijalankan:
1. Laptop Dell XPS 13 - $1,299.99 (Stock: 15)
2. iPhone 15 Pro - $999.99 (Stock: 25)
3. Samsung Galaxy Watch 6 - $299.99 (Stock: 30)

## Database Schema
```sql
CREATE TABLE Products (
    Id INTEGER PRIMARY KEY AUTOINCREMENT,
    Name TEXT NOT NULL,
    Description TEXT,
    Price REAL NOT NULL,
    Stock INTEGER NOT NULL,
    CreatedAt DATETIME NOT NULL,
    UpdatedAt DATETIME NOT NULL
);
```

## Project Structure
```
ProductManagementSystem/
├── Controllers/
│   └── ProductsController.cs      # Controller untuk CRUD products
├── Data/
│   └── ApplicationDbContext.cs    # Database context dengan Entity Framework
├── Models/
│   └── Product.cs                 # Model untuk entity Product
├── Views/
│   ├── Products/
│   │   ├── Index.cshtml          # List products dengan search
│   │   ├── Create.cshtml         # Form create product
│   │   ├── Edit.cshtml           # Form edit product
│   │   ├── Details.cshtml        # Detail product
│   │   └── Delete.cshtml         # Konfirmasi delete
│   └── Shared/
│       ├── _Layout.cshtml        # Master layout
│       └── _ValidationScriptsPartial.cshtml
├── wwwroot/
│   ├── css/site.css              # Custom styles
│   └── js/site.js                # Custom JavaScript
├── Program.cs                    # Application entry point
├── appsettings.json              # Configuration
└── ProductManagementSystem.csproj # Project file
```

## Notes
- Database menggunakan SQLite untuk kemudahan review (single file database)
- Responsive design works pada desktop, tablet, dan mobile
- Bootstrap 5 untuk modern UI components
- Client-side validation untuk user experience yang lebih baik
- Server-side validation untuk data integrity

---
**Candidate:** Theofilius  
**Position:** AI Engineer  
**Company:** PT. Akarsa Garment Indonesia  
**Repository:** https://github.com/lilbuu-glitch/product-management-test.git
