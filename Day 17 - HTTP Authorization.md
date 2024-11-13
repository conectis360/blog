## **Step 1: Understanding Authorization Basics**

### 1.1 Authentication vs. Authorization

- **Authentication** verifies the identity of a user or system (e.g., "Who are you?").
- **Authorization** determines what an authenticated user or system can access (e.g., "What are you allowed to do?").

### 1.2 Role of HTTP Headers

The HTTP `Authorization` header is used to send credentials or tokens as part of a request. For example:
```http
GET /secure-data HTTP/1.1
Host: example.com
Authorization: Bearer <token>
```
## **Step 2: Authorization Mechanisms in HTTP**

### 2.1 Basic Authentication

A simple form of authentication where credentials (username and password) are encoded and sent with every request.

#### Example Request
```http
GET /secure-data HTTP/1.1
Host: example.com
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
```
#### Explanation

- The `username:password` string is Base64-encoded.
- Example of encoding `user:password`:
```bash
echo -n "user:password" | base64
```
- The server decodes the credentials and validates them.
#### Server Response
```http
HTTP/1.1 401 Unauthorized
WWW-Authenticate: Basic realm="Access to secure-data"
```
The `WWW-Authenticate` header prompts the client to provide valid credentials.

---

### 2.2 Bearer Token (OAuth 2.0)

Bearer tokens are used for token-based authentication in systems like OAuth 2.0. Tokens are passed in the `Authorization` header.

#### Example Request
```http
GET /api/data HTTP/1.1
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```
#### Explanation

1. **Token Issuance**: The user authenticates with an identity provider (e.g., Google OAuth) and receives a token.
2. **Token Validation**: The server verifies the token’s validity (e.g., expiration, signature).

#### Example with JWT

A JSON Web Token (JWT) includes claims like user roles:
```json
{
  "sub": "1234567890",
  "name": "John Doe",
  "roles": ["admin"],
  "iat": 1516239022
}
```
### 2.3 API Keys

API keys are a simple mechanism for authorizing requests, often used in server-to-server communications.

#### Example Request
```http
GET /api/data HTTP/1.1
x-api-key: abc123XYZ
```
#### Server Validation

- The server compares the provided key with its stored keys.
- Authorization is granted if the key matches.

---

### 2.4 Digest Authentication

Digest authentication hashes credentials with a nonce (random value) to enhance security compared to Basic Authentication.

#### Server Challenge
```http
HTTP/1.1 401 Unauthorized
WWW-Authenticate: Digest realm="secure",
                   qop="auth",
                   nonce="abc123",
                   opaque="xyz456"
```
Client Response
```http
GET /secure-data HTTP/1.1
Authorization: Digest username="user",
               realm="secure",
               nonce="abc123",
               uri="/secure-data",
               response="5d41402abc4b2a76b9719d911017c592",
               opaque="xyz456"
```
## **Step 3: Role-Based and Attribute-Based Access**

### 3.1 Role-Based Access Control (RBAC)

Authorization is granted based on user roles.

#### Example

- **Admin Role**: Can access all resources.
- **User Role**: Can access only their data.

In Spring Boot, roles can be defined using annotations:
```java
@PreAuthorize("hasRole('ADMIN')")
public ResponseEntity<String> getAdminData() {
    return ResponseEntity.ok("Admin Data");
}
```
### 3.2 Attribute-Based Access Control (ABAC)

Authorization is based on user attributes (e.g., department, region).

#### Example

A user with the attribute `"region": "North America"` can access only North America-specific data.

---

## **Step 4: Implementing Authorization in Practice**

### 4.1 Spring Security Example

Here’s a Spring Boot example implementing Bearer token authorization with JWT.

#### Controller
```java
@RestController
@RequestMapping("/api")
public class SecureController {

    @GetMapping("/admin")
    @PreAuthorize("hasRole('ADMIN')")
    public String adminEndpoint() {
        return "Welcome Admin";
    }

    @GetMapping("/user")
    @PreAuthorize("hasRole('USER')")
    public String userEndpoint() {
        return "Welcome User";
    }
}
```
Security Configuration
```java
@EnableWebSecurity
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .authorizeRequests()
                .antMatchers("/api/admin").hasRole("ADMIN")
                .antMatchers("/api/user").hasRole("USER")
                .anyRequest().authenticated()
            .and()
            .oauth2ResourceServer().jwt(); // Configures JWT validation
    }
}
```
## **Step 5: Testing Authorization**

### 5.1 Valid Request

A user with a valid token sends:
```http
GET /api/admin HTTP/1.1
Authorization: Bearer validToken
```
Response
```http
HTTP/1.1 200 OK
Welcome Admin
```
### 5.2 Invalid Request

A user with an invalid token sends:
```http
GET /api/admin HTTP/1.1
Authorization: Bearer invalidToken
```
Response
```http
HTTP/1.1 403 Forbidden
```
## **tep 6: Best Practices**

1. **Use Secure Protocols**: Always use HTTPS to protect credentials and tokens.
2. **Token Expiry**: Set short lifetimes for tokens to limit the impact of theft.
3. **Token Refresh**: Implement refresh tokens to allow users to obtain new access tokens without re-authentication.
4. **Audit and Logging**: Log authorization attempts for auditing and monitoring.