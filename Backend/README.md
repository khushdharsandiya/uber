land ghalu thandapan

# Backend API Documentation

##  `/users/register` Endpoint


### Description:
Registers a new user by creating a user account with the provide information.

### HTTP Method

`POST`

### Endpoint

`users/register`

### Request Body:
The request body should be a JSON format and include the following fields:

- `fullname`: An object containing:
  - `firstname`: A string with a minimum length of 3 characters.
  - `lastname`: A string with a minimum length of 3 characters.
- `email`: A string that must be a valid email address.
- `password`: A string with a minimum length of 6 characters.


## Example Response


- `fullname`: An object containing:
  - `firstname`: A string with a minimum length of 3 characters.
  - `lastname`: A string with a minimum length of 3 characters.
- `email`: A string that must be a valid email address.
- `password`: A string with a minimum length of 6 characters.
