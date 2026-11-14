
# Auth Service

The Auth Service is a core microservice of the **TenantSphere** platform, responsible for centralized authentication, identity security, and secure access management across the distributed system.

It manages user authentication workflows, including registration, login, logout, JWT-based authentication, and refresh token rotation. The service securely stores authentication credentials and refresh tokens in PostgreSQL and integrates with other microservices to provide a consistent and secure authentication mechanism.

## Key Responsibilities

- User registration and login authentication.
- JWT access token generation and validation.
- Refresh token generation, rotation, and revocation.
- Secure password hashing and verification.
- User logout and session management.
- Account activation and password reset.
- Authentication-related security operations.
- Integration with other TenantSphere microservices.

## Technology Stack

| Technology | Purpose |
|---|---|
| Java 21 | Primary programming language |
| Spring Boot | Application framework |
| Spring Security | Authentication and security |
| Spring Data JPA | Database interaction |
| PostgreSQL | Authentication data storage |
| JWT | Token-based authentication |
| Maven | Dependency management |
| Docker | Containerization |

## Architecture Overview

The Auth Service acts as the centralized authentication component of TenantSphere.

It is responsible for verifying user identities and issuing authentication tokens that are used to access protected resources across the platform.

### Authentication Flow

1. A user submits login credentials.
2. Auth Service validates the credentials.
3. Upon successful authentication, an access token and refresh token are generated.
4. The client uses the access token to access protected APIs.
5. Other microservices validate the access token.
6. When the access token expires, the client can request a new token using the refresh token.
7. Refresh token rotation helps maintain secure sessions.

## Database

**Database:** PostgreSQL

The Auth Service maintains its own database to ensure independent data ownership.

Primary data entities:
- User Credentials
- Refresh Tokens
- Authentication Sessions
- Password Reset Tokens
- Account Verification Tokens

## Microservice Responsibilities

| Service | Responsibility |
|---|---|
| Auth Service | Authentication, credentials, tokens, and sessions |
| Tenant Service | Tenant registration, configuration, and subscription management |
| User Service | User profiles, roles, and permissions |

## Security Considerations

- Passwords are stored using secure hashing algorithms.
- JWT tokens are signed and validated.
- Refresh tokens are securely stored and rotated.
- Sensitive credentials are never exposed in API responses.
- Authentication endpoints are protected against unauthorized access.
- Token expiration and revocation are properly managed.

## Project Status

🚧 **Under Development**

The Auth Service is part of the TenantSphere microservices ecosystem and is being developed incrementally with a focus on security, scalability, maintainability, and production-ready architecture.

---

**Project:** TenantSphere  
**Service:** Auth Service  
**Java Version:** 21  
**Database:** PostgreSQL
