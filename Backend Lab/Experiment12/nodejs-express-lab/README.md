# Experiment 12 – Node.js, Express.js and EJS

## Aim
To develop a backend application using Node.js and Express.js and demonstrate HTTP responses, routing, query parameters, route parameters, POST requests and server-side rendering using EJS.

## Technologies

- Node.js
- Express.js
- EJS
- Nodemon

## Project Files

```text
nodejs-express-lab/
├── app.js
├── script.js
├── nodemon.js
├── package.json
├── package-lock.json
└── views/
    ├── home.ejs
    ├── users.ejs
    └── profile.ejs
```

## Program Description

`app.js` creates an Express server and exposes several examples of backend communication.

### 1. Basic response

```text
GET /
```

Returns a welcome message.

### 2. Plain text response

```text
GET /text
```

Returns a plain text response.

### 3. HTML response

```text
GET /html
```

Returns an HTML response.

### 4. JSON response

```text
GET /json
```

Returns JSON data.

### 5. Route parameters

```text
GET /user/:id
```

Example:

```text
http://localhost:3000/user/5
```

The value `5` is received through `req.params.id`.

### 6. Query parameters

```text
GET /search?q=term
```

Example:

```text
http://localhost:3000/search?q=computer
```

The search value is read from `req.query.q`.

### 7. Calculator

```text
GET /calculate?num1=10&num2=5&operation=add
```

Supported operations in the program include:

```text
add
subtract
multiply
divide
```

The result is returned as JSON.

### 8. Registration

```text
POST /register
```

The server reads:

```text
username
email
password
```

and returns a registration-success response containing the username and email.

### 9. Login

```text
POST /login
```

The demonstration accepts:

```text
Email: test@example.com
Password: password123
```

A successful response contains a sample token. This is only a demonstration and is **not a real JWT authentication system**.

### 10. EJS Home Page

```text
GET /home
```

Renders:

```text
views/home.ejs
```

and passes title, heading and message data to the template.

### 11. User List

```text
GET /users
```

Renders `users.ejs` using an in-memory array containing three sample users.

### 12. Dynamic Profile

```text
GET /profile/:id
```

Example:

```text
http://localhost:3000/profile/2
```

Renders `profile.ejs` using the requested ID.

## Additional Node.js File

`script.js` is a basic Node.js demonstration that:

- Prints a message
- Uses variables
- Uses template literals
- Creates an array
- Calculates the sum using `reduce()`

Run it separately with:

```bash
node script.js
```

## Installation

Open PowerShell or Command Prompt inside this folder:

```bash
npm install
```

## Run

Normal mode:

```bash
npm start
```

Development mode:

```bash
npm run dev
```

The server runs at:

```text
http://localhost:3000
```

## Useful Program Links

```text
http://localhost:3000/
http://localhost:3000/text
http://localhost:3000/html
http://localhost:3000/json
http://localhost:3000/user/1
http://localhost:3000/search?q=computer
http://localhost:3000/calculate?num1=10&num2=5&operation=add
http://localhost:3000/home
http://localhost:3000/users
http://localhost:3000/profile/1
```

`/register` and `/login` are POST routes and should be tested using Postman or another HTTP client.

## Official Documentation

- [Node.js Documentation](https://nodejs.org/docs/latest/api/)
- [Express.js Documentation](https://expressjs.com/)
- [Express Installation Guide](https://expressjs.com/en/starter/installing.html)
- [EJS Documentation](https://ejs.co/)
- [Nodemon](https://nodemon.io/)

## Learning Outcome

This experiment demonstrates how a Node.js application can use Express to create routes and return different types of HTTP responses, while EJS is used to generate HTML dynamically on the server.
