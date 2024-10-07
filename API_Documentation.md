<style>
    /* Enable smooth scrolling */
    @media screen and (prefers-reduced-motion: no-preference) {
        html {
            scroll-behavior: smooth;
        }
    }

    /* Style the button */
    .top-link {
    transition:       all .25s ease-in-out;
    position:         fixed;
    bottom:           0;
    right:            0;
    display:          inline-flex;
    color:            #000000;
    font-size:        2.5em;

    cursor:           pointer;
    align-items:      center;
    justify-content:  center;
    margin:           0 1.5em 1.5em 0;
    border-radius:    50%;
    padding:          .25em;
    width:            1.5em;
    height:           1.5em;
    background-color: #F8F8F8;
    }
</style>


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


<a class="top-link hide" href="#top">↑</a>
<a name="top"></a>