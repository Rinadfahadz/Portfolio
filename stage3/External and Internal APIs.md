# Hackathon Teaming Platform – API Design

1) Authentication APIs (Main Auth: Email & Password)

POST /api/v1/auth/register

Input format: JSON
Input: name, email, password, role (participant/team_owner)
Output format: JSON
Output: user created + token (or success message)

⸻

POST /api/v1/auth/login

Input format: JSON
Input: email, password
Output format: JSON
Output: authentication token + user info

⸻

POST /api/v1/auth/logout

Input format: JSON
Input: token
Output format: JSON
Output: logout confirmation

⸻

GET /api/v1/auth/me

Input format: None
Output format: JSON
Output: current user profile info

⸻

2) User Profile APIs

GET /api/v1/users/:user_id

Input format: None
Output format: JSON
Output: user profile details

⸻

PUT /api/v1/users/:user_id

Input format: JSON
Input: name, skills, bio, interests
Output format: JSON
Output: updated profile result

⸻

3) Hackathon APIs

GET /api/v1/hackathons

Input format: None
Output format: JSON
Output: list of available hackathons

⸻

GET /api/v1/hackathons/:hackathon_id

Input format: None
Output format: JSON
Output: hackathon details

⸻

POST /api/v1/hackathons

Input format: JSON
Input: title, description, start_date, end_date, rules
Output format: JSON
Output: hackathon creation result (admin only)

⸻

4) Team APIs

POST /api/v1/teams

Input format: JSON
Input: name, idea, hackathon_id
Output format: JSON
Output: team creation result

⸻

GET /api/v1/teams/:team_id

Input format: None
Output format: JSON
Output: team details + members

⸻

POST /api/v1/teams/:team_id/join

Input format: JSON
Input: user_id (or auto from token)
Output format: JSON
Output: join request result

⸻

POST /api/v1/teams/:team_id/leave

Input format: JSON
Input: user_id
Output format: JSON
Output: leave confirmation

⸻

POST /api/v1/teams/:team_id/invite

Input format: JSON
Input: user_id
Output format: JSON
Output: invitation sent result

⸻

5) Matching / Recommendation APIs

GET /api/v1/matching/teams

Input format: Query (skills, interests)
Output format: JSON
Output: recommended teams list

⸻

GET /api/v1/matching/users

Input format: Query (skills, role, availability)
Output format: JSON
Output: recommended users list

⸻

6) Participation APIs

POST /api/v1/participations/join

Input format: JSON
Input: user_id, hackathon_id
Output format: JSON
Output: participation confirmation

⸻

GET /api/v1/participations/:user_id

Input format: None
Output format: JSON
Output: user hackathon participation history

⸻

7) Messaging APIs (Real-time Chat

POST /api/v1/messages

Input format: JSON
Input: sender_id, receiver_id OR team_id, message
Output format: JSON
Output: message sent confirmation

⸻

GET /api/v1/messages/:conversation_id

Input format: None
Output format: JSON
Output: chat history

⸻

8) Notifications APIs

GET /api/v1/notifications/:user_id

Input format: None
Output format: JSON
Output: list of notifications

⸻

POST /api/v1/notifications/mark-read

Input format: JSON
Input: notification_id
Output format: JSON
Output: status updated

⸻

9) Admin APIs

GET /api/v1/admin/users

Input format: None
Output format: JSON
Output: all users list

⸻

POST /api/v1/admin/hackathons/:hackathon_id/close

Input format: JSON
Input: reason
Output format: JSON
Output: hackathon closed result

⸻

DELETE /api/v1/admin/users/:user_id

Input format: JSON
Input: reason
Output format: JSON
Output: user removed result
