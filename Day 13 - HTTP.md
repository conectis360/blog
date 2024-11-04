### HTTP Overview

- **Definition**: HTTP is the foundational protocol used for transmitting data on the web. It defines how messages are formatted and transmitted, and how web servers and browsers should respond to various commands.

### Flashcards

1. **Q**: What does HTTP stand for?  
    **A**: Hypertext Transfer Protocol.
    
2. **Q**: What is the main purpose of HTTP?  
    **A**: To facilitate the transfer of data between a client (usually a web browser) and a server on the internet.
    
3. **Q**: What is a client in the context of HTTP?  
    **A**: A client is an application (e.g., web browser) that sends requests to a server for web content.
    
4. **Q**: What is a server in HTTP?  
    **A**: A server is a system that hosts and serves web content to clients upon receiving HTTP requests.
    
5. **Q**: What is an HTTP request?  
    **A**: An HTTP request is a message sent by the client to the server asking for a specific resource (e.g., a web page or file).
    
6. **Q**: What is an HTTP response?  
    **A**: An HTTP response is the message sent back from the server to the client, containing the requested resource or an error message.
    
7. **Q**: What are the main HTTP methods?  
    **A**:
    
    - **GET**: Requests data from a specified resource.
    - **POST**: Submits data to be processed to a specified resource.
    - **PUT**: Updates or replaces a resource.
    - **DELETE**: Deletes a specified resource.
8. **Q**: What does the status code `200 OK` indicate?  
    **A**: It means the HTTP request was successful and the server has returned the requested resource.
    
9. **Q**: What does the status code `404 Not Found` mean?  
    **A**: It indicates that the requested resource could not be found on the server.
    
10. **Q**: What is the significance of `HTTPS`?  
    **A**: HTTPS stands for HTTP Secure, which encrypts data transferred between the client and server using SSL/TLS to ensure data privacy and security.
    
11. **Q**: What is the function of HTTP headers?  
    **A**: HTTP headers provide essential metadata about the request or response, such as content type, content length, and caching policies.
    
12. **Q**: What does the `User-Agent` header do?  
    **A**: It identifies the client’s application type, operating system, and version to the server.
    
13. **Q**: What is a cookie in the context of HTTP?  
    **A**: A small piece of data sent by the server and stored on the client’s device to remember stateful information for future requests.
    
14. **Q**: What does `Stateless Protocol` mean regarding HTTP?  
    **A**: HTTP is stateless, meaning each request from a client to a server is independent, and the server does not retain any state information about past requests.
    
15. **Q**: Why is `302 Found` or `301 Moved Permanently` used?  
    **A**: These status codes indicate that the requested resource has been temporarily or permanently moved to a different URI.
    
16. **Q**: What is the purpose of the `Content-Type` header?  
    **A**: It informs the client about the type of data returned (e.g., `text/html`, `application/json`).
    
17. **Q**: What does the `Cache-Control` header do?  
    **A**: It specifies caching policies to optimize the retrieval of resources, indicating whether or how long a resource can be cached.
    
18. **Q**: What role does a proxy server play in HTTP?  
    **A**: A proxy server acts as an intermediary between the client and the server to filter requests, enhance security, and cache responses for faster access.
    

### Quick Summary of HTTP Life-cycle

- **Client Initiates Request**: The client sends an HTTP request to a server using a specific method (e.g., GET, POST).
- **Server Processes Request**: The server processes the request, retrieves the required data, or performs the action.
- **Response Sent Back**: The server responds with an HTTP status code, headers, and the requested data (if applicable).
- **Client Processes Response**: The client processes the response and renders content accordingly.