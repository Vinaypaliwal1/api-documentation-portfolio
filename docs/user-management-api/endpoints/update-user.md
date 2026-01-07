# Update user

## What this endpoint does

Updates an existing user’s profile information.  
Business teams use this to keep user data accurate, while developers use it to modify stored user details.

## Technical details

### Endpoint

```http
PUT /users/{userId}
```

### Path parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| userId | string | Yes | Unique user identifier. The userId value is returned when a user is created.  |

### Request headers

| Header | Required | Value |
| --- | --- | --- |
| Content-Type | Yes | application/json |
| Authorization | Yes | Bearer <access_token> |

### Request body

```json
{
  "firstName": "Vinay",
  "lastName": "Paliwal"
}
```

<div style=" background-color: #e7f0fd; border-left: 4px solid #6495ED; padding: 10px 12px; margin: 12px 0; "> <strong>Note:</strong> Include only the fields that require updates. </div>

#### Request body fields

| Field | Required | Description |
|--- | --- | --- |
| firstName | Yes | User’s first name |
| lastName | Yes | User’s last name | 

### Success response

HTTP status: `200 OK`

```json
{
 "userId": "u12345",
 "firstName": "Vinay",
 "lastName": "Paliwal",
 "email": "vinay.paliwal@example.com",
 "status": "ACTIVE",
 "updatedAt": "2025-01-16T11:20:00Z"
}
```

#### Response fields

| Field | Type | Description |
| --- | --- | --- |
| userId | string | Unique identifier for the user |
| firstName | string | User’s first name |
| lastName | string | User’s last name |
| email | string | Email address associated with the user |
| status | string | Current status of the user account |
| updatedAt | string | Timestamp of last update (ISO 8601) |

### Error responses

- 404 Not Found

  ```json
  {
   "errorCode": "USR_404",
   "message": "User not found"
  }
  ```



[Back to User Management API](../README.md)
