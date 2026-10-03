# Experiment 12 – Node.js, Express.js and EJS

## Objective
To develop an Express.js server and understand HTTP responses, routing, route parameters, query parameters, POST requests, and EJS server-side rendering.

## Technologies
- Node.js
- Express.js
- EJS
- Nodemon

## Features
- Plain text response
- HTML response
- JSON response
- URL parameters
- Query parameters
- Calculator using query parameters
- POST registration
- Login validation
- EJS rendering
- User list
- Dynamic user profile

## Routes

| Method | Route | Purpose |
|---|---|---|
| GET | `/` | Welcome message |
| GET | `/text` | Plain text response |
| GET | `/html` | HTML response |
| GET | `/json` | JSON response |
| GET | `/user/:id` | Route parameter |
| GET | `/search` | Query parameters |
| GET | `/calculate` | Arithmetic operation |
| POST | `/register` | Register user |
| POST | `/login` | Login validation |
| GET | `/home` | EJS home page |
| GET | `/users` | User list |
| GET | `/profile/:id` | Dynamic profile |

## How to Run

```bash
npm install
npm start
```

For development:

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```
