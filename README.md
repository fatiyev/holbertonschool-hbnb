# HBnB Evolution Project

## Overview

The HBnB Evolution project aims to develop a simplified version of an Airbnb-like application. The application enables user management, property listing, review submissions, and amenity management. This project was developed as part of the Holberton School Web & Mobile Developer curriculum and is structured in four progressive parts, from technical documentation to a fullstack web application.

## Table of Contents

1. [Project Objectives](#project-objectives)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Project Parts](#project-parts)
    - [Part 1: Technical Documentation](#part-1-technical-documentation)
    - [Part 2: Backend API (In-Memory)](#part-2-backend-api-in-memory)
    - [Part 3: Secure Backend & Database](#part-3-secure-backend--database)
    - [Part 4: Fullstack Web Application](#part-4-fullstack-web-application)
5. [Architecture & Diagrams](#architecture--diagrams)
6. [API Endpoints](#api-endpoints)
7. [Installation & Usage](#installation--usage)
8. [Testing](#testing)

## Project Objectives

- Create technical documentation for the HBnB Evolution application.
- Document the architecture, business logic, and interactions within the system.
- Develop a RESTful API backend with authentication and database integration.
- Build a modern, interactive frontend web client.

## Features

- **User Management**: Register, update, and manage users as regular or admin.
- **Place Management**: List properties with details and manage amenities.
- **Review Management**: Submit and manage reviews for places.
- **Amenity Management**: Create and manage amenities associated with places.
- **Authentication**: JWT-based authentication and role-based access control.
- **Frontend**: Responsive web client (HTML5, CSS3, JS ES6) with login, place listing, details, and review submission.

## Project Structure

```
holbertonschool-HBNB/
│
├── part1/           # Technical documentation (UML, diagrams, notes)
├── part2/           # Backend API Flask (in-memory storage)
├── part3/           # Secure backend (JWT, SQLAlchemy, SQLite/MySQL)
├── part4/           # Final version: Backend + Full frontend web client
│
├── README.md        # This file
├── Documentation_Compilation.md
├── Diagramm_De_Class.png, Package_Diagram.drawio.png, ...
```

## Project Parts

### Part 1: Technical Documentation
- **Goal:** Design all technical documentation (UML diagrams, architecture, API sequences, etc.) as a foundation for development.
- **Deliverables:**
  - High-level package diagram (3-layer architecture)
  - Detailed class diagram (User, Place, Review, Amenity)
  - Sequence diagrams (registration, place creation, review, etc.)
  - Compiled in `Documentation_Compilation.md`

### Part 2: Backend API (In-Memory)
- **Goal:** Implement a RESTful API in Python/Flask with in-memory storage (no database).
- **Features:**
  - User, place, review, and amenity management
  - Layered architecture (API, services, persistence)
  - Facade pattern for business logic
- **Structure:**
  - `part2/hbnb/app/` (api, models, services, persistence)
  - Unit tests in `part2/hbnb/tests/`

### Part 3: Secure Backend & Database
- **Goal:** Secure the API (JWT authentication, admin roles), integrate a relational database (SQLite for dev, MySQL for prod).
- **Features:**
  - JWT authentication, session management
  - Role-based access control (admin/user)
  - SQLAlchemy mapping of entities and relationships
  - Database initialization scripts (`init_db.py`)
- **Structure:**
  - `part3/hbnb/app/` (api, models, services, persistence)
  - Unit tests in `part3/hbnb/tests/`

### Part 4: Fullstack Web Application
- **Goal:** Develop a modern web interface (HTML5, CSS3, JS ES6) connected to the API.
- **Features:**
  - Pages: login, place list, place details, add review
  - Client-side authentication (JWT storage)
  - Dynamic API calls (Fetch/AJAX)
  - Filtering, dynamic display, session management
- **Structure:**
  - `part4/hbnb/frontend/base_files/` (HTML, CSS, JS)
  - Images in `part4/hbnb/frontend/images/`
  - Final backend in `part4/hbnb/app/`
  - Unit tests in `part4/hbnb/tests/`

## Architecture & Diagrams

The application follows a layered architecture:

1. **Presentation Layer**: Handles user interactions and API calls.
2. **Business Logic Layer**: Contains the core logic and models.
3. **Persistence Layer**: Manages data storage and retrieval.

### Diagrams

- **High-Level Package Diagram**  
![High-Level Package Diagram](Package_Diagram.drawio.png)

- **Detailed Class Diagram**  
![Class Diagram](Diagramm_De_Class.png)

- **Sequence Diagrams:**
    - User Registration  
    ![User Registration Sequence](API_POST_User_Registration.jpeg)
    - Place Creation  
    ![Place Creation Sequence](API_POST_Place_Creation.jpeg)
    - Review Submission  
    ![Review Submission Sequence](API_POST_Review_Submission.jpeg)
    - Fetching Places  
    ![Fetching Places Sequence](API_POST_Fetch_a_list_of_places.jpeg)

## API Endpoints

- **POST /api/v1/users/**: Register a user
- **POST /api/v1/places/**: Create a place listing
- **POST /api/v1/reviews/**: Submit a review
- **GET /api/v1/places/**: Fetch a list of places
- **POST /api/v1/auth/login**: User login (JWT)
- **GET /api/v1/amenities/**: List amenities
- **Admin endpoints**: See Swagger documentation for full list

## Installation & Usage

### 1. Clone the repository
```bash
git clone https://github.com/Weebaay/holbertonschool-higher_level_programming.git
cd holbertonschool-higher_level_programming/holbertonschool-HBNB/part4/hbnb
```

### 2. Create and activate a virtual environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Initialize the database
```bash
python3 init_db.py
```

### 5. Run the API
```bash
python3 run.py
```

### 6. Run the frontend
In another terminal:
```bash
cd frontend
python3 -m http.server 8080
```
Go to [http://127.0.0.1:8080/base_files/index.html](http://127.0.0.1:8080/base_files/index.html)

## Testing

To run unit tests:
```bash
python3 -m unittest discover tests
```
