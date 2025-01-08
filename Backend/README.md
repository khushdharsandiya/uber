# Captain Routes Documentation

## `/captain/register` Endpoint

### Description:
Register a new captain account with vehicle details and license information.

### HTTP Method
`POST`

### Request Body:
The request body should be in JSON format and include the following fields:

-`fullname` (object):
   -`firstname` (string, required): Captain's first name (minimum 3 characters)
   -`lastname` (string, optional): Captain's last name
-`email` (string, required): Captain's email address (must be a valid email)
-`password` (string, required): Captain's password (minimum 6 characters)
-`vehicle` (object):
   -`color` (string, required): Vehicle color (minimum 3 characters)
   -`plate` (string, required): Vehicle plate number (minimum 3 characters)
   -`capacity` (number, required): Vehicle passenger capacity (minimum 1)
   -`vehicleType` (string, required): Type of vehicle (must be 'car', 'motorcycle', or 'auto')

### Example Response:

- `user` (object).
  - `fullname` (object).
    -`firstname`(string): User's first name 
    - `lastname` (string): User's last name 
  - `email`(string): User's email address   
  - `password`(string): User's password     
  - `vahicle`(object)
    - `color`(string) vehicle color
    - `capacity` (number) vehicle capacity
    - `vahicleType` (string) vehicle type
    - `plate` (string) vehicle plate number
- `token` (String): JWT Token

## `/captain/login` Endpoint

### Description:
Authenticate a captain and get access token.

### HTTP Method
`POST`

### Request Body:
```json
{
  "email": "john.captain@example.com",
  "password": "password123"
}
```

### Response:
- **Success (200 OK)**
```json
{
  "token": "jwt_token_here",
  "captain": {
    "_id": "captain_id",
    "fullname": {
      "firstname": "John",
      "lastname": "Doe"
    },
    "email": "john.captain@example.com",
    "status": "offline"
  }
}
```
