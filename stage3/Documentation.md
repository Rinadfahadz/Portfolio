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

### User APIs
| End Point | Method | Input | Output |
|-----------|--------|-------|--------|
| /api/users | GET | - | [ { user data } ] |
| /api/users/:id | GET | userId (param) | { user details } |
| /api/users/:id | PUT | { updated fields } | { success message } |

### Team APIs
| End Point | Method | Input | Output |
|-----------|--------|-------|--------|
| /api/teams | Get | - | [ { teams list } ] |
| /api/teams | POST | { name, description, required_roles } | { team created } |
| /api/teams/:id | GET | teamId | { team details } |

### Join Request APIs
| End Point | Method | Input | Output |
|-----------|--------|-------|--------|
| /api/requests | POST | { userId, teamId } | { request status } |
| /api/requests/:id | PUT | { status: accepted/rejected } | { updated request } |
| /api/requests/team/:teamId | GET | teamId | [ requests list ] |

### Idea Protection APIs
| End Point | Method | Input | Output |
|-----------|--------|-------|--------|
| /api/ideas | POST | { teamId, userId, message } | { saved message with timestamp } |
| /api/ideas/:teamId | GET | teamId | [ idea logs ] |
