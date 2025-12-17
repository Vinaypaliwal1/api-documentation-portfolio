# Delete user

## What this endpoint does

Deletes an existing user account from the system.  
Business users deactivate users who no longer require access, and developers permanently remove user records.

## Technical details

### Endpoint

```http
DELETE /users/{userId}
```

### Path parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| userId | string | Yes | Unique user identifier. The userId value is returned when a user is created.  |

### Request headers

| Header | Required | Value |
| --- | --- | --- |
| Authorization | Yes | Bearer <access\_token> |

### Example request (curl)

Use this example to delete a user account from a terminal.

```bash
curl -X DELETE https://api.example.com/v1/users/u12345 \
 -H "Authorization: Bearer <access_token>"
```

### Request body

This endpoint does not require a request body.

### Success response

HTTP status: `204 No Content`

No response body is returned when the deletion succeeds.

### Error responses

- 401 Unauthorized

   ```json
   {
    "errorCode": "AUTH_401",
    "message": "Invalid or missing access token",
    "traceId": "abc-401"
   }
   ```  

- 404 Not Found

   ```json
   {
    "errorCode": "USR_404",
    "message": "User not found",
    "traceId": "abc-404"
   }
   ```   

- 409 Conflict

   ```json
   {
    "errorCode": "USR_409",
    "message": "User cannot be deleted due to active dependencies",
    "traceId": "abc-409"
   }
   ```

- 500 Internal Server Error

   ```json
   {
    "errorCode": "SYS_500",
    "message": "Internal server error",
    "traceId": "abc-500"
   }
    ```


[Back to User Management API](../README.md)
