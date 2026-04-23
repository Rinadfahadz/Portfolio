# High Level Sequence Diagram

## Use Case: Create Team & Join Hackathon
```mermaid

sequenceDiagram
    participant User as Participant
    participant Frontend as React Frontend
    participant API as Node.js Backend
    participant Auth as Firebase Auth
    participant DB as MySQL

    User->>Frontend: Create Team form
    Frontend->>Auth: Verify token
    Auth-->>Frontend: Token valid

    Frontend->>API: POST /teams
    API->>Auth: Verify token
    Auth-->>API: Authenticated

    API->>DB: Insert new team
    DB-->>API: Team created

    API-->>Frontend: Success response
    Frontend-->>User: Show team created
```

## Use Case: Join Request & Team Leader Respons
```mermaid
sequenceDiagram
    participant User
    participant Frontend
    participant API
    participant DB
    participant Firebase

    User->>Frontend: Send join request
    Frontend->>API: POST /join-request

    API->>DB: Save request
    DB-->>API: Request stored

    API->>Firebase: Notify team leader
    Firebase-->>Frontend: Real-time update

    API-->>Frontend: Request sent successfully
```
