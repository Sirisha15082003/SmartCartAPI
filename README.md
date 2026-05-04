🛒 Smart Cart – ASP.NET Core MVC E‑Commerce App
A full‑stack scalable shopping cart system using ASP.NET Core MVC, Entity Framework Core, and Identity, featuring JWT APIs, PayPal payments, and cookie‑based cart.

🧱 System Architecture Diagram
                     ┌─────────────────────────────────┐
                     │          Presentation            │
                     │   Razor Views (.cshtml)          │
                     └─────────────────────────────────┘
                                   │
                                   ▼
                     ┌─────────────────────────────────┐
                     │            MVC Layer             │
                     │ Controllers (UI)                 │
                     │ API Controllers (REST + JWT)     │
                     └─────────────────────────────────┘
                                   │
                                   ▼
                     ┌─────────────────────────────────┐
                     │            Services              │
                     │ CartHelper, EmailSender,        │
                     │ DatabaseInitializer             │
                     └─────────────────────────────────┘
                                   │
                                   ▼
                     ┌─────────────────────────────────┐
                     │              Data                │
                     │ EF Core Models + DbContext       │
                     └─────────────────────────────────┘
                                   │
                                   ▼
                     ┌─────────────────────────────────┐
                     │         SQL Server DB           │
                     └─────────────────────────────────┘


🔄 End‑to‑End Request Flow (Click → DB → Response)
🖱️ Example: Add to Cart
User Click "Add to Cart"
       │
       ▼
StoreController (Details Page)
       │
       ▼
CartHelper (Cookie-based cart)
       │
       ▼
Cookie updated (Base64 JSON)
       │
       ▼
Response → Updated cart count in navbar

🧾 Example: Checkout (COD)
User Checkout
     │
     ▼
CartController (POST CheckoutDTO)
     │
     ▼
Build Order Model
     │
     ▼
EF Core → SQL Server
     │
     ▼
Order Confirmation View

💳 Example: PayPal Payment Flow
CheckoutController
    │
    ├── CreateOrder() → PayPal API
    │
    ├── User Approves Payment
    │
    └── CompleteOrder() → Capture Payment + Save to DB


🧩 Folder Structure with Responsibilities
Controllers/
   MVC Controllers for Views
   API Controllers for JWT-protected endpoints

Models/
   Database entities (Product, Order, ApplicationUser)

DTOs/
   Safe data exchange objects for Views + APIs

Services/
   CartHelper     → cookie-based shopping cart
   EmailSender    → transactional emails
   DatabaseInitializer → Role/admin seeding

Data/
   ApplicationDbContext + EF Core database mapping

Views/
   Razor pages for store, account, admin, orders


🔐 Security Diagram
                 ┌──────────────────────────┐
                 │  ASP.NET Identity         │
                 │  Users + Roles            │
                 └──────────────────────────┘
                           │
                           ▼
        ┌────────────────────────────────────────┐
        │              Authentication             │
        │  - Cookies (MVC)                       │
        │  - JWT Tokens (Web API)                │
        └────────────────────────────────────────┘
                           │
                           ▼
           ┌───────────────────────────────────┐
           │           Authorization            │
           │   [Authorize(Roles="admin")]       │
           │   [Authorize(Roles="client")]      │
           └───────────────────────────────────┘


🛠️ Tech Stack

ASP.NET Core MVC
EF Core + SQL Server
ASP.NET Identity
JWT Bearer Auth
Razor + Bootstrap
PayPal REST API
Brevo (SendInBlue) Email API


📦 Installation
Shellgit clone <repo-url>cd SmartCartShow more lines
Update appsettings.json, then run:
Shellupdate-databasedotnet runShow more lines

👤 Default Admin Credentials
Email: admin@admin.com
Password: admin123


🤝 License
MIT License.
