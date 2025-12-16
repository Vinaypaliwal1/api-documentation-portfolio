\# Delete user



\## What this endpoint does



Deletes an existing user account from the system.  

Business users deactivate users who no longer require access, and developers permanently remove user records.



\## Technical Details



\### Endpoint



```http

DELETE /users/{userId}

```



\### Path parameters



| Parameter | Type | Required | Description |

| --- | --- | --- | --- |

| userId | string | Yes | Unique user identifier. The userId value is returned when a user is created.  |



\### Request headers



| Header | Required | Value |

| --- | --- | --- |

| Authorization | Yes | Bearer <access\_token> |





\### Example request (curl)



Use this example to delete a user account from a terminal.



```bash

curl -X DELETE https://api.example.com/v1/users/u12345 \\

&nbsp; -H "Authorization: Bearer <access\_token>"

```



\### Request body



This endpoint does not require a request body.



\### Success response



HTTP status: `204 No Content`



No response body is returned when the deletion succeeds.





\### Error responses



* 401 Unauthorized



&nbsp;  ```json

&nbsp;  {

&nbsp;   "errorCode": "AUTH\_401",

&nbsp;   "message": "Invalid or missing access token",

&nbsp;   "traceId": "abc-401"

&nbsp;  }

&nbsp;  ```

&nbsp;  

* 404 Not Found



&nbsp;  ```json

&nbsp;  {

&nbsp;   "errorCode": "USR\_404",

&nbsp;   "message": "User not found",

&nbsp;   "traceId": "abc-404"

&nbsp; }

&nbsp; ```   



* 409 Conflict



&nbsp;  ```json

&nbsp;  {

&nbsp;   "errorCode": "USR\_409",

&nbsp;   "message": "User cannot be deleted due to active dependencies",

&nbsp;   "traceId": "abc-409"

&nbsp; }

&nbsp; ```



* 500 Internal Server Error



&nbsp;  ```json

&nbsp;  {

&nbsp;   "errorCode": "SYS\_500",

&nbsp;   "message": "Internal server error",

&nbsp;   "traceId": "abc-500"

&nbsp; }

&nbsp; ```

