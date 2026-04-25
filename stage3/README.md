# Hackathon Team Formation Platform
## Stage 3: Technical Documentation

> **Project Team:** Rinad (PM\Backend), Afnan (Frontend), Sarah (Docs)
> **Status:** Stage 3 Complete (Technical Design)

---

<details>
<summary><b> 1. User Stories & MoSCoW Prioritization</b></summary>

### **Must Have (MVP)**
* **Profile Management:** Users can list skills and roles.
* **Team Creation:** Leads can post missing roles.
* **Request System:** Users can apply to join teams.
* **Idea Protection:** Basic timestamping for chat messages.

### **Should Have**
* **Matching:** Filtered list of teams based on user skills.
* **Notifications:** Alerts for accepted/rejected requests.
</details>
  
<details>
<summary><b> 2. System Architecture & Tech Stack</b></summary>

* **Frontend:** React.js (Component-based UI)
* **Backend:** Node.js + Express (REST API)
* **Database:** mySQL (Relational data)
* **Auth:** Firebase (Secure Login)

**High-Level Flow:**
`User Interface (React) <--> API Gateway (Express) <--> Database (PostgreSQL)`
</details>

<details>
<summary><b> 3. Database Schema</b></summary>

| Table | Key Fields |
| :--- | :--- |
| **Users** | `id`, `username`, `skills[]`, `primary_role` |
| **Teams** | `id`, `name`, `lead_id`, `description` |
| **Requests** | `id`, `user_id`, `team_id`, `status` |
| **IdeaLogs** | `id`, `team_id`, `message`, `timestamp` |
</details>

<details>
<summary><b>🔌 4. Core API Endpoints</b></summary>

| Method | Endpoint | Action |
| :--- | :--- | :--- |
| `POST` | `/api/auth/register` | User Signup |
| `GET` | `/api/teams` | Browse Teams |
| `POST` | `/api/requests` | Apply to Team |
| `GET` | `/api/chat/:id` | View Idea Logs |
</details>

<details>
<summary><b> 5. SCM & QA Strategy</b></summary>

* **Branching Strategy:**
* `main` (Stable production-ready code only)
* `develop` (Integration and testing branch)
* `feature/` (Separate branch for each feature such as authentication, team creation, join requests)
* Optional `hotfix/` branches for urgent production bug fixes

* **Commit Strategy:**
* Small and frequent commits
* Clear and descriptive commit messages (e.g. `feat: add team creation API`)
* No direct commits to `main`
* All changes go through feature branches first

* **Code Review Process:**
* All changes must be submitted via Pull Requests (PRs)
* At least one reviewer approval required before merging
* Review checks include code quality, logic correctness, and security
* Prevent merging untested or incomplete code

* **Testing Strategy:**
* **Unit Testing (Jest)** for backend functions such as authentication and team logic
* **Integration Testing** to ensure proper communication between API, database, and frontend
* **Manual Testing** for critical flows like login, team creation, and join requests
* **API Testing (Postman)** to validate endpoints and responses

* **Quality Assurance Practices:**
* Validate all inputs (email, password, join requests)
* Ensure secure authentication using JWT tokens
* Standardize API response structure across all endpoints
* Handle errors properly with meaningful messages

* **Deployment Strategy:**
* Development happens in feature branches
* Merged into `develop` after testing and review
* Stable and tested code is merged into `main`
* Production deployment only from `main`

* **Testing Environments:**
* **Development Environment** for active coding and initial testing
* **Staging Environment** for final QA validation before release
* **Production Environment** for live users and final system deployment
</details>

<details>
<summary><b> 6. Technical Justifications</b></summary>

* **MySQL:** Chosen for its strong support of relational data, which fits the system structure where Users, Teams, and Hackathon entities are highly interconnected. It ensures data consistency through foreign keys and supports complex queries for team management and participation tracking.

* **Authentication Approach:** Email and password-based authentication with JWT is used instead of third-party services to ensure full control over user data, security, and system logic within the backend.

* **Idea Protection:** The `IdeaLogs` table uses server-side timestamps to record the exact time of idea submission, ensuring proof of originality and preventing disputes during hackathon idea submission phases.

* **Scalability:** The system is designed with a modular backend structure (Node.js APIs), allowing easy scaling and future feature expansion such as chat systems or advanced team matching.

* **Real-time Updates:** WebSocket / Socket.IO is used instead of external services to provide instant updates for join requests and team notifications, ensuring low latency communication between users.

* **Separation of Concerns:** Frontend (React), Backend (Node.js), and Database (MySQL) are fully separated to improve maintainability, testing, and future system upgrades.

* **Security Considerations:** All protected routes are secured using JWT verification, and sensitive operations (like joining teams or creating teams) require authenticated access to prevent unauthorized actions.
</details>

---
