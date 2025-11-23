# Project Management API

RESTful API for collaborative project management with task organization and role-based access control.

## Features

- User authentication with JWT
- Project and task management
- Hierarchical subtasks
- File attachments
- Role-based permissions
- Project documentation

## Tech Stack

- Node.js + Express.js
- JWT Authentication
- Multer

## Installation

```bash
npm install
cp .env.example .env
npm start
```

## API Endpoints

### Authentication

```
POST   /api/v1/auth/register
POST   /api/v1/auth/login
POST   /api/v1/auth/refresh-token
GET    /api/v1/auth/verify-email/:token
```

### Projects

```
GET    /api/v1/projects
POST   /api/v1/projects
GET    /api/v1/projects/:projectId
PUT    /api/v1/projects/:projectId
DELETE /api/v1/projects/:projectId
```

### Tasks

```
GET    /api/v1/tasks/:projectId
POST   /api/v1/tasks/:projectId
GET    /api/v1/tasks/:projectId/t/:taskId
PUT    /api/v1/tasks/:projectId/t/:taskId
```

### Notes

```
GET    /api/v1/notes/:projectId
POST   /api/v1/notes/:projectId
GET    /api/v1/notes/:projectId/n/:noteId
```

## User Roles

- **Admin** - Full access
- **Project Admin** - Manage tasks
- **Member** - View and update subtasks

## License

MIT
