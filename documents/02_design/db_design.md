# Database Design

> Status: 🔒 LOCKED
> Version: v1.0
> Locked by: [Your Name]
> Locked at: YYYY-MM-DD
> Note: Database schema and relationships

## Database: [Database Name]

### Tables

#### users
```json
{
  "id": "INTEGER PRIMARY KEY AUTOINCREMENT",
  "email": "VARCHAR(255) UNIQUE NOT NULL",
  "password_hash": "VARCHAR(255) NOT NULL",
  "name": "VARCHAR(255) NOT NULL",
  "created_at": "TIMESTAMP DEFAULT CURRENT_TIMESTAMP",
  "updated_at": "TIMESTAMP DEFAULT CURRENT_TIMESTAMP"
}
```

#### [Table Name]
```json
{
  "id": "INTEGER PRIMARY KEY AUTOINCREMENT",
  "user_id": "INTEGER REFERENCES users(id)",
  "field1": "VARCHAR(255)",
  "field2": "TEXT",
  "created_at": "TIMESTAMP DEFAULT CURRENT_TIMESTAMP",
  "updated_at": "TIMESTAMP DEFAULT CURRENT_TIMESTAMP"
}
```

## Relationships
- users 1:N [table_name] (one user can have many [records])
- [Add other relationships]

## Indexes
- users.email (UNIQUE)
- [table_name].user_id (for foreign key lookups)

## Sample Data
```json
{
  "users": [
    {
      "id": 1,
      "email": "admin@example.com",
      "name": "Admin User",
      "created_at": "2024-01-01T00:00:00Z"
    }
  ],
  "[table_name]": [
    {
      "id": 1,
      "user_id": 1,
      "field1": "Sample Data",
      "created_at": "2024-01-01T00:00:00Z"
    }
  ]
}
```
