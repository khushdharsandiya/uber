# Backend API Documentation

##  `/users/register` Endpoint


### Description:
Registers a new user by creating a user account with the provided information.

### HTTP Method

`POST`


### Request Body:
The request body should be a JSON format and include the following fields:

- `fullname` (object):
  - `firstname` (string, required): User's first name (minimum 3 characters).
  - `lastname` (string, optional): User's last name (minimum 3 characters).
- `email` (string, required): User's email address (must be a valid email).
- `password` (string, required): User's password (minimum 6 characters).

## Example Response


- `user` (object).
  - `fullname` (object).
    -`firstname`(string): User's first name (minimum 3 characters).
    - `lastname` (string): User's last name (minimum 3 characters).
  - `email`(string): User's email address (must be a valid email).
  - `password`(string): User's password (minimum 6 characters).
- `token` (String): JWT Token

## `/users/login` Endpoint

### Description:
Authenticates a user and returns a JWT token if the credentials are valid.

### HTTP Method

`POST`

### Request Body:
The request body should be in JSON format and include the following fields:

- `email` (string, required): User's email address (must be a valid email).
- `password` (string, required): User's password (minimum 6 characters).

## Example Response

- `user` (object).
  - `fullname` (object).
    - `firstname` (string): User's first name.
    - `lastname` (string): User's last name.
  - `email` (string): User's email address.
- `token` (string): JWT Token



## `/users/profile` Endpoint

### Description:
Retrieves the profile information of the authenticated user.

### HTTP Method

`GET`

### Authentication:
Requires a valid JWT token in Authorization header or cookie.
`Authoraization: Bearer <token>`

## Example Response

- `user` (object).
  - `fullname` (object).
    -`firstname`(string): User's first name (minimum 3 characters).
    - `lastname` (string): User's last name (minimum 3 characters).
  - `email`(string): User's email address (must be a valid email).



## `/users/logout` Endpoint

### Description:
Logout the current user and blacklist the token provided in cookie headers.

### HTTP Method

`GET`

### Authentication:
Requires a valid JWT token in Authorization header or cookie.

## `/captain/register` Endpoint

### Description:
Registers a new captain by creating a captain account with the provided information.

### HTTP Method

`POST`

### Request Body:
The request body should be in JSON format and include the following fields:

- `fullname` (object):
  - `firstname` (string, required): Captain's first name (minimum 3 characters)
  - `lastname` (string, optional): Captain's last name
- `email` (string, required): Captain's email address (must be a valid email)
- `password` (string, required): Captain's password (minimum 6 characters)
- `vehicle` (object):
  - `color` (string, required): Vehicle color (minimum 3 characters)
  - `plate` (string, required): Vehicle plate number (minimum 3 characters)
  - `capacity` (number, required): Vehicle passenger capacity (minimum 1)
  - `vehicleType` (string, required): Type of vehicle ('car', 'motorcycle', or 'auto')

### Example Response:
```json
{
  "captain": {
    "fullname": {
      "firstname": "John",
      "lastname": "Doe"
    },
    "email": "john.doe@example.com",
    "vehicle": {
      "color": "black",
      "plate": "ABC123",
      "capacity": 4,
      "vehicleType": "car"
    }
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}


