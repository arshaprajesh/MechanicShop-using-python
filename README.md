

📂 Project Structure
<img width="551" height="279" alt="image" src="https://github.com/user-attachments/assets/c2309b22-3e7a-4059-bd10-be677c1b6de2" />


<img width="1335" alt="image" src="https://github.com/user-attachments/assets/61062899-e0d7-41a4-947c-98324ab93e94" />

🛠️ Mechanic Shop Advanced API
A production‑ready RESTful backend service built with Flask, SQLAlchemy, Marshmallow, and MySQL, supporting full CRUD operations for Customers, Mechanics, Service Tickets, and Inventories, with token authentication, Swagger documentation, advanced queries, and automated unit testing.

Code
+----------------+       1        M       +--------------------+
|   Customers    |------------------------|   Service Tickets  |
+----------------+                        +--------------------+
| id (PK)        |                        | id (PK)            |
| name           |                        | customer_id (FK)   |
| email          |                        | mechanic_id (FK)   |
| phone          |                        | issue_description  |
+----------------+                        | status             |
                                          +--------------------+
                                                   |
                                                   |
                                      +---------------------------+
                                      |   mechanic_services       |
                                      +---------------------------+
                                      | mechanic_id (FK)          |
                                      | service_ticket_id (FK)    |
                                      +---------------------------+

+----------------+       1        M       +--------------------+
|   Mechanics    |------------------------|    Inventories     |
+----------------+                        +--------------------+
| id (PK)        |                        | id (PK)            |
| name           |                        | part_name          |
| specialization |                        | quantity           |
+----------------+                        +--------------------+
🚀 Features
Full CRUD operations for Customers, Mechanics, Service Tickets, and Inventories

Token‑based authentication (JWT)

Rate limiting + caching for performance and abuse prevention

Advanced queries: filtering, sorting, pagination

Many‑to‑many relationships using junction tables with additional fields

Marshmallow schemas for validation and serialization

Swagger UI documentation (OpenAPI YAML)

Automated unit tests using Python’s unittest

Clean Application Factory Pattern with modular blueprints

🛠️ Tech Stack
Backend: Flask

ORM: SQLAlchemy

Validation: Marshmallow

Database: MySQL

Auth: JWT

Documentation: Swagger / OpenAPI

Testing: unittest

Tools: Postman

📦 Installation & Setup
1. Clone the repository
bash
git clone <your-repo-url>
cd mechanic-shop-api
2. Create and activate a virtual environment
bash
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
3. Install dependencies
bash
pip install -r requirements.txt
4. Configure your database
Update your MySQL connection in config.py.

5. Run the application
bash
python app.py
📘 API Endpoints
Customers
Method	Endpoint	Description
GET	/customers	Get all customers
GET	/customers/	Get customer by ID
POST	/customers	Create customer
PUT	/customers/	Update customer
DELETE	/customers/	Delete customer
Mechanics
Method	Endpoint	Description
GET	/mechanics	Get all mechanics
POST	/mechanics	Create mechanic
PUT	/mechanics/	Update mechanic
DELETE	/mechanics/	Delete mechanic
Service Tickets
Method	Endpoint	Description
POST	/tickets	Create service ticket
GET	/tickets	Get all tickets
GET	/tickets/	Get ticket by ID
PUT	/tickets/	Update ticket
DELETE	/tickets/	Delete ticket
Inventories
Method	Endpoint	Description
GET	/inventory	Get all inventory items
POST	/inventory	Add inventory item
PUT	/inventory/	Update inventory
DELETE	/inventory/	Delete inventory
📚 Swagger Documentation
After running the app:

Code
http://127.0.0.1:5000/api/docs/
Swagger loads the OpenAPI file from:

Code
/application/static/swagger.yaml
🔐 Authentication
Protected routes require a valid JWT token:

Code
Authorization: Bearer <your_token_here>
Tokens are generated after login.

🧪 Unit Testing
Run all tests:
bash
python -m unittest discover tests
Run a specific test:
bash
python -m unittest tests.test_customers
Covered modules:
test_customers.py – Auth + CRUD

test_mechanics.py

test_service_tickets.py

test_inventories.py

📂 Project Structure
Code
mechanic-shop-api/
│
├── application/
│   ├── __init__.py               # create_app() – Application Factory
│   ├── extensions.py             # DB, JWT, caching, rate limiting
│   │
│   ├── blueprints/
│   │   ├── customer/
│   │   │   ├── __init__.py
│   │   │   ├── routes.py
│   │   │   └── schemas.py
│   │   ├── mechanic/
│   │   ├── service_ticket/
│   │   └── inventory/
│   │
│   ├── static/
│   │   └── swagger.yaml
│   │
│   ├── utils/
│   │   └── util.py               # Token helpers
│   │
│   └── models.py                 # All SQLAlchemy models
│
├── tests/
│   ├── test_customers.py
│   ├── test_mechanics.py
│   ├── test_service_tickets.py
│   └── test_inventories.py
│
├── app.py
├── config.py
└── requirements.txt


