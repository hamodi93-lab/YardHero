# YardHero Web Application

YardHero is a full-stack web application for lawn care, snow removal, and outdoor service requests. The project uses a React frontend, Express backend, and SQLite database initialized from a SQL script.

## Project Structure

```text
YardHeroFull/
‚îú‚îÄ‚îÄ frontend/       React application with React Router
‚îú‚îÄ‚îÄ backend/        Express API server
‚îú‚îÄ‚îÄ database/       SQL schema and seed data
‚îú‚îÄ‚îÄ README.md
‚îú‚îÄ‚îÄ reflection-summary.md
‚îî‚îÄ‚îÄ prompt-log.md
```

## Pages and Routing

The frontend uses React Router and includes multiple pages:

1. `/` - Home/Landing page
2. `/dashboard` - Data dashboard showing saved service requests
3. `/manage` - CRUD page for creating, editing, and deleting service requests
4. `/login` - Demo login page showing edge-case handling for incorrect credentials

## System Architecture

The frontend communicates with the backend using `fetch()` requests to the Express API at `http://localhost:5000/api`. The backend reads and writes data to a SQLite database. Data persists after browser refresh because records are stored in `backend/yardhero.db`, which is initialized using `database/yardhero.sql`.

## Installation Instructions

### 1. Start the backend

```bash
cd backend
npm install
npm start
```

The backend runs at:

```text
http://localhost:5000
```

### 2. Start the frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

The frontend runs at the URL shown in the terminal, usually:

```text
http://localhost:5173
```

## Demo Login

```text
Email: admin@yardhero.com
Password: YardHero123
```

Incorrect login credentials display an error message.

## API Documentation

### GET `/api/requests`
Returns all service requests.

### GET `/api/requests/:id`
Returns one service request by ID.

### POST `/api/requests`
Creates a new service request.

Example body:

```json
{
  "customerName": "John Smith",
  "email": "john@example.com",
  "phone": "216-555-1234",
  "address": "Cleveland, OH",
  "serviceType": "Lawn Care",
  "jobSize": "Medium",
  "notes": "Need mowing this week.",
  "status": "Pending"
}
```

### PUT `/api/requests/:id`
Updates an existing service request.

### DELETE `/api/requests/:id`
Deletes a service request.

### POST `/api/login`
Validates demo admin credentials.

## CRUD Entity

The main CRUD entity is `Service Request`.

Fields:

- id
- customer_name
- email
- phone
- address
- service_type
- job_size
- notes
- status
- created_at

## Video Demonstration Checklist

Record a 3‚Äì5 minute video showing:

1. Home page navigation
2. Dashboard page
3. Manage Requests page
4. Create a new request
5. Refresh the browser and show the request still exists
6. Edit the request status
7. Delete the request
8. Try login with incorrect credentials and show the error
9. Try submitting an empty request and show validation

## Notes

This project is designed for local full-stack demonstration. GitHub Pages can only host static frontend files and does not run the Express backend.

