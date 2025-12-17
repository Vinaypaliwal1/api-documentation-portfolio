# Create user

## What this endpoint does

Creates a new user account that can access the application.

## Technical details

### Endpoint

```http
POST /users
```

### Request headers

| Header | Required | Value |
| --- | --- | --- |
| Content-Type | Yes | application/json |
| Authorization | Yes | Bearer <access_token> |

### Example request (curl)

Use this example to test the API from a terminal.

```bash
curl -X POST https://api.example.com/v1/users \
 -H "Authorization: Bearer <access_token>" \
 -H "Content-Type: application/json" \
 -d
  {
   "firstName": "Vinay",
   "lastName": "Paliwal",
   "email": "vinay.paliwal@example.com"
  }
```

### Request body

```json
{
 "firstName": "Vinay",
 "lastName": "Paliwal",
 "email": "vinay.paliwal@example.com"
}
```

#### Request body fields

| Field | Required | Description |
| --- | --- | --- |
| firstName | Yes | User’s first name |
| lastName | Yes | User’s last name |
| email | Yes | Unique email address for the user |

### Success response

HTTP status: `201 Created`

```json
{
 "userId": "u12345",
 "status": "ACTIVE",
 "createdAt": "2025-01-15T10:30:00Z"
}
```

#### Response fields

| Field | Type | Description |
| --- | --- | --- |
| userId | string | Unique identifier for the user |
| status | string | Current status of the user account |
| createdAt | string | Date and time when the user was created (UTC, ISO 8601)|

### Error responses

- 400 Bad Request

  ```json
  {
    "errorCode": "USR\_400",
    "message": "Email is required"
  }
  ```

- 409 Conflict

  ```json
  {
    "errorCode": "USR\_409",
    "message": "User already exists"
  }
  ```






