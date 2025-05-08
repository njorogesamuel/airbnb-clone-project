# Airbnb Clone Project

## Overview
The Airbnb Clone Project is a full-stack simulation of the Airbnb platform, focusing on backend development, API security, database architecture, and collaborative workflows. This project is designed to deepen understanding of scalable web application development using modern frameworks and DevOps practices.

---

## 🚀 Project Goals.
- Build a scalable backend using Django and GraphQL.
- Design and implement a normalized MySQL database.
- Implement secure, RESTful APIs.
- Establish CI/CD pipelines with Docker and GitHub Actions.
- Collaborate via GitHub with documented roles and responsibilities.

---

## 👥 Team Roles and Responsibilities.

| Role                  | Description |
|-----------------------|-------------|
| **Backend Developer** | Designs and implements the business logic and REST/GraphQL APIs using Django. |
| **Database Administrator (DBA)** | Plans and maintains the MySQL schema, ensures data consistency and performance tuning. |
| **DevOps Engineer**   | Sets up CI/CD pipelines using GitHub Actions and Docker for testing and deployment. |
| **QA Engineer**       | Writes and runs test cases to validate API endpoints and ensure system stability. |
| **Project Manager**   | Oversees progress, ensures timelines are met, and coordinates team communication. |

---

## 🧰 Technology Stack

| Technology   | Purpose |
|--------------|---------|
| **Django**   | A Python web framework used to build robust and secure backend APIs. |
| **MySQL**    | Relational database system used to store all application data. |
| **GraphQL**  | A flexible query language for APIs enabling frontend apps to request exactly what they need. |
| **Docker**   | Used to containerize the application for consistent development and deployment. |
| **GitHub Actions** | Automates testing and deployment workflows via CI/CD. |
| **Markdown** | Used for clear documentation, including the README.md file. |

---

## 🗃️ Database Design

**Entities and Key Fields:**

1. **Users**
   - id (PK)
   - name
   - email
   - password_hash
   - role (guest/host)

2. **Properties**
   - id (PK)
   - owner_id (FK to Users)
   - title
   - description
   - location

3. **Bookings**
   - id (PK)
   - user_id (FK to Users)
   - property_id (FK to Properties)
   - check_in
   - check_out

4. **Reviews**
   - id (PK)
   - user_id (FK to Users)
   - property_id (FK to Properties)
   - rating
   - comment

5. **Payments**
   - id (PK)
   - booking_id (FK to Bookings)
   - amount
   - payment_date
   - status

**Relationships:**
- A `User` can list multiple `Properties`.
- A `User` can create multiple `Bookings`.
- Each `Booking` is linked to one `Property`.
- A `Review` is linked to both a `User` and a `Property`.
- A `Payment` is linked to one `Booking`.

---

## ✨ Feature Breakdown

1. **User Management**
   - Users can register, log in, and manage their profiles.
   - Role-based access control to distinguish between guests and hosts.

2. **Property Management**
   - Hosts can create, update, and delete property listings.
   - Images and amenities are associated with listings.

3. **Booking System**
   - Guests can search for properties and make bookings.
   - Calendar-based availability checks.

4. **Reviews**
   - Guests can leave reviews and ratings after their stay.
   - Hosts can respond to reviews.

5. **Payment Integration**
   - Process and track payments via a secure gateway.
   - View payment history for each booking.

---

## 🔐 API Security

| Measure         | Importance |
|-----------------|------------|
| **Authentication** | Ensures only registered users can access or modify data. Implemented using JWT tokens. |
| **Authorization**  | Prevents unauthorized access to endpoints (e.g., only hosts can edit listings). |
| **Rate Limiting**  | Protects the API from abuse or brute-force attacks. |
| **Input Validation & Sanitization** | Prevents SQL injection and XSS attacks. |
| **HTTPS Enforcement** | Secures data transmission between client and server. |

---

## ⚙️ CI/CD Pipeline

### What is CI/CD?
CI/CD (Continuous Integration/Continuous Deployment) automates the software release process by:
- Continuously testing new changes.
- Automatically deploying validated code to production.

### Tools Used:
- **GitHub Actions**: Automates linting, unit tests, and deployment workflows.
- **Docker**: Packages the app with its environment to ensure consistency.
- **pytest**: For running backend unit tests during CI.
- **Docker Hub** (optional): Store and version Docker images.
