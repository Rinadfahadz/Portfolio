flowchart LR
    subgraph Client["Client Layer"]
        FE["Frontend<br/>React"]
    end

    subgraph Server["Server Layer"]
        BE["Backend<br/>Node.js + Express"]
    end

    subgraph Data["Data Layer"]
        DB[(MySQL<br/>Main Database)]
        DB2[(Firebase Firestore<br/>Realtime Logs)]
    end

    subgraph External["External Services"]
        AUTH["Firebase Auth"]
    end

    %% Client ↔ Backend
    FE <-->|"HTTP Requests / JSON"| BE

    %% Backend ↔ MySQL
    BE <-->|"Users / Teams / Requests CRUD"| DB

    %% Backend ↔ Firestore
    BE <-->|"Idea Logs / Realtime Updates"| DB2

    %% Client ↔ Firebase Auth
    FE -->|"Login / Register"| AUTH
    AUTH -->|"JWT Token"| FE

    %% Backend ↔ Auth Verification
    BE -->|"Verify Token"| AUTH

    %% Client ↔ Firestore (Realtime)
    FE <-->|"Realtime Sync / Notifications"| DB2
