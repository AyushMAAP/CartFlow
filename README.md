# 🛒 CartFlow

A Java-based e-commerce web application built with Spring Boot, Spring MVC, JSP, Spring Security, Hibernate ORM, and MySQL.

CartFlow follows a layered MVC architecture with separate controller, service, and data-access layers. The application supports customer registration and authentication, product browsing, profile management, and role-based administrative workflows for managing products, categories, and customers.

---

## ✨ Features

### 👤 Customer

- User registration
- User login and logout
- Role-based authentication
- Product browsing
- User profile viewing
- Profile and account information updates
- Password management
- Server-rendered JSP pages

### 🔐 Authentication & Authorization

- Spring Security-based authentication
- Role-based authorization
- Separate security configuration for admin and customer routes
- BCrypt password encoding
- CSRF protection for form-based requests
- Session-based authentication
- Custom `UserDetailsService`

### 🛠️ Admin

- Admin authentication
- Admin dashboard
- Product management
- Category management
- Customer listing
- Protected `/admin/**` routes

### 🗄️ Persistence

- MySQL relational database
- Hibernate ORM
- Custom Hibernate `SessionFactory` configuration
- DAO-based data-access layer
- Service layer for business logic
- Entity-based database mapping
- Transaction management using Hibernate

---

## 🏗️ Architecture

CartFlow follows a layered MVC architecture:

```text
                         ┌──────────────────────┐
                         │       Browser        │
                         │     JSP / HTML       │
                         └──────────┬───────────┘
                                    │
                                    │ HTTP Request
                                    ▼
                         ┌──────────────────────┐
                         │   Spring Security   │
                         │ Authentication /    │
                         │ Authorization        │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │     Controllers      │
                         │    Spring MVC        │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │      Services        │
                         │   Business Logic     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │        DAO           │
                         │   Data Access Layer  │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │      Hibernate       │
                         │   SessionFactory     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │        MySQL         │
                         │      Database        │
                         └──────────────────────┘
