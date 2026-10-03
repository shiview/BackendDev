# Experiment 12B – Sessions and Cookies

## Objective
To understand session management and cookies in an Express.js application.

## Technologies
- Node.js
- Express.js
- express-session
- cookie-parser

## Features
- Login form
- Express session
- Cookie creation
- Session-based welcome message
- Logout
- Session destruction
- Cookie clearing
- Cookie expiration

## Routes

| Method | Route | Purpose |
|---|---|---|
| GET | `/` | Login or welcome page |
| POST | `/login` | Start session and set cookie |
| GET | `/logout` | Destroy session |

## How to Run

```bash
npm install
node session-cookie-demo/server.js
```

Open:

```text
http://localhost:3000
```
