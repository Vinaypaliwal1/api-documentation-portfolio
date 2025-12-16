\# Error handling



The API returns standard HTTP status codes to indicate the outcome of a request.



\## Error response format



```json

{

&nbsp; "errorCode": "string",

&nbsp; "message": "string",

&nbsp; "traceId": "string"

}

```



\## How to read errors



Each error response includes:

\- An error code that support teams can use for investigation

\- A human-readable message that describes the issue

\- A trace ID that helps identify the request in logs



\## Example



```json

{

&nbsp; "errorCode": "USR\_404",

&nbsp; "message": "User not found",

&nbsp; "traceId": "abc-123"

}

```



\## Common errors



| Status | Description |

| --- | --- |

| 400 |	Invalid request |

| 401 |	Unauthorized |

| 404 |	Resource not found |

| 409 |	Conflict |

| 500 |	Internal server error |

