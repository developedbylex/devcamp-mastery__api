<h1 align="center">🚀 Devcamp Mastery API</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
</p>

<p align="center">
  A comprehensive REST API for managing bootcamps, courses, reviews, and user authentication built with Node.js, Express, and MongoDB.
</p>

---

## 📋 Table of Contents

- [Description](#description)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## 📖 Description

Devcamp Mastery is a backend REST API designed to handle operations for an educational platform. It provides endpoints for managing bootcamps, courses, user reviews, authentication, and administrative tasks. The API includes features like user registration, JWT-based authentication, file uploads, geocoding for location-based queries, and email notifications.

## ✨ Features

- 🔐 **User Authentication & Authorization**: Register, login, password reset, and role-based access control (user, publisher, admin)
- 🎓 **Bootcamp Management**: Create, read, update, delete bootcamps with photo uploads and location-based search
- 📚 **Course Management**: Manage courses associated with bootcamps
- ⭐ **Review System**: Users can create and manage reviews for bootcamps
- 👨‍💼 **Admin Panel**: Administrative functions for user management
- 🛡️ **Security**: Helmet, XSS protection, MongoDB sanitization, rate limiting, CORS
- ⚡ **Caching**: API response caching for improved performance
- 📁 **File Uploads**: Support for photo uploads with size limits
- 📍 **Geocoding**: Location-based queries using zipcode and distance
- 📧 **Email Notifications**: SMTP-based email sending for password resets, etc.

## 🛠️ Tech Stack

| Category           | Technology                                                 |
| ------------------ | ---------------------------------------------------------- |
| **Backend**        | Node.js, Express.js                                        |
| **Database**       | MongoDB with Mongoose ODM                                  |
| **Authentication** | JSON Web Tokens (JWT)                                      |
| **Security**       | Helmet, express-mongo-sanitize, express-xss-sanitizer, hpp |
| **Caching**        | apicache                                                   |
| **File Uploads**   | express-fileupload                                         |
| **Geocoding**      | node-geocoder                                              |
| **Email**          | nodemailer                                                 |
| **Other**          | bcryptjs, slugify, colors                                  |

## Usage

### 🏥 Health Check

- **GET /** or **GET /health**: Check if the API is running.

### 🔐 Authentication Endpoints (`/api/v1/auth`)

- **POST /register**: Register a new user
- **POST /login**: Login user
- **GET /me**: Get current user info (requires auth)
- **GET /logout**: Logout user (requires auth)
- **POST /forgot-password**: Request password reset
- **PUT /reset-password/:reset_token**: Reset password with token
- **PUT /update-info**: Update user info (requires auth)
- **PUT /update-password**: Update password (requires auth)

### 🎓 Bootcamps Endpoints (`/api/v1/bootcamps`)

- **GET /**: Get all bootcamps (with filtering)
- **POST /**: Create a new bootcamp (publisher auth required)
- **GET /:id**: Get bootcamp by ID
- **PUT /:id**: Update bootcamp (publisher auth required)
- **DELETE /:id**: Delete bootcamp (publisher auth required)
- **PUT /:id/photo**: Upload bootcamp photo (publisher auth required)
- **GET /radius/:zipcode/:distance**: Get bootcamps within radius

### 📚 Courses Endpoints (`/api/v1/courses`)

- **GET /**: Get all courses (with filtering)
- **POST /**: Create a new course (publisher auth required)
- **GET /:id**: Get course by ID
- **PUT /:id**: Update course (publisher auth required)
- **DELETE /:id**: Delete course (publisher auth required)

### ⭐ Reviews Endpoints (`/api/v1/reviews`)

- **GET /**: Get all reviews (with filtering)
- **POST /**: Create a new review (user auth required)
- **GET /:id**: Get review by ID
- **PUT /:id**: Update review (user auth required)
- **DELETE /:id**: Delete review (user auth required)

### 👨‍💼 Admin Endpoints (`/api/v1/admin`) - Admin auth required for all

- **GET /users**: Get all users
- **POST /users**: Create a new user
- **GET /users/:userId**: Get user by ID
- **PUT /users/:userId**: Update user
- **DELETE /users/:userId**: Delete user

## 📚 API Documentation

For detailed API documentation, including request/response examples and parameters, visit [https://developedbylex.github.io/devcamp](https://developedbylex.github.io/devcamp).

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**[developedbylex](https://github.com/developedbylex)**

---

> _Note: This API is part of the Devcamp Mastery platform. Ensure you have MongoDB running locally or provide a valid DB_URI for cloud databases._
