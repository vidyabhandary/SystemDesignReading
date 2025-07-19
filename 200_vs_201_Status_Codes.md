## 200 vs 201 Status Codes

HTTP status codes communicate the result of a server's attempt to process a client's request. Both **200** and **201** are success codes, but they are used in different scenarios:

#### HTTP 200 OK

- **Meaning:** The request has succeeded.
- **Typical Use:** Returned for successful **GET**, **PUT**, **PATCH**, and **DELETE** requests.
- **Implication:** The server successfully processed the request, and the response body (if any) contains the requested data or confirmation.
- **Example:** Retrieving a user profile with a GET request, updating a resource with a PUT request.
  * A `GET /users/123` returns a user profile → **200 OK**

#### HTTP 201 Created

- **Meaning:** The request has succeeded **and a new resource has been created** as a result.
- **Typical Use:** Most commonly returned from **POST** requests.
- **Implication:** The server has created a new resource in response to the client’s request. Usually, the response includes a `Location` header that points to the URL of the newly created resource.
- **Example:** Creating a new user account or posting a new entry to a database.

  * A `POST /users` that creates a new user → **201 Created**
  * Often includes a `Location` header pointing to the new resource.


#### Comparison Table

| Code | Name | When Used | Typical Methods | Additional Info |
| :-- | :-- | :-- | :-- | :-- |
| 200 | OK | Successful operations, no creation | GET, PUT, PATCH, DELETE | Returns requested data or confirmation |
| 201 | Created | Resource created as a result | POST | Returns resource URI in `Location` header |

**Summary:**

- Use **200 OK** for successful operations that do not result in resource creation.
- Use **201 Created** specifically when a new resource has been created as a result of the request.

