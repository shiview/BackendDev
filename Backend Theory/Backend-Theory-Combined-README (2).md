# Backend Theory – Experiments and Assignments

This folder contains the theory/practical tasks for Backend Development, covering backend environment setup, HTTP requests, REST APIs, FastAPI, sessions, cookies, Web Storage, server-side rendering, EJS, Jinja2, and a browser-based Notes application.

---

# Contents

1. [L03 – Setting Up the Backend Environment](#l03--setting-up-the-backend-environment)
2. [L04 – HTTP Requests, DevTools, cURL, Postman and Fetch](#l04--http-requests-devtools-curl-postman-and-fetch)
3. [L05 – RESTful APIs and FastAPI](#l05--restful-apis-and-fastapi)
4. [L06 – Server-side Sessions, Cookies and State Management](#l06--server-side-sessions-cookies-and-state-management)
5. [L07 – Web Storage APIs and DevTools](#l07--web-storage-apis-and-devtools)
6. [L08 – Server-Side Rendering and Templating Engines](#l08--server-side-rendering-and-templating-engines)
7. [Assignment 1 – Notes App](#assignment-1--notes-app)
8. [Technologies](#technologies)
9. [Learning Outcomes](#learning-outcomes)

---

# L03 – Setting Up the Backend Environment

## Aim

To set up a basic backend development environment and progressively build applications using Node.js, Express.js, EJS and Flask.

## Technologies

- Node.js
- npm
- Express.js
- EJS
- Python
- Flask

---

## Task 1 – Basic Express Server

**Location:**

```text
L03 Setting Up the Backend Environment/Task1/
```

**Main file:**

```text
server.js
```

Creates a basic Express server with:

```text
GET /
```

Response:

```text
Backend Server Running
```

### Run

```bash
npm install
node server.js
```

### URL

```text
http://localhost:3000/
```

---

## Task 2 – Basic Student Routes

**Main file:**

```text
Task2/server.js
```

Routes:

```text
GET /
GET /students
GET /students/1
```

The program demonstrates simple Express routing using student-related responses.

### Run

```bash
npm install
node server.js
```

### URLs

```text
http://localhost:3000/
http://localhost:3000/students
http://localhost:3000/students/1
```

---

## Task 3 – JSON Student API

**Main file:**

```text
Task3/server.js
```

Routes:

```text
GET /
GET /students
GET /students/:id
```

The program stores students in memory and returns JSON responses.

A student that does not exist produces an HTTP `404` response.

### Example

```text
http://localhost:3000/students/2
```

### Run

```bash
npm install
node server.js
```

---

## Task 4 – HTML Student Management API

**Main file:**

```text
Task4/server.js
```

Routes:

```text
GET /
GET /students
GET /students/:id
```

The program demonstrates:

- Express routes
- Dynamic route parameters
- Dynamic HTML generation
- `404` response handling

### Run

```bash
npm install
node server.js
```

---

## Task 5 – Express + EJS

**Main file:**

```text
Task5/server.js
```

Structure:

```text
Task5/
├── server.js
└── views/
    ├── home.ejs
    └── students.ejs
```

Routes:

```text
GET /
GET /students
```

The application passes student data from Express to EJS templates.

### Run

```bash
npm install
node server.js
```

### URLs

```text
http://localhost:3000/
http://localhost:3000/students
```

---

## Task 6 – Basic Flask Server

**Main file:**

```text
Task6/app.py
```

Creates a Flask application with:

```text
GET /
```

### Run

```bash
python app.py
```

Typical Flask address:

```text
http://127.0.0.1:5000/
```

---

## Task 7 – Flask Student API

**Main file:**

```text
Task7/app.py
```

Routes:

```text
GET /
GET /students
GET /students/<student_id>
```

Returns student information as JSON and produces `404` for an invalid student ID.

### Run

```bash
python app.py
```

---

## Task 8 – Express Student API

**Main file:**

```text
Task8/server.js
```

Routes:

```text
GET /
GET /students
```

Returns an in-memory student list as JSON.

### Run

```bash
npm install
node server.js
```

### URLs

```text
http://localhost:3000/
http://localhost:3000/students
```

---

# L04 – HTTP Requests, DevTools, cURL, Postman and Fetch

## Aim

To understand HTTP requests and responses and practice accessing backend APIs using browser Developer Tools, cURL, Postman and JavaScript Fetch.

## Technologies

- Node.js
- Express.js
- Python
- Flask
- HTTP
- JSON
- Postman
- cURL
- Fetch API
- Browser Developer Tools

---

## Task 1 – Basic Student API

**File:**

```text
Task1/server.js
```

Routes:

```text
GET /
GET /students
```

The root route returns an HTML welcome message, while `/students` returns student data as JSON.

### Run

```bash
npm install
node server.js
```

### URLs

```text
http://localhost:3000/
http://localhost:3000/students
```

---

## Task 2 – Student API with ID

**File:**

```text
Task2/server.js
```

Routes:

```text
GET /students
GET /students/:id
```

The application searches the student array using the supplied ID.

Example:

```text
http://localhost:3000/students/2
```

An invalid ID returns HTTP `404`.

---

## Task 3 – Dynamic Student Route

**File:**

```text
Task3/server.js
```

Routes:

```text
GET /students
GET /students/:id
```

Demonstrates:

- Dynamic route parameters
- JSON responses
- Student lookup
- `404` handling

Example:

```text
http://localhost:3000/students/1
```

---

## Task 4 – Student Management API

**File:**

```text
Task4/server.js
```

Routes:

```text
GET /
GET /students
GET /students/2
```

The application uses Express JSON middleware and returns student information.

### Run

```bash
npm install
node server.js
```

---

## Task 5 – Flask Student API

**File:**

```text
Task5/app.py
```

Route:

```text
GET /students
```

Returns the student list as JSON.

### Run

```bash
pip install flask
python app.py
```

### URL

```text
http://127.0.0.1:5000/students
```

---

## Testing with cURL

Example:

```bash
curl http://localhost:3000/students
```

Specific student:

```bash
curl http://localhost:3000/students/2
```

---

## Testing with Postman

Create a new GET request and enter:

```text
http://localhost:3000/students
```

or:

```text
http://localhost:3000/students/2
```

Click **Send** to inspect the response.

---

## Browser Developer Tools

Open:

```text
F12 → Network
```

Then access an API endpoint.

You can inspect:

- Request URL
- HTTP method
- Status code
- Request headers
- Response headers
- Response body
- Request timing

---

## Fetch API

A backend API can be accessed using JavaScript:

```javascript
fetch("http://localhost:3000/students")
    .then(response => response.json())
    .then(data => console.log(data));
```

---

# L05 – RESTful APIs and FastAPI

## Aim

To build a REST-style Student Management API using FastAPI.

## Technologies

- Python
- FastAPI
- Pydantic
- Uvicorn

## Main File

```text
L05 RESTful APIs and FastAPI/Task1/main.py
```

## Program Description

The application uses Pydantic models for student data.

A student contains:

```text
id
name
branch
```

The initial in-memory data contains:

```text
1 – Aarav – CSE
2 – Diya – ECE
3 – Rohan – IT
```

The data is stored in memory and is not persisted to a database.

---

## API Endpoints

### Get All Students

```text
GET /students
```

Example:

```text
http://127.0.0.1:5000/students
```

### Filter by Branch

```text
GET /students?branch=CSE
```

### Get One Student

```text
GET /students/{student_id}
```

Example:

```text
http://127.0.0.1:5000/students/2
```

An invalid ID returns HTTP `404`.

### Create Student

```text
POST /students
```

Example JSON:

```json
{
  "name": "Karan",
  "branch": "CSE"
}
```

The application assigns the next available ID.

### Update Student

```text
PUT /students/{student_id}
```

Example JSON:

```json
{
  "name": "Karan Sharma",
  "branch": "IT"
}
```

### Delete Student

```text
DELETE /students/{student_id}
```

A successful deletion returns HTTP `204`.

---

## Run

Install dependencies:

```bash
pip install fastapi uvicorn pydantic
```

Run:

```bash
python main.py
```

The application uses:

```text
127.0.0.1:5000
```

---

## Interactive Documentation

FastAPI automatically provides:

```text
http://127.0.0.1:5000/docs
```

and:

```text
http://127.0.0.1:5000/redoc
```

These pages can be used to test the API.

---

## Important Note

The application uses an in-memory Python list. Data is therefore lost when the server is restarted.

---

# L06 – Server-side Sessions, Cookies and State Management

## Aim

To understand sessions, cookies and query strings and how they maintain or transfer state between HTTP requests.

## Technologies

- Node.js
- Express.js
- express-session
- cookie-parser

## Main File

```text
L06 Managing Server-side Session, Cookie, and State Management/Task1/app.js
```

---

## Session Routes

### Login

```text
GET /login
```

Stores:

```text
username = JohnDoe
```

in the Express session.

URL:

```text
http://localhost:3000/login
```

### Profile

```text
GET /profile
```

Reads the session and displays the logged-in username.

URL:

```text
http://localhost:3000/profile
```

### Logout

```text
GET /logout
```

Destroys the session.

URL:

```text
http://localhost:3000/logout
```

---

## Cookie Routes

### Set Cookie

```text
GET /setcookie
```

Creates:

```text
username=JohnDoe
```

### Get Cookie

```text
GET /getcookie
```

Reads the `username` cookie.

### Delete Cookie

```text
GET /deletecookie
```

Removes the cookie.

---

## Query String

Route:

```text
GET /welcome
```

Example:

```text
http://localhost:3000/welcome?user=Shiv&role=student
```

The program reads:

```javascript
req.query.user
req.query.role
```

---

## Run

```bash
npm install
node app.js
```

Server:

```text
http://localhost:3000
```

## Session Configuration

The session cookie is configured with:

```text
maxAge = 60000
```

which is approximately one minute.

---

# L07 – Web Storage APIs and DevTools

## Aim

To understand browser-side storage using `localStorage` and `sessionStorage`, JSON serialization and browser Developer Tools.

## Technologies

- HTML
- JavaScript
- Web Storage API
- Browser Developer Tools

---

## Task 1 – localStorage

**File:**

```text
Task1/index.html
```

Stores:

```text
favColor = blue
```

using:

```javascript
localStorage.setItem("favColor", "blue");
```

The stored value is then read and displayed in the console.

---

## Task 2 – sessionStorage

**File:**

```text
Task2/index.html
```

Demonstrates the `sessionStorage` API.

The supplied program contains:

```javascript
sessionStorage.setItem("tempData");
```

`setItem()` normally takes both a key and a value. The code currently provides only the key, so this README documents the program exactly as supplied.

---

## Task 3 – JSON with localStorage

**File:**

```text
Task3/index.html
```

Creates a JavaScript object:

```json
{
  "name": "Alice",
  "age": 25
}
```

and converts it to JSON using:

```javascript
JSON.stringify(user)
```

The JSON string is stored in `localStorage`.

---

## Task 4 – JSON.stringify and JSON.parse

**File:**

```text
Task4/index.html
```

Demonstrates:

```text
JavaScript Object
       ↓
JSON.stringify()
       ↓
JSON String
       ↓
JSON.parse()
       ↓
JavaScript Object
```

The program accesses object properties such as:

```text
name
age
skills
```

---

## Task 5 – DevTools Verification

**File:**

```text
Task5/index.html
```

Stores:

```text
name = Ajay
course = Computer Science
city = Delhi
```

These values can be inspected using:

```text
F12 → Application → Local Storage
```

---

## Task 6 – Reusable Storage Functions

**File:**

```text
Task6/index.html
```

Defines:

```javascript
save(key, data)
load(key)
```

The `save()` function converts data to JSON before storing it.

The `load()` function retrieves and parses the stored JSON.

---

## Task 7 – Notes / Todo App

**File:**

```text
Task7/index.html
```

A small client-side notes application using `localStorage`.

Features:

- Add notes
- Display notes
- Edit notes
- Delete notes
- Local storage
- Creation timestamp
- Update timestamp
- Empty-input validation

Each note contains:

```text
id
text
completed
createdAt
updatedAt
```

---

## How to Run

These are client-side applications.

Open:

```text
Task1/index.html
Task2/index.html
...
Task7/index.html
```

in a modern browser.

Use Developer Tools to inspect console output and browser storage.

---

# L08 – Server-Side Rendering and Templating Engines

## Aim

To understand server-side rendering using EJS with Express and Jinja2 with FastAPI.

## Technologies

- Node.js
- Express.js
- EJS
- Python
- FastAPI
- Jinja2
- CSS
- Static files

---

## Task 1 – EJS Student List

Structure:

```text
TASK1/
├── app.js
├── package.json
└── views/
    └── students.ejs
```

The application stores four students:

```text
Aarav – CSE
Diya – ECE
Rohan – IT
Karan – CSE
```

Route:

```text
GET /
```

The student array is passed to the EJS template.

### Run

```bash
npm install
node app.js
```

### URL

```text
http://localhost:3000/
```

---

## Task 2 – EJS Multiple Pages

Structure:

```text
TASK2/
├── app.js
├── package.json
└── views/
    ├── students.ejs
    └── about.ejs
```

### Routes

```text
GET /
GET /about
```

The `/about` page receives:

```text
Course: Backend Development
Lecturer: Dr. Prateek Raj Gautam
```

### Run

```bash
npm install
node app.js
```

---

## Task 3 – FastAPI + Jinja2

Structure:

```text
TASK3/
├── main.py
└── templates/
    └── home.html
```

The FastAPI application uses Jinja2 templates and passes the current date/time to the HTML template.

### Install

```bash
pip install fastapi uvicorn jinja2
```

### Run

```bash
uvicorn main:app --reload
```

### URL

```text
http://127.0.0.1:8000/
```

---

## Task 4 – EJS + Static CSS

Structure:

```text
TASK4/
├── app.js
├── package.json
├── views/
│   ├── students.ejs
│   └── about.ejs
└── Public/
    └── CSS/
        └── style.css
```

Demonstrates:

- EJS rendering
- Dynamic student data
- Multiple pages
- Static CSS
- Express static middleware

Routes:

```text
GET /
GET /about
```

### Run

```bash
npm install
node app.js
```

---

## Task 5 – FastAPI + Jinja2 + Static Files

Structure:

```text
TASK5/
├── main.py
└── templates/
    └── home.html
```

The application:

- Creates a FastAPI server
- Configures Jinja2
- Mounts a static-file path
- Renders an HTML template

### Install

```bash
pip install fastapi uvicorn jinja2
```

### Run

```bash
uvicorn main:app --reload
```

### URL

```text
http://127.0.0.1:8000/
```

---

## Server-Side Rendering Flow

```text
Browser Request
       ↓
Backend Server
       ↓
Template Engine
       ↓
HTML Generated
       ↓
Browser
```

EJS performs server-side rendering in the Express tasks, while Jinja2 performs it in the FastAPI tasks.

---

# Assignment 1 – Notes App

## Aim

To create a browser-based Notes application using HTML, CSS, JavaScript and Local Storage.

## Main File

```text
assignment1/index.html
```

The application is completely client-side and does not require a backend server.

---

## Features

### Add Notes

The user enters text and selects **Add Note**.

The program validates the input and creates a note object.

Each note contains:

```text
id
text
completed
createdAt
updatedAt
```

### Edit Notes

The Edit button allows the note text to be changed.

The `updatedAt` timestamp is updated.

### Delete Notes

The Delete button removes a note after confirmation.

### Persistent Storage

Notes are stored using:

```javascript
localStorage.setItem(
    "notes",
    JSON.stringify(notes)
);
```

When the page loads, the stored JSON is parsed back into JavaScript objects.

### Empty State

When there are no saved notes:

```text
No notes available.
```

is displayed.

---

## Data Flow

```text
User enters note
       ↓
handleAddNote()
       ↓
getNotes()
       ↓
Create note object
       ↓
saveNotes()
       ↓
localStorage
       ↓
renderNotes()
```

---

## How to Run

Open:

```text
assignment1/index.html
```

in a modern browser.

To inspect the saved notes:

```text
F12 → Application → Local Storage
```

The storage key is:

```text
notes
```

---

# Technologies

The theory folder covers:

| Technology | Used For |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | Backend server and routing |
| EJS | Server-side rendering |
| Python | Backend programming |
| Flask | Python web/API development |
| FastAPI | REST API development |
| Pydantic | FastAPI data validation |
| Uvicorn | ASGI server |
| Jinja2 | Python server-side templates |
| MongoDB concepts | Database connectivity |
| JavaScript | Client-side functionality |
| Local Storage | Browser persistence |
| Session Storage | Temporary browser storage |
| Cookies | Client-side state |
| Postman | API testing |
| cURL | HTTP/API testing |
| Browser DevTools | Request and storage inspection |

---

# General Setup

## Node.js

Check installation:

```bash
node --version
npm --version
```

Install dependencies inside a Node.js task:

```bash
npm install
```

Run the appropriate application:

```bash
node server.js
```

or:

```bash
node app.js
```

Some projects may provide:

```bash
npm start
```

---

## Python

Check installation:

```bash
python --version
```

Install Flask:

```bash
pip install flask
```

Install FastAPI:

```bash
pip install fastapi uvicorn jinja2
```

Run Flask:

```bash
python app.py
```

Run FastAPI:

```bash
uvicorn main:app --reload
```

---

# Useful Documentation Links

## Node.js

https://nodejs.org/docs/latest/api/

## Express.js

https://expressjs.com/

## EJS

https://ejs.co/

## Flask

https://flask.palletsprojects.com/

## FastAPI

https://fastapi.tiangolo.com/

## Pydantic

https://docs.pydantic.dev/

## Uvicorn

https://www.uvicorn.org/

## Jinja2

https://jinja.palletsprojects.com/

## MDN HTTP

https://developer.mozilla.org/en-US/docs/Web/HTTP

## Fetch API

https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

## Web Storage API

https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API

## Local Storage

https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage

## Session Storage

https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage

## JSON

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON

## Postman

https://learning.postman.com/

## cURL

https://curl.se/docs/

## Chrome DevTools

https://developer.chrome.com/docs/devtools/

---

# Learning Outcomes

After completing these theory experiments and assignment, the following concepts are covered:

1. Backend environment setup
2. Node.js fundamentals
3. Express.js server creation
4. HTTP request and response handling
5. Express routing
6. Route parameters
7. Query parameters
8. JSON API responses
9. REST API concepts
10. Flask API development
11. FastAPI development
12. Pydantic validation
13. GET, POST, PUT and DELETE operations
14. EJS server-side rendering
15. Jinja2 server-side rendering
16. Express sessions
17. HTTP cookies
18. Browser Local Storage
19. Browser Session Storage
20. JSON serialization and parsing
21. API testing with Postman and cURL
22. Browser Developer Tools
23. Client-server communication
24. Client-side CRUD using Local Storage

---

# Folder Structure

```text
Backend Theory/
│
├── L03 Setting Up the Backend Environment/
│   ├── Task1/
│   ├── Task2/
│   ├── Task3/
│   ├── Task4/
│   ├── Task5/
│   ├── Task6/
│   ├── Task7/
│   └── Task8/
│
├── L04 HTTP Requests, DevTools, CURL, Postman, and fetch/
│   ├── Task1/
│   ├── Task2/
│   ├── Task3/
│   ├── Task4/
│   └── Task5/
│
├── L05 RESTful APIs and FastAPI/
│   └── Task1/
│
├── L06 Managing Server-side Session, Cookie, and State Management/
│   └── Task1/
│
├── L07 Web Storage APIs and DevTools/
│   ├── Task1/
│   ├── Task2/
│   ├── Task3/
│   ├── Task4/
│   ├── Task5/
│   ├── Task6/
│   └── Task7/
│
├── L08 Server-Side Rendering and Templating Engines/
│   ├── TASK1/
│   ├── TASK2/
│   ├── TASK3/
│   ├── TASK4/
│   └── TASK5/
│
└── assignment1/
```

---

# Conclusion

The Backend Theory folder provides a progression from basic backend environment setup to API development, state management, browser storage and server-side rendering.

The experiments collectively demonstrate both **JavaScript-based backend development with Node.js/Express** and **Python-based backend development with Flask/FastAPI**, along with the tools commonly used to test and debug web applications.
