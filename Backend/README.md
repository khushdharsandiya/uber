# User Registration API Documentation

## Register User
Registers a new user in the system.

### Endpoint
```
POST /users/register
```

### Request Body
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| email | string | Yes | User's email address |
| fullname.firstname | string | Yes | User's first name (min 3 characters) |
| fullname.lastname | string | No | User's last name (min 3 characters if provided) |
| password | string | Yes | User's password (min 6 characters) |

### Example Request
```json
{
  "email": "john.doe@example.com",
  "fullname": {
    "firstname": "John",
    "lastname": "Doe"
  },
  "password": "securepassword123"
}
```

### Responses

#### Success Response
- **Status**: 201 Created
```json
{
  "token": "jwt_token_here",
  "user": {
    "_id": "user_id",
    "email": "john.doe@example.com",
    "fullname": {
      "firstname": "John",
      "lastname": "Doe"
    }
  }
}
```

#### Error Responses

##### Validation Error
- **Status**: 400 Bad Request
```json
{
  "errors": [
    {
      "msg": "Invalid Email",
      "param": "email",
      "location": "body"
    }
  ]
}
```

##### User Already Exists
- **Status**: 400 Bad Request
```json
{
  "message": "User already exist"
}
```

### Validation Rules
- Email must be a valid email address
- First name must be at least 3 characters long
- Password must be at least 6 characters long
- Last name, if provided, must be at least 3 characters long

### Example Response
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "_id": "60d0fe4f5311236168a109ca",
    "email": "john.doe@example.com",
    "fullname": {
      "firstname": "John",
      "lastname": "Doe"
    }
  }
}
```
