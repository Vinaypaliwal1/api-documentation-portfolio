\# Quick start



\## How the API works



1\. Your application sends a request with an access token.

2\. The API validates the request.

3\. The API performs the requested user operation.

4\. The API returns a success or error response.



\## What you need



\- API base URL

\- Access token

\- JSON request payload



\## Supported operations



The User Management API supports common user lifecycle operations. Operations can occur independently based on business needs.



User lifecycle operations:



```mermaid

flowchart LR

&nbsp;   A\[Create user] --> B\[Retrieve user]

&nbsp;   B --> C\[Update user]

&nbsp;   C --> D\[Delete user]

