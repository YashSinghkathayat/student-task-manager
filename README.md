A secure, scalable RESTful backend application built using Spring Boot that enables authenticated users to manage their tasks efficiently. The application implements JWT-based stateless authentication, BCrypt password hashing, layered architecture, and proper exception handling following industry best practices.
Project Overview

The Student Task Manager is a backend system designed to:

Register and authenticate users securely

Manage user-specific tasks

Protect APIs using JWT authentication

Maintain data integrity using relational mapping

Follow clean layered architecture

This project demonstrates real-world backend development concepts including authentication, authorization, data persistence, validation, and REST API design.

🏗 System Architecture

The project follows a layered architecture:

Controller → Service → Repository → Database
Security Layer → JWT Filter → Authentication Flow

Layers Explained
1️⃣ Controller Layer

Handles HTTP requests and responses

Exposes RESTful APIs

Performs request validation

2️⃣ Service Layer

Contains business logic

Handles password encoding

Manages user-task relationships

3️⃣ Repository Layer

Uses Spring Data JPA

Interacts directly with MySQL database

Performs CRUD operations

4️⃣ Security Layer

Implements Spring Security

Uses JWT for stateless authentication

Validates every protected request via filter

🔐 Authentication & Security Flow
🔹 Registration Flow

Client sends registration request with username & password.

Password is hashed using BCrypt.

Hashed password is stored in the database.

Plain-text password is never stored.

🔹 Login Flow

User submits credentials.

System retrieves stored hashed password.

BCrypt matches() compares input password with stored hash.

If valid, JWT token is generated.

Token is returned to client.

🔹 Authorization Flow

Client sends JWT in Authorization header.

JwtFilter intercepts request.

Token is validated.

Username extracted from token.

SecurityContext is updated.

Protected endpoints become accessible.

This ensures stateless and secure communication.

🔑 Core Features

User Registration with secure password hashing (BCrypt)

JWT-based Authentication

Stateless Security Configuration

Role-based User Model (USERS / ADMIN)

Task Management (CRUD Operations)

One-to-Many Relationship (User → Tasks)

Global Exception Handling

Input Validation using Jakarta Validation

Clean and Scalable Code Structure

🧠 Key Concepts Implemented
🔹 BCrypt Password Hashing

Uses salting and multiple hashing rounds

One-way hashing (cannot be reversed)

Protects against rainbow table attacks

🔹 JWT (JSON Web Token)

Stateless authentication

Digitally signed token

Contains username and expiration time

Reduces server session storage

🔹 Entity Relationship

One User → Many Tasks

Foreign key mapping using JPA annotations

Ensures relational integrity

🔹 Global Exception Handling

Custom exception classes

Centralized error response structure

Clean API error messages

🛠 Tech Stack

Java

Spring Boot

Spring Security

JWT (jjwt)

Spring Data JPA

MySQL

Maven

Postman
