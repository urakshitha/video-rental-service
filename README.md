# video-rental-service
# Simplified Video Rental API

A simplified version of a video rental system built using **Spring Boot** and **MySQL**.  
This RESTful API provides secure user authentication via Basic Auth, role-based access control (`ADMIN`, `CUSTOMER`), and allows for video catalog management.

___

## Tech Stack
- Java 17+
- Spring Boot
- Spring Security
- Spring Data JPA
- MySQL
- BCrypt

---

# Key Features

# Authentication & Authorization
- Basic Authentication using email and password
- Role-based access control using ADMIN and CUSTOMER
- Passwords are securely hashed using BCrypt

#  User Management
User Registration with fields: Email, Password, First Name, Last Name, Role
- Role defaults to CUSTOMER if not specified
- Public registration endpoint (/api/public/register)
- Basic Auth login with email & password

# Video Management
Videos include: Title, Director, Genre, Availability Status
All videos are assumed to be available to rent by default

Only ADMIN users can:
- Create new videos
- Update existing videos
- Delete videos

Any authenticated user (ADMIN or CUSTOMER) can:
- View the list of available videos

---

# Project Structure
com.yourname.videorental
├── config
│   └── SecurityConfig.java
├── controller
│   ├── PublicController.java
│   ├── AdminController.java
│   └── UserController.java
├── dto
│   └── UserRegistrationRequest.java
├── entity
│   ├── User.java
│   └── Video.java
├── repository
│   ├── UserRepository.java
│   └── VideoRepository.java
├── service
│   ├── UserService.java
│   └── VideoService.java
└── VideoRentalApiApplication.java
