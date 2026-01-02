# HBnB – Part 2

## Business Logic & API Implementation (Flask + Flask-RESTx)

This project is the second part of the **HBnB** application and focuses on implementing the **Business Logic** and **API (Presentation Layer)** using **Python**, **Flask**, and **Flask-RESTx**.
In Part 1, the system design and architecture were defined. In Part 2, you bring that design to life by implementing the core functionality and API endpoints for the major entities of the application.

---

## 📑 Table of Contents

1. [Introduction](#introduction)
2. [Project Scope](#project-scope)
3. [Features](#features)
4. [Project Structure](#project-structure)
5. [Business Logic Layer](#business-logic-layer)
6. [API Layer (Flask + Flask-RESTx)](#api-layer-flask--flask-restx)
7. [Setup & Installation](#setup--installation)
8. [Usage](#usage)
9. [Endpoints Overview](#endpoints-overview)
10. [Data Serialization](#data-serialization)
11. [Testing](#testing)
12. [Future Work (Part 3 Preview)](#future-work-part-3-preview)
13. [Contributors](#contributors)
14. [License](#license)

---

## 📘 Introduction

In this phase of HBnB, you implement the **core Business Logic** and **RESTful API** endpoints that enable management of Users, Places, Reviews, and Amenities. This part establishes the foundation for the full application, including relationships among entities and serialization logic.

Authentication and SQLAlchemy persistence **are not included here** and will be implemented in Part 3. For now, data is handled using an **in-memory repository** designed to later be replaced by a database layer.

---

## 🎯 Project Scope

This part includes:

### ✔️ Project Setup

* Modular directory structure
* Packages for Presentation, Business Logic, and Persistence layers
* In-memory repository
* Facade pattern for communication between layers

### ✔️ Core Business Logic Classes

* `User`
* `Place`
* `Amenity`
* `Review`
* Base classes for shared attributes
* Relationship handling

### ✔️ RESTful API

Endpoints for:

* Users (POST, GET, PUT)
* Amenities (POST, GET, PUT)
* Places (POST, GET, PUT)
* Reviews (POST, GET, PUT, DELETE)

### ✔️ Validation

* Attribute validation (e.g., place price, latitude, longitude, review text)

### ✔️ Testing & Documentation

* Manual testing using `cURL` and Postman
* Swagger (Flask-RESTx) auto-generated documentation
* Basic automated tests (unittest/pytest)

---

## ⭐ Features

* Fully modular and scalable Python API structure
* Facade pattern to unify Business Logic and API communication
* Entity relationships:

  * User ↔ Places
  * Place ↔ Amenities
  * Place ↔ Reviews
  * User ↔ Reviews
* Built-in in-memory repository with validation
* RESTful API with clear status codes and schemas
* Password is never exposed in user API responses
* Swagger documentation via Flask-RESTx

---

## 📁 Project Structure

```
part2/
│
├── api/
│   └── v1/
│       ├── users.py
│       ├── amenities.py
│       ├── places.py
│       └── reviews.py
│
├── business/
│   ├── models/
│   │   ├── base.py
│   │   ├── user.py
│   │   ├── place.py
│   │   ├── amenity.py
│   │   └── review.py
│   └── facade.py
│
├── persistence/
│   ├── repository.py  (in-memory implementation)
│   └── validators.py
│
├── app.py
└── README.md
```

This structure is prepared for future replacement of the Persistence Layer with SQLAlchemy in Part 3.

---

## 🧠 Business Logic Layer

Implements the domain rules:

### Entities

* **User** — first_name, last_name, email, password (hidden in responses)
* **Place** — name, owner (User), amenities, price, latitude, longitude
* **Amenity** — label
* **Review** — text, rating, user, place

### Responsibilities

* Attribute validation
* Relationship maintenance
* Unique ID generation using UUID
* Timestamp updates
* Entity-level business rules

### Facade Pattern

The `Facade` class exposes high-level methods such as:

```python
create_user(data)
get_user(id)
update_user(id, data)
```

so the API never touches repository methods directly.

---

## 🌐 API Layer (Flask + Flask-RESTx)

* Organized under `api/v1/` namespaces
* Automatic Swagger documentation via Flask-RESTx
* For each entity:

  * POST → Create
  * GET → Retrieve list or by ID
  * PUT → Update
  * DELETE → Only for Reviews

All endpoints return consistent JSON structures and status codes.

---

## 🛠 Setup & Installation

```bash
# Clone repository
git clone https://github.com/holbertonschool-hbnb.git
cd holbertonschool-hbnb/part2

# Install dependencies
pip install -r requirements.txt

# Run the Flask app
python3 app.py
```

Once running, open:

```
http://localhost:5000/api/v1/
http://localhost:5000/swagger/   (auto docs)
```

---

## ▶️ Usage

Example: Create a user

```bash
curl -X POST http://localhost:5000/api/v1/users \
-H "Content-Type: application/json" \
-d '{"first_name": "John", "last_name": "Doe", "email": "john@example.com", "password": "pass123"}'
```

Example: Get all amenities

```bash
curl http://localhost:5000/api/v1/amenities
```

---

## 📚 Endpoints Overview

### Users

| Method | Endpoint             | Description    |
| ------ | -------------------- | -------------- |
| POST   | `/api/v1/users`      | Create user    |
| GET    | `/api/v1/users`      | List all users |
| GET    | `/api/v1/users/<id>` | Retrieve user  |
| PUT    | `/api/v1/users/<id>` | Update user    |

### Amenities

| Method | Endpoint                 | Description |
| ------ | ------------------------ | ----------- |
| POST   | `/api/v1/amenities`      |             |
| GET    | `/api/v1/amenities`      |             |
| GET    | `/api/v1/amenities/<id>` |             |
| PUT    | `/api/v1/amenities/<id>` |             |

### Places

| Method                    | Endpoint |
| ------------------------- | -------- |
| POST `/api/v1/places`     |          |
| GET `/api/v1/places`      |          |
| GET `/api/v1/places/<id>` |          |
| PUT `/api/v1/places/<id>` |          |

### Reviews

| Method                        | Endpoint |
| ----------------------------- | -------- |
| POST `/api/v1/reviews`        |          |
| GET `/api/v1/reviews`         |          |
| GET `/api/v1/reviews/<id>`    |          |
| PUT `/api/v1/reviews/<id>`    |          |
| DELETE `/api/v1/reviews/<id>` |          |

---

## 🧩 Data Serialization

When returning entities, related data is included.

Example: GET Place returns:

```json
{
  "id": "uuid",
  "name": "Cozy Apartment",
  "owner": {
    "first_name": "Alice",
    "last_name": "Smith"
  },
  "amenities": [
    {"id": "uuid", "label": "Wifi"},
    {"id": "uuid", "label": "Pool"}
  ]
}
```
---