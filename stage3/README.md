# 🚀 Hackathon Team Formation Platform
## Stage 3: Technical Documentation

> **Project Team:** Rinad (PM\Backend), Afnan (Frontend), Sarah (Docs)
> **Status:** Stage 3 Complete (Technical Design)

---

<details>
<summary><b>🎯 1. User Stories & MoSCoW Prioritization</b></summary>

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
<summary><b>🏗️ 2. System Architecture & Tech Stack</b></summary>

* **Frontend:** React.js (Component-based UI)
* **Backend:** Node.js + Express (REST API)
* **Database:** mySQL (Relational data)
* **Auth:** Firebase (Secure Login)

**High-Level Flow:**
`User Interface (React) <--> API Gateway (Express) <--> Database (PostgreSQL)`
</details>

<details>
<summary><b>💾 3. Database Schema</b></summary>

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
<summary><b>🛡️ 5. SCM & QA Strategy</b></summary>

* **Branching:** `main` (Stable), `develop` (Testing), `feature/` (Work).
* **Code Review:** Mandatory PR reviews before merging to develop.
* **Testing:** * **Postman** for API validation.
    * **Manual UI Testing** for team-joining flows.
</details>

<details>
<summary><b>💡 6. Technical Justifications</b></summary>

* **mySQL:** Chosen for its ability to handle relational links between Users and Teams.
* **Idea Protection:** The `IdeaLogs` table uses server-side timestamps to ensure users have proof of original concepts shared during the formation phase.
</details>

---
