## External APIs
### No External APIs Used
The system does not rely on any external third-party APIs. All core functionalities are developed internally to maintain full control over data, security, and system behavior.
### Reasons for this decision:
- Reduces system dependencies
- Improves security and data privacy
- Simplifies MVP development
- Ensures full control over authentication and business logic

## Internal APIs
The system uses RESTful APIs built with Node.js and Express. All data is exchanged in JSON format.
### Authentication APIs
| End Point | Method | Input | Output |
|-----------|--------|-------|--------|
| /api/auth/register | POST | { username, email, password } | { message, userId } |
| /api/auth/login | POST | { email, password } | { token, user } |
