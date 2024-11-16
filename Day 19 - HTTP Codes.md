HTTP status codes are part of the HTTP protocol and are used to indicate the result of a client's request to a server. They are grouped into five categories, with each category providing specific information about the outcome of the request.

---

## **1. Informational Responses (100–199)**

### Characteristics:

- These codes are provisional and indicate that the initial part of the request has been received and further action is being taken.

### Examples:

#### **100 Continue**

- **Meaning:** The server acknowledges the request headers and is ready for the client to send the body (e.g., in a `POST` request).
- **Use Case:** Large file uploads to ensure headers are correct before sending the full payload.

#### **101 Switching Protocols**

- **Meaning:** The server agrees to switch to a different protocol (e.g., from HTTP to WebSocket) as requested by the client.
- **Use Case:** Establishing WebSocket connections.

#### **103 Early Hints**

- **Meaning:** Used to hint at resources the client should preload before the final response.
- **Use Case:** Optimizing page loading by preloading assets.

---

## **2. Success Responses (200–299)**

### Characteristics:

- These codes indicate that the request was successfully received, understood, and accepted.

### Examples:

#### **200 OK**

- **Meaning:** The request succeeded, and the server returned the requested data.
- **Use Case:** Returning data for a `GET` request.

#### **201 Created**

- **Meaning:** A resource was successfully created as a result of the request.
- **Use Case:** After a successful `POST` request to create a new resource.
#### **202 Accepted**

- **Meaning:** The request has been accepted but has not yet been processed.
- **Use Case:** Long-running background processes (e.g., batch uploads).

#### **204 No Content**

- **Meaning:** The request was successful, but there is no content to send in the response.
- **Use Case:** Successful deletion of a resource (`DELETE` request).

---

## **3. Redirection Responses (300–399)**

### Characteristics:

- These codes indicate that the client must take additional actions to complete the request (e.g., follow a different URL).

### Examples:

#### **301 Moved Permanently**

- **Meaning:** The requested resource has been moved to a new permanent URL.
- **Use Case:** Redirecting from an old domain to a new domain.

#### **302 Found**

- **Meaning:** The requested resource temporarily resides at another URL.
- **Use Case:** Temporary redirection.

#### **303 See Other**

- **Meaning:** The response should be retrieved using a `GET` request to a different URL.
- **Use Case:** Redirecting after a successful form submission.

#### **304 Not Modified**

- **Meaning:** The requested resource has not changed since the last access, and the cached version can be used.
- **Use Case:** Efficient caching mechanisms to reduce bandwidth usage.

#### **307 Temporary Redirect**

- **Meaning:** A temporary redirect where the original HTTP method must be used for the new request.
- **Use Case:** Temporary URL changes without altering the HTTP method.

---

## **4. Client Error Responses (400–499)**

### Characteristics:

- These codes indicate that the client made an error in the request.

### Examples:

#### **400 Bad Request**

- **Meaning:** The server cannot process the request due to malformed syntax.
- **Use Case:** Sending invalid JSON data.

#### **401 Unauthorized**

- **Meaning:** Authentication is required but has not been provided or is invalid.
- **Use Case:** Accessing protected resources without a valid token.

#### **403 Forbidden**

- **Meaning:** The client is authenticated but does not have permission to access the resource.
- **Use Case:** Attempting to access an admin-only page as a regular user.

#### **404 Not Found**

- **Meaning:** The server cannot find the requested resource.
- **Use Case:** Requesting a non-existent API endpoint or URL.

#### **405 Method Not Allowed**

- **Meaning:** The HTTP method used is not supported for the resource.
- **Use Case:** Sending a `POST` request to an endpoint that only supports `GET`.

#### **429 Too Many Requests**

- **Meaning:** The client has sent too many requests in a given time frame.
- **Use Case:** Rate limiting APIs.

---

## **5. Server Error Responses (500–599)**

### Characteristics:

- These codes indicate that the server encountered an error and was unable to process the request.

### Examples:

#### **500 Internal Server Error**

- **Meaning:** A generic error indicating the server encountered an unexpected condition.
- **Use Case:** Unhandled exceptions in server-side code.

#### **501 Not Implemented**

- **Meaning:** The server does not support the functionality required to fulfill the request.
- **Use Case:** A server that does not support a specific HTTP method.

#### **502 Bad Gateway**

- **Meaning:** The server received an invalid response from an upstream server.
- **Use Case:** Issues with reverse proxies or load balancers.

#### **503 Service Unavailable**

- **Meaning:** The server is temporarily unable to handle the request due to maintenance or overload.
- **Use Case:** Scheduled maintenance windows.

#### **504 Gateway Timeout**

- **Meaning:** The server did not receive a timely response from an upstream server.
- **Use Case:** A timeout occurred while querying a database.