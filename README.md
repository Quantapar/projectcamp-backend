# Project Camp Backend

A RESTful API service for collaborative project management, enabling teams to organize projects, manage tasks with subtasks, and maintain project notes with role-based access control.

## Features

- **User Authentication** - Secure JWT-based authentication with email verification
- **Project Management** - Create and manage projects with team collaboration
- **Task Management** - Hierarchical task organization with subtasks and file attachments
- **Role-Based Access** - Three-tier permission system (Admin, Project Admin, Member)
- **Project Notes** - Documentation capabilities for projects

## Tech Stack

- Node.js + Express.js
- JWT Authentication
- Multer (File uploads)

## Getting Started

### Installation

```bash
# Clone the repository
git clone <repository-url>

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env

# Start the server
npm start
```

## API Overview

### Base URL

```
/api/v1
```

### Authentication

Complete authentication system including registration, login, email verification, and password reset.

```
POST   /auth/register
POST   /auth/login
POST   /auth/refresh-token
GET    /auth/verify-email/:token
```

### Projects

Manage projects, team members, and project settings.

```
GET    /projects
POST   /projects
GET    /projects/:projectId
PUT    /projects/:projectId (Admin only)
DELETE /projects/:projectId (Admin only)
```

### Tasks & Subtasks

Create and manage tasks with hierarchical subtask support.

```
GET    /tasks/:projectId
POST   /tasks/:projectId (Admin/Project Admin)
GET    /tasks/:projectId/t/:taskId
PUT    /tasks/:projectId/t/:taskId (Admin/Project Admin)
```

### Notes

Project documentation and notes system.

```
GET    /notes/:projectId
POST   /notes/:projectId (Admin only)
GET    /notes/:projectId/n/:noteId
```

### Health Check

```
GET    /healthcheck
```

For complete API documentation, see [API_DOCS.md](./API_DOCS.md)

## User Roles

| Role              | Permissions                                              |
| ----------------- | -------------------------------------------------------- |
| **Admin**         | Full access - manage projects, members, tasks, and notes |
| **Project Admin** | Manage tasks and subtasks within assigned projects       |
| **Member**        | View projects and update subtask status                  |

## Security

- JWT-based authentication with refresh tokens
- Role-based authorization
- Email verification
- Secure password reset
- Input validation and CORS configuration

## License

MIT
