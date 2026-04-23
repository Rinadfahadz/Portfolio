> .:
# Class Diagram

(Users, Teams, Chat, Hackathon)
---
config:
  theme: dark
---
classDiagram

class User {
  userId
  name
  email
  password
  role
  profileImage

  +register()
  +login()
  +updateProfile()
  +sendMessage()
  +viewTeams()
}

class Participant {
  skills
  portfolioLink
  experience

  +requestToJoinTeam()
  +viewJoinRequestsStatus()
}

class TeamLeader {
  +createTeam()
  +updateTeam()
  +deleteTeam()
  +acceptRequest()
  +rejectRequest()
}

class Organizer {
  +createHackathon()
  +updateHackathon()
  +deleteHackathon()
  +viewTeams()
}

class Admin {
  +manageUsers()
  +deleteUser()
  +manageHackathons()
}

User <|-- Participant
User <|-- TeamLeader
User <|-- Organizer
User <|-- Admin

class Team {
  teamId
  name
  projectIdea
  requiredRoles
  maxMembers
  status

  +addMember()
  +removeMember()
  +updateProjectIdea()
  +changeStatus()
}

class JoinRequest {
  requestId
  status
  createdAt

  +createRequest()
  +cancelRequest()
  +updateStatus()
}

class Hackathon {
  hackathonId
  title
  description
  startDate
  endDate
  location

  +addTeam()
  +removeTeam()
  +updateDetails()
}

class Chat {
  chatId
  createdAt

  +createChat()
  +addParticipant()
  +removeParticipant()
}

class Message {
  messageId
  content
  timestamp

  +send()
  +edit()
  +delete()
}

User --> Team
User --> JoinRequest
User --> Message

Team --> User
Team --> JoinRequest
Team --> Hackathon
Team --> Chat

JoinRequest --> User
JoinRequest --> Team

Hackathon --> Team
Hackathon --> Organizer

Chat --> Message
Chat --> User
Chat --> Team

Message --> User
Message --> Chat
