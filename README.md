


🛠️ Mechanic Shop Advanced API
A production‑ready RESTful backend service built with Flask, SQLAlchemy, Marshmallow, and MySQL, supporting full CRUD operations for Customers, Mechanics, Service Tickets, and Inventories, with token authentication, Swagger documentation, advanced queries, and automated unit testing.

<img width="635" height="515" alt="image" src="https://github.com/user-attachments/assets/3eb95bc9-dd27-4a6c-9e50-7e644f0711c6" />

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
   (https://github.com/arshaprajesh/MechanicShop-using-python.git)
   
cd mechanic-shop-api

3. Create and activate a virtual environment
4. 
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows

6. Install dependencies
   
pip install -r requirements.txt

6. Configure your database
Update your MySQL connection in config.py.

7. Run the application

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


http://127.0.0.1:5000/api/docs/
Swagger loads the OpenAPI file from:


/application/static/swagger.yaml
🔐 Authentication
Protected routes require a valid JWT token:


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
<img width="696" height="649" alt="image" src="https://github.com/user-attachments/assets/5202e4d9-0e57-4bb4-b6f5-c929642cd80d" />


