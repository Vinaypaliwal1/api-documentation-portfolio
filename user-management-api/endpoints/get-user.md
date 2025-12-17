# Get user

## What this endpoint does

Retrieves user details by using a unique user identifier.  
Business users can verify user information, and developers can retrieve profile data for application workflows.

## Technical details

### Endpoint

```http
GET /users/{userId}
```

### Path parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| userId | string | Yes | Unique user identifier. The userId value is returned when a user is created.  |

### Request headers

| Header | Required | Value |
| --- | --- | --- |
| Authorization | Yes | Bearer <access_token> |

### Example request (curl)

Use this example to retrieve user details from a terminal.

```bash
curl -X GET https://api.example.com/v1/users/u12345 \
 -H "Authorization: Bearer <access\_token>"
```

### Success response 

HTTP status: `200 OK`

```json
{
 "userId": "u12345",
 "firstName": "Vinay",
 "lastName": "Paliwal",
 "email": "vinay.paliwal@example.com",
 "status": "ACTIVE"
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

### Error responses

- 404 Not Found

   ```json
   {
    "errorCode": "USR\_404",
    "message": "User not found"
   }
   ```



