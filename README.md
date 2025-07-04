# airbnb-clone-project
## 📌 Project Overview

This project is a simplified Airbnb clone focused on building a real-world back-end system. It demonstrates skills in database modeling, API development, secure authentication, and CI/CD integration. The project emphasizes back-end architecture using Django, PostgreSQL, and GraphQL.

---

## 👥 Team Roles

| Role | Responsibilities |
|------|------------------|
| **Back-End Developer** | Develops RESTful and GraphQL APIs, handles logic and integration between front-end and database. |
| **Database Administrator** | Designs and maintains relational schemas, optimizes performance, ensures data integrity and backup. |
| **DevOps Engineer** | Sets up CI/CD pipelines, manages Docker containers, handles deployment and monitoring. |
| **Security Engineer** | Implements authentication, authorization, input validation, and protects against threats like SQL injection. |
| **Project Manager** | Coordinates tasks, maintains timeline, ensures collaboration among team members. |

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| **Django** | Python-based web framework for building secure and scalable APIs. |
| **PostgreSQL** | Relational database system to store structured data like users, properties, and bookings. |
| **GraphQL** | API query language to fetch nested and specific data efficiently. |
| **Docker** | Containerization tool for packaging and deploying the application. |
| **GitHub Actions** | Automation tool for CI/CD pipelines (testing, building, deploying). |

---

## 🗃️ Database Design

### 🧑 Users
- `id` (PK)
- `name`
- `email`
- `password_hash`
- `is_host` (boolean)

### 🏠 Properties
- `id` (PK)
- `title`
- `location`
- `price_per_night`
- `host_id` (FK → Users)

### 📆 Bookings
- `id` (PK)
- `user_id` (FK → Users)
- `property_id` (FK → Properties)
- `start_date`
- `end_date`
- `status` (e.g., confirmed, cancelled)

### 💬 Reviews
- `id` (PK)
- `user_id` (FK → Users)
- `property_id` (FK → Properties)
- `rating`
- `comment`

### 💳 Payments
- `id` (PK)
- `booking_id` (FK → Bookings)
- `amount`
- `payment_method`
- `status`

**Relationships:**
- One User can have many Properties.
- One Property can have many Bookings and Reviews.
- One Booking has one Payment.

---

## ✨ Feature Breakdown

| Feature | Description |
|---------|-------------|
| **User Management** | Users can sign up, log in, and update profiles. Hosts can manage their listings. |
| **Property Listing** | Hosts can add, edit, and delete properties with details like location, price, and images. |
| **Booking System** | Guests can search properties and create bookings based on availability. |
| **Reviews and Ratings** | After a stay, users can review and rate properties to build trust. |
| **Payment Integration** | Handles secure payment processing for bookings. |
| **Admin Dashboard (Optional)** | Allows admin to manage users, listings, and reports. |

---

## 🔐 API Security

| Security Measure | Importance |
|------------------|------------|
| **Authentication (JWT)** | Ensures that only verified users access certain routes. |
| **Authorization** | Controls access based on roles (e.g., host vs guest). |
| **Rate Limiting** | Prevents abuse of APIs through excessive requests. |
| **Data Validation** | Avoids injection attacks by validating inputs. |
| **HTTPS** | Encrypts data transmission between client and server. |

---

## ⚙️ CI/CD Pipeline

**CI/CD** ensures rapid, consistent deployments and testing.

| Tool | Purpose |
|------|---------|
| **GitHub Actions** | Automate tests and deployments on push or PR. |
| **Docker** | Package the app into containers for portability. |
| **PostgreSQL Service** | Used for test database in CI. |

### Sample Workflow:
1. Code pushed to GitHub.
2. GitHub Actions runs tests.
3. If passed, Docker image is built.
4. Image deployed to a staging/production environment.


