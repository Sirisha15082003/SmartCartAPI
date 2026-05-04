🛒 Smart Cart — E‑Commerce Web App (ASP.NET Core MVC)
Smart Cart is a full‑stack e‑commerce application built using ASP.NET Core MVC, Entity Framework Core, Identity, and JWT APIs.
It includes product browsing, cookie‑based cart, PayPal checkout, order tracking, and an admin management dashboard.
Key Highlights

User authentication (Identity) & role‑based access (Admin, Client)
Product browsing with search, filter, sort & pagination
Cookie‑based shopping cart (guest + logged‑in users)
PayPal online payment integration (create & capture)
Order history & tracking
Admin product CRUD, user management & order management
Secure REST APIs with JWT + API versioning

Tech Stack

Backend: ASP.NET Core MVC, EF Core, Identity, JWT
Frontend: Razor Pages, Bootstrap
Database: SQL Server
Integrations: PayPal REST API, Brevo (Email API)

Run Locally

Update appsettings.json with DB, PayPal & Email credentials
Run migrations → update-database
Run the application → dotnet run
Default admin auto‑created:
Email: admin@admin.com
Password: admin123



