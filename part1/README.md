# HBnB Evolution - Technical Documentation

## Overview

HBnB Evolution is a simplified version of an AirBnB-like application that allows users to manage properties, reviews, and amenities. This documentation provides a comprehensive blueprint of the application’s architecture, business logic, and interactions between components. It is intended to guide the implementation phase and ensure clarity in the system’s design.

---

## Application Features

### User Management
- Users can register, update profiles, and delete accounts.
- Each user has:
  - First Name
  - Last Name
  - Email
  - Password
  - Administrator flag (boolean)
- Users can be regular or administrative.

### Place Management
- Users can list properties (places) they own.
- Each place has:
  - Title
  - Description
  - Price
  - Latitude & Longitude
  - List of associated amenities
- Operations include create, update, delete, and list.

### Review Management
- Users can leave reviews for places they visited.
- Each review includes:
  - Rating
  - Comment
  - Associated User and Place
- Operations include create, update, delete, and list by place.

### Amenity Management
- Each amenity has:
  - Name
  - Description
- Operations include create, update, delete, and list.

---

## Business Rules
- Each entity has a unique ID.
- Creation and update timestamps are registered for all entities.
- Places are linked to users as owners.
- Places can have multiple amenities.

---

## Architecture

The application follows a **layered architecture**:

1. **Presentation Layer**  
   - Handles user interactions via services and API endpoints.
2. **Business Logic Layer**  
   - Contains models, core logic, and validation.
3. **Persistence Layer**  
   - Responsible for storing and retrieving data from the database.

**Communication** between layers uses the **Facade Pattern**, ensuring separation of concerns and simplified interfaces.

---

## Diagrams

### 1. High-Level Package Diagram
- Shows the three-layer architecture and interactions between Presentation, Business Logic, and Persistence layers.

### 2. Detailed Class Diagram (Business Logic Layer)
- Entities: `User`, `Place`, `Review`, `Amenity`
- Relationships:
  - `User` → `Place` (owns)
  - `Place` ↔ `Amenity` (many-to-many)
  - `User` → `Review` (writes)
  - `Place` → `Review` (has)
- Attributes and methods for each entity are defined, including CRUD operations and timestamps.

### 3. Sequence Diagrams for API Calls
- **User Registration**: Flow from API to persistence.
- **Place Creation**: How a new place is created and linked to a user.
- **Review Submission**: Flow of submitting a review for a place.
- **Fetching List of Places**: Interaction between layers to retrieve places.

> All diagrams use **UML notation** for consistency.

---

## Persistence
- Data is stored in a database (to be implemented in Part 3).
- Each entity’s CRUD operations interact with the persistence layer.
- Relations, keys, and timestamps are maintained.

---

## Tools and Resources
- UML Basics: [OOP - Introduction to UML](#)
- Package Diagrams: [UML Package Diagram Overview](#), [UML Package Diagrams Guide](#)
- Class Diagrams: [UML Class Diagram Tutorial](#), [How to Draw UML Class Diagrams](#)
- Sequence Diagrams: [UML Sequence Diagram Tutorial](#), [Understanding Sequence Diagrams](#)
- Diagram Tools: [Mermaid.js Documentation](https://mermaid.js.org/), [draw.io](https://app.diagrams.net/)

---

## Conclusion

This documentation provides a complete blueprint for the HBnB Evolution application. It ensures:
- Clear understanding of business rules
- Proper design of entities and relationships
- Well-defined interactions between layers
- Smooth guidance for the implementation phase

---