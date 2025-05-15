
# 🧳 alx_travel_app

> A scalable Django-based travel listing platform — built using real-world best practices for backend architecture, API documentation, and MySQL integration.

---

## 💬 Project Overview (Interview Style)

### ❓ What is **alx_travel_app**, and why did you build it?

**alx_travel_app** is a foundational Django project designed to simulate a real-world travel listing platform. It allows users to interact with travel-related listings via REST APIs and is structured with scalability, maintainability, and team collaboration in mind.

I built this as part of a milestone project to demonstrate how to architect production-ready backend applications using Django, Django REST Framework, Swagger (drf-yasg), and MySQL — while following best practices like environment variable management and version control.

---

## 🛠️ Technologies & Tools Used

| Tool/Library           | Purpose |
|------------------------|---------|
| Django                 | Core web framework |
| Django REST Framework  | API building |
| drf-yasg               | Swagger API documentation |
| django-environ         | Secure environment variable management |
| django-cors-headers    | Handle cross-origin requests |
| MySQL                  | Relational database |
| Celery + RabbitMQ      | (For future tasks) Async background processing |
| Git + GitHub           | Version control and collaboration |

---

## 🧱 Project Structure

```
alx_travel_app/
│
├── listings/                 # Main app for travel-related functionalities
│   ├── models.py
│   ├── views.py
│   ├── serializers.py
│   └── urls.py
│
├── alx_travel_app/           # Project settings
│   ├── settings.py           # Uses django-environ for secrets
│   ├── urls.py               # Includes Swagger docs and app URLs
│   └── wsgi.py
│
├── requirements.txt          # List of all dependencies
├── .env                      # Not committed — stores DB and secret keys
└── manage.py
```

---

## ⚙️ Configuration Details

### 🔑 Environment Variables

Environment variables are managed using `django-environ` to securely handle sensitive data like:

```ini
# .env (NOT pushed to GitHub)


In `settings.py`, we load the `.env` using:

```python
import environ
env = environ.Env()
environ.Env.read_env()

```

---

## 🧪 API Documentation with Swagger

Swagger (via `drf-yasg`) is configured to automatically generate live, interactive API docs at:

```
http://localhost:8000/swagger/
```

All API endpoints are visible, testable, and auto-updated.

---

## 📦 Installation Guide

### 1. Clone the Repo

```bash
git clone https://github.com/yourusername/alx_travel_app.git
cd alx_travel_app
```

### 2. Create and Activate a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Create `.env` File

Create a `.env` file at the root with your MySQL credentials and other settings.

### 5. Run Migrations & Start Server

```bash
python manage.py migrate
python manage.py runserver
```

Visit [http://127.0.0.1:8000/swagger/](http://127.0.0.1:8000/swagger/) to test APIs.

---

## 📜 requirements.txt (Snapshot)

```
Django>=4.2
djangorestframework
drf-yasg
django-environ
mysqlclient
django-cors-headers
celery
```

---

## 🌍 Future Roadmap

- 🔐 Add user authentication (JWT or session-based)
- ✈️ Create models for listings, destinations, and bookings
- 🔄 Integrate Celery + RabbitMQ for async tasks (e.g., email notifications)
- 📊 Admin dashboard for managing listings
- 🧪 Add unit and integration tests

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## ✅ GitHub Repo Structure

```
📁 alx_travel_app/
├── alx_travel_app/
├── listings/
├── .env
├── requirements.txt
└── README.md
```

---

## 🙋🏽‍♂️ Interview Notes

> **Q:** *Why did you use MySQL instead of SQLite?*  
> **A:** MySQL is more suitable for production due to performance and concurrency handling, unlike SQLite which is great only for development.

> **Q:** *What’s the role of `drf-yasg`?*  
> **A:** It provides live Swagger UI documentation for all DRF APIs, reducing the need for manually maintained docs and improving collaboration.

> **Q:** *How is the app scalable?*  
> **A:** Through modular architecture, async task support via Celery, RESTful APIs, and MySQL. It also uses `.env` configs, making it deployment-ready.

> **Q:** *What are some best practices you’ve followed?*  
> **A:** Environment separation, version control, API documentation, secure config handling, and RESTful design principles.
