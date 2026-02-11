Mechanic Shop API – Flask Application Factory Pattern
A modular, scalable backend API built using Flask, Application Factory Pattern, MySQL, JWT Authentication, Rate Limiting, Caching, Swagger Documentation, and TDD.
This project demonstrates real‑world backend engineering practices including clean architecture, blueprints, configuration management, API documentation, and automated testing.

📌 About This Project
This API is designed using the Application Factory Pattern, which allows the application to be created dynamically and configured cleanly.
It supports:

Modular blueprints
JWT authentication
Rate limiting
Caching
Pagination
Query parameters
Swagger documentation
TDD (Test‑Driven Development)
Clean folder structure for scalability

🏗️ Application Factory Pattern
What is it?
A design pattern where the application instance is created inside a function (create_app()), allowing dynamic configuration and modular architecture.

Why use it?
Loosely coupled architecture
Avoids duplication
Supports multiple environments (dev, test, prod)
Easier testing and scaling

How it works
create_app() initializes the app
extensions.py registers extensions (DB, Marshmallow, JWT, Limiter, Cache)
blueprints/ organizes routes
models.py defines database models
config.py stores environment configurations
app.py runs the application

📂 Project Structure

/project
├── app/
│   ├── __init__.py          # create_app() lives here
│   ├── extensions.py        # DB, Marshmallow, JWT, Limiter, Cache
│   ├── models.py            # SQLAlchemy models
│   ├── blueprints/
│   │   └── customers/
│   │       ├── __init__.py  # Initialize Customer Blueprint
│   │       ├── routes.py    # Customer routes/controllers
│   │       └── schemas.py   # Marshmallow schemas
├── config.py                # App configuration
├── app.py                   # Entry point
└── tests/                   # TDD test cases

<img width="1335" alt="image" src="https://github.com/user-attachments/assets/61062899-e0d7-41a4-947c-98324ab93e94" />



⏳ Flask-Limiter (Rate Limiting)
What is it?
An extension that restricts how many requests a user can make within a time window.

Why use it?
Protects routes from excessive traffic
Prevents abuse and brute‑force attacks

⚡ Flask-Caching
What is it?
Stores frequently accessed data temporarily to improve performance.

Why use it?
Reduces database load
Speeds up API responses
Improves scalability

🔐 JWT Authentication
Used to secure protected routes.

Why?
Ensures only authenticated users can access sensitive endpoints
Stateless and scalable

🧮 Pagination
What is it?
Splits large datasets into smaller pages.

Why?
Reduces server load
Improves performance
Makes responses more manageable

Examples
Limit & Offset
https://api.example.com/products?limit=10&offset=20

Page & Page Size
https://api.example.com/products?page=2&page_size=10

🔍 Query Parameters
What are they?
Key‑value pairs added to a URL after ?.

Why use them?
Filter results without sending JSON payloads

Example:

https://127.0.0.1:5000/mechanics/search?name=ma

📝 Swagger Documentation
What is it?
A UI for documenting and testing APIs.

Why use it?
Developers can test endpoints visually
Shows request/response examples
Helps teams understand API behavior

How to enable?
pip install flask-swagger flask_swagger_ui
Create:
/static/swagger.yaml
To authorize JWT in Swagger
Click Authorize
Enter: Bearer <token>

🧪 Test Driven Development (TDD)
What is it?
Write tests before writing code.

Why?
Improves code quality
Reduces bugs
Speeds up development

TDD Cycle
Red – Write failing test
Green – Write minimal code to pass
Refactor – Improve code

Run tests
python -m unittest discover tests

▶️ Running the Project Locally
1. Create virtual environment
python3 -m venv venv
source venv/bin/activate

3. Install dependencies
pip install flask flask-sqlalchemy mysql-connector-python
pip install flask-marshmallow marshmallow-sqlalchemy
pip install Flask-Limiter Flask-Caching PyJWT

5. Start the server
python app.py

7. Test using Postman or Swagger
Swagger UI:
http://127.0.0.1:5000/api/docs
