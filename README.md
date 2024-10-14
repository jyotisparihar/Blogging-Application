# Java Blogging Application

This is a Java-based blogging application built with **Spring Boot** that provides a comprehensive set of RESTful APIs for managing blog posts, comments, categories, user authentication, and authorization. The application is secured with **Spring Security** and **JWT (JSON Web Token)** for role-based access control.

## Features

- **CRUD Operations**: Create, Read, Update, Delete for blog posts, comments, and categories.
- **User Authentication and Authorization**: Sign up, log in, and secure APIs using **JWT** and **Spring Security** with role-based access control.
- **Pagination and Sorting**: APIs support pagination and sorting for listing blog posts.
- **Validation and Exception Handling**: Includes input validation and error handling.
- **Entity Relationships**: Implements **one-to-many** and **many-to-many** JPA mappings for entities.
- **DTOs**: Uses **Data Transfer Objects (DTOs)** to decouple the data layer from the API layer.
- **Postman Testing**: API testing has been done using **Postman**.

## Technologies Used

- **Java 11** or later
- **Spring Boot**
    - Spring Data JPA (with **Hibernate**)
    - Spring Security
    - **JWT (JSON Web Token)**
    - Spring Boot Validation
- **MySQL** database
- **Lombok** for reducing boilerplate code
- **Maven** as a build tool

## API Endpoints

### Authentication

- **POST** `/api/v1/auth/signup`  
  Register a new user.

- **POST** `/api/v1/auth/login`  
  Authenticate user and generate a JWT token.

### Blog Post APIs

- **POST** `/api/v1/posts`  
  Create a new blog post.

- **GET** `/api/v1/posts`  
  Get all blog posts (supports pagination and sorting).

- **GET** `/api/v1/posts/{id}`  
  Get a single blog post by ID.

- **PUT** `/api/v1/posts/{id}`  
  Update an existing blog post by ID.

- **DELETE** `/api/v1/posts/{id}`  
  Delete a blog post by ID.

### Comment APIs

- **POST** `/api/v1/posts/{postId}/comments`  
  Add a comment to a blog post.

- **GET** `/api/v1/posts/{postId}/comments`  
  Get all comments for a blog post.

- **DELETE** `/api/v1/comments/{commentId}`  
  Delete a comment by its ID.

### Category APIs

- **POST** `/api/v1/categories`  
  Create a new category.

- **GET** `/api/v1/categories`  
  Get all categories.

- **GET** `/api/v1/categories/{id}`  
  Get a single category by ID.

- **PUT** `/api/v1/categories/{id}`  
  Update a category by ID.

- **DELETE** `/api/v1/categories/{id}`  
  Delete a category by ID.

## Security and Authentication
- **Spring Security** and **JWT** have been implemented for authentication and authorization.
- Role-based access control ensures that only authenticated users with the proper roles (e.g., `ADMIN`, `USER`) can access certain APIs.
## JWT Token Flow:
- **Login** using the `/auth/login` API with username and password to generate a JWT token.
- Use the generated token in the `Authorization` header for subsequent requests to secured APIs.