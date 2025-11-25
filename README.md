# 📚 Library Service

The Library Service API is a modern book borrowing and inventory management system built with Django REST Framework.
It digitizes library workflows such as inventory tracking, borrowing/returns, payments, and notifications.

🔑 Key Features
📘 Inventory Management

Full CRUD operations for books

Automated stock tracking (inventory field)

📚 Borrowing & Returns

Create borrowing records

Automatic inventory decrease on borrow

Automatic inventory increase on return

🔐 Authentication & Authorization

User registration and login

Secure JWT-based authentication

💳 Payments (WIP)

Stripe integration for:

Borrowing fees

Late return fines

🔔 Notifications (WIP)

New borrowings

Overdue reminders

Successful payment notifications

🚀 Quick Start (Docker Compose)

The easiest way to run the project is via Docker Compose, which automatically sets up Django and PostgreSQL.

📦 Requirements

Docker & Docker Compose installed

.env file created in the project root

1️⃣ Environment Variables

Create a .env file in the root directory.
Use .env.sample or the template below:

# Core Settings
SECRET_KEY=your_secret_key
DEBUG=True_or_False
ALLOWED_HOSTS=your_host

# Database Settings (Used by Docker Compose)
DJANGO_ENV=docker
POSTGRES_DB=db_name
POSTGRES_USER=user_name
POSTGRES_PASSWORD=your_password
POSTGRES_HOST=host_name
POSTGRES_PORT=your_port


2️⃣ Build & Run

From the project root:

docker-compose up -d --build


This will:

Build the Django app image

Start the PostgreSQL container

Start the Django container

Automatically wait for DB and run migrations

3️⃣ Create Superuser
docker-compose exec library_service_project python manage.py createsuperuser



💻 API Access & Documentation

The API is fully documented via DRF Spectacular (Swagger UI).

Interface	URL	Description
Swagger UI	http://localhost:8001/api/doc/swagger/
	
🔑 JWT Authorization

Open /api/doc/swagger/

Use POST /api/users/token/ to obtain an access token

Click Authorize and enter:

Bearer <your_token>
