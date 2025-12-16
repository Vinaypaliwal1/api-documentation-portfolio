\# Create user



\## What this endpoint does



Creates a new user account that can access the application.





\## Technical details



\### Endpoint



```http

POST /users

```



\### Request headers



| Header | Required | Value |

| --- | --- | --- |

| Content-Type | Yes | application/json |

| Authorization | Yes | Bearer <access\_token> |


### Example request (curl)

Use this example to test the API from a terminal.

```bash

curl -X POST https://api.example.com/v1/users \\

&nbsp; -H "Authorization: Bearer <access\_token>" \\

&nbsp; -H "Content-Type: application/json" \\

&nbsp; -d '{

&nbsp;   "firstName": "Vinay",

&nbsp;   "lastName": "Paliwal",

&nbsp;   "email": "vinay.paliwal@example.com"

&nbsp; }'

```



\### Request body



```json

{

&nbsp; "firstName": "Vinay",

&nbsp; "lastName": "Paliwal",

&nbsp; "email": "vinay.paliwal@example.com"

}
```



\#### Request body fields



| Field | Required | Description |

|------|----------|-------------|

| firstName | Yes | User’s first name |

| lastName | Yes | User’s last name |

| email | Yes | Unique email address for the user |





\### Success response



HTTP status: `201 Created`



```json

{

&nbsp; "userId": "u12345",

&nbsp; "status": "ACTIVE",

&nbsp; "createdAt": "2025-01-15T10:30:00Z"

}

```



\#### Response fields





| Field | Type | Description |

| --- | --- | --- |

| userId | string | Unique identifier for the user |

| status | string | Current status of the user account |

| createdAt | string | Date and time when the user was created (UTC, ISO 8601)|





\### Error responses



* 400 Bad Request



&nbsp;  ```json

&nbsp; {

&nbsp;   "errorCode": "USR\_400",

&nbsp;   "message": "Email is required"

&nbsp; }

&nbsp; ```

* 409 Conflict



&nbsp; ```json

&nbsp; {

&nbsp;   "errorCode": "USR\_409",

&nbsp;   "message": "User already exists"

&nbsp; }

&nbsp; ```





\### Example request (curl)



Use this example to test the API from a terminal.



```bash

curl -X POST https://api.example.com/v1/users \\

&nbsp; -H "Authorization: Bearer <access\_token>" \\

&nbsp; -H "Content-Type: application/json" \\

&nbsp; -d '{

&nbsp;   "firstName": "Vinay",

&nbsp;   "lastName": "Paliwal",

&nbsp;   "email": "vinay.paliwal@example.com"

&nbsp; }'

```





