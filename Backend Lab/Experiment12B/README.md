# Experiment 12B – Sessions and Cookies

## Aim
To understand session management and browser cookies in an Express.js application.

## Technologies

- Node.js
- Express.js
- express-session
- cookie-parser

## Project Structure

```text
Experiment12B/
├── package.json
├── package-lock.json
├── session-cookie-demo/
│   └── server.js
└── source/
    ├── session-example.js
    └── cookie-example.js
```

## Program Description

The main demonstration is located in:

```text
session-cookie-demo/server.js
```

It uses both Express sessions and cookies.

## Session Demonstration

### Start Session

```text
GET /login
```

The server stores:

```text
username = JohnDoe
```

in the session.

Open:

```text
http://localhost:3000/login
```

### Read Session

```text
GET /profile
```

If a session exists, the application displays a welcome message.

```text
http://localhost:3000/profile
```

### Destroy Session

```text
GET /logout
```

The session is destroyed.

```text
http://localhost:3000/logout
```

## Cookie Demonstration

### Set Cookie

```text
GET /setcookie
```

Creates a cookie named:

```text
username
```

with the value:

```text
JohnDoe
```

### Read Cookie

```text
GET /getcookie
```

Reads the cookie using `req.cookies`.

### Delete Cookie

```text
GET /deletecookie
```

Removes the `username` cookie.

## Query String Demonstration

The program also contains:

```text
GET /welcome
```

It reads:

```text
user
role
```

from the query string.

Example:

```text
http://localhost:3000/welcome?user=Shiv&role=student
```

## Session Configuration

The session uses a one-minute cookie lifetime:

```text
maxAge: 60000
```

The cookie example uses a one-hour lifetime:

```text
maxAge: 3600000
```

## Installation

```bash
npm install
```

## Run

```bash
node session-cookie-demo/server.js
```

Open:

```text
http://localhost:3000
```

## Useful Links

```text
http://localhost:3000/login
http://localhost:3000/profile
http://localhost:3000/logout
http://localhost:3000/setcookie
http://localhost:3000/getcookie
http://localhost:3000/deletecookie
http://localhost:3000/welcome?user=Shiv&role=student
```

## Official Documentation

- [Express.js](https://expressjs.com/)
- [express-session](https://www.npmjs.com/package/express-session)
- [cookie-parser](https://www.npmjs.com/package/cookie-parser)
- [MDN Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookies)

## Learning Outcome

The experiment demonstrates the difference between server-side session state and client-side cookies and shows how Express middleware can manage both.
