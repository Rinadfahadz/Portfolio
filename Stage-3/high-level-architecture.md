## High-Level Architecture Diagram

```mermaid
flowchart LR

  subgraph Client_Layer
    A[Frontend (React)]
  end

  subgraph Server_Layer
    B[Backend (Node.js + Express)]
  end

  subgraph Data_Layer
    C[(MySQL Database)]
    D[(Firebase Auth)]
  end

  subgraph External_APIs
    E[Firebase Services]
  end

  A -->|HTTP Requests / JSON| B
  B -->|CRUD Operations| C
  B -->|Authentication| D
  D --> E
