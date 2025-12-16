\# Authentication



The API uses JWT bearer token authentication.



\## Authorization header



Include the access token in the `Authorization` header of each request.



```http

Authorization: Bearer <access\_token>

```



\## Token Usage



* Obtain the access token from the authentication service.
* Include the token in all API requests.



\## Unauthorized Response Example



HTTP status: `401 Unauthorized`



```json

{

&nbsp; "errorCode": "AUTH\_401",

&nbsp; "message": "Invalid or missing access token"

}

```

