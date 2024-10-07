# API Documentation

## Index
- [API Documentation](#api-documentation)
  - [Index](#index)
  - [Endpoints](#endpoints)
    - [`/auth/register`](#authregister)
    - [`/auth/login`](#authlogin)


## Endpoints

### `/auth/register`
- **Method:** POST
- **Description:** To register a new user
- **Request Body:**
    - `displayName`  *(required, string)*
    - `email`  *(required, string)*
    - `password`  *(required, string)*
- **Respone:**
    - `201 Created` : User registered successfully  
    **Response object :** 
        - *message*
    - `400 Bad Request` : Invalid request body  
    **Response object :** 
        - *message*
    - `409 Conflict` : Existing email  
    **Response object :** 
        - *message*
    - `500 Internal Server Error`  
    **Response object :** 
        - *message*
---
### `/auth/login`
- **Method:** POST
- **Description:** To log in an existing user
- **Request Body:**
    - `email`  *(required, string)*
    - `password`  *(required, string)*
- **Response:**
    - `200 OK` : Successful login.  
    **Response object :**
        - *token* : JWT session token
    - `400 Bad Request` : Invalid request body  
    **Response object :** 
        - *message*
    - `401 Unauthorized` : Invalid username or password  
    **Response object :** 
        - *message*
    - `404 Not Found` : User not found  
    **Response object :** 
        - *message*
    - `500 Internal Server Error`  
    **Response object :** 
        - *message*
---