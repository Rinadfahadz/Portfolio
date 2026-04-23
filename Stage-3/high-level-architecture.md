flowchart LR

  subgraph Client Layer
    A[Frontend (React)]
  end

  subgraph Server Layer
    B[Backend (Node.js + Express)]
  end

  subgraph Data Layer
    C[(MySQL Database)]
    D[(Firebase Authentication)]
  end

  subgraph External Services
    E[Firebase Services]
  end

  A <-->|HTTP Requests / JSON| B
  B -->|CRUD Operations| C
  B -->|Authentication| D
  D --> E
