🛒 Smart Cart – ASP.NET Core MVC E‑Commerce Application

Smart Cart is a full‑stack e‑commerce web application built with ASP.NET Core MVC, Entity Framework Core, Identity, and JWT-secured REST APIs.
It includes product browsing, cookie‑based cart, PayPal payments, order tracking, admin dashboards, and user management.

🚀 Features
👤 Authentication & Authorization

ASP.NET Core Identity
Register/Login/Logout
Forgot & Reset Password
Role-based access (Admin, Client)
Profile & password editing

🛍️ Store & Products

Browse, search, filter, sort products
Product details page
Admin product management (CRUD)
Image upload & replacement
Pagination for large catalogs

🛒 Shopping Cart

Cookie‑based cart (guest & logged‑in users)
Add/update/remove products
Automatic subtotal, shipping, and total calculation

💳 Checkout & Payments

Delivery address entry
Payment methods:

Cash on Delivery
PayPal (Create & Capture API flow)


Order confirmation before placement

📦 Orders

Clients: View order history & details
Admin: View all orders

Update payment status
Update order status
View PayPal metadata



🔐 REST APIs (JWT Protected)

/api/auth/login
/api/v1/products (Admin)
/api/v1/orders (Client)
/api/v1/admin/orders (Admin)

Features:

API Versioning
JWT Token authentication
Role-based protection


🗂️ Project Structure
SmartCart/
│
├── Controllers/
│   ├── MVC Controllers
│   └── API Controllers (JWT Secured)
│
├── Models/
│   ├── ApplicationUser
│   ├── Product
│   ├── Order / OrderItem
│   └── View Models
│
├── DTOs/
│   ├── RegisterDTO / LoginDTO
│   ├── ProductDTO
│   ├── CheckoutDTO
│   ├── ProfileDTO / PasswordDTO
│   └── PasswordResetDTO
│
├── Services/
│   ├── CartHelper
│   ├── DatabaseInitializer
│   └── EmailSender
│
├── Data/
│   └── ApplicationDbContext
│
├── Views/ (Razor)
│
└── appsettings.json


⚙️ Configuration (appsettings.json)
JSON"ConnectionStrings": {  "DefaultConnection": "Server=...;Database=ShoppingCartDB;Trusted_Connection=True;"},"JwtSettings": {  "Issuer": "SmartCartAPI",  "Audience": "SmartCartClient",  "SecretKey": "YOUR_SECRET_KEY"},"BrevoSettings": {  "ApiKey": "YOUR_BREVO_KEY",  "SenderName": "Smart Cart",  "SenderEmail": "admin@smartcart.com"},"CartSettings": {  "ShippingFee": 6.5},"PayPalSettings": {  "ClientId": "YOUR_PAYPAL_CLIENT",  "Secret": "YOUR_PAYPAL_SECRET",  "Url": "https://api-m.sandbox.paypal.com"}Show more lines

▶️ How to Run the Project
1️⃣ Prerequisites

.NET 6+
SQL Server (LocalDB/Express)
Visual Studio / VS Code
PayPal Sandbox credentials (optional)
Brevo (SendInBlue) API key (optional)

2️⃣ Setup
Shellgit clone <repo-url>cd SmartCartShow more lines
3️⃣ Update appsettings.json
Add your DB connection & API keys.
4️⃣ Apply migrations (if required)
Shellupdate-databaseShow more lines
5️⃣ Run the app
Shelldotnet runShow more lines
6️⃣ Admin Account Auto‑Generated
Email: admin@admin.com
Password: admin123


🔐 API Testing via Swagger
Swagger UI available at:
https://localhost:{port}/swagger

Steps:

Login via /api/auth/login
Copy JWT token
Click "Authorize" and paste token
Test protected endpoints


🛡️ Security Highlights

All operations validated using DTOs
ASP.NET Identity password hashing
Role‑based authorization for Admin & Client
JWT Bearer authentication (APIs)
EF Core prevents SQL Injection
PayPal handled via server‑side API (secure)
Sensitive keys stored in config, not in code


🎯 Future Improvements

Inventory management
Product reviews & ratings
Redis-based distributed cart
Admin analytics dashboard
Azure deployment setup


📝 License
This project is open‑source under the MIT License.

💬 Support
For issues or feature requests, please open a GitHub Issue.
