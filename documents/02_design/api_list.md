# API List

> Status: 🔒 LOCKED
> Version: v1.0
> Locked by: [Your Name]
> Locked at: YYYY-MM-DD
> Note: Backend API endpoints specification

## Authentication
### POST /api/auth/login
- **Description:** User login
- **Request:**
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "token": "jwt_token_here",
    "user": {
      "id": 1,
      "email": "user@example.com",
      "name": "User Name"
    }
  }
  ```

### POST /api/auth/register
- **Description:** User registration
- **Request:**
  ```json
  {
    "email": "user@example.com",
    "password": "password123",
    "name": "User Name"
  }
  ```
- **Response:**
  ```json
  {
    "token": "jwt_token_here",
    "user": {
      "id": 1,
      "email": "user@example.com",
      "name": "User Name"
    }
  }
  ```

## User Management
### GET /api/users/profile
- **Description:** Get user profile
- **Headers:** Authorization: Bearer {token}
- **Response:**
  ```json
  {
    "id": 1,
    "email": "user@example.com",
    "name": "User Name",
    "created_at": "2024-01-01T00:00:00Z"
  }
  ```

### PUT /api/users/profile
- **Description:** Update user profile
- **Headers:** Authorization: Bearer {token}
- **Request:**
  ```json
  {
    "name": "New Name",
    "email": "new@example.com"
  }
  ```

## [Add more API endpoints as needed]
