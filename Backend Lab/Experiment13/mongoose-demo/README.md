# Experiment 13 – MongoDB Connectivity with Mongoose

## Aim
To connect a Node.js/Express application to MongoDB using Mongoose and understand database-backed application development.

## Technologies

- Node.js
- Express.js
- MongoDB
- Mongoose
- dotenv

## Project Structure

```text
mongoose-demo/
├── server.js
├── package.json
├── package-lock.json
└── .gitignore
```

## Program Description

The application uses Mongoose to connect the Express server to MongoDB.

The program demonstrates the basic structure required for a MongoDB-backed Node.js application:

```text
Express Server
      ↓
Mongoose
      ↓
MongoDB
```

## Configuration

The MongoDB connection string should be stored in an environment variable.

Create:

```text
.env
```

with:

```env
MONGO_URI=your_mongodb_connection_string
```

Do not upload database passwords or private connection strings to GitHub.

## Installation

```bash
npm install
```

## Run

```bash
node server.js
```

The application is intended to run locally on:

```text
http://localhost:3000
```

## MongoDB / Compass

If MongoDB is running locally, a connection string can typically use the local MongoDB server.

If MongoDB Atlas is used, copy the application connection string from the Atlas dashboard and place it in `MONGO_URI`.

MongoDB Compass can be used separately to inspect the database and collections created by the application.

## Important Note

The README documents the MongoDB/Mongoose experiment as it exists in the supplied project. The repository currently contains the main `server.js` application file but does not contain a separate frontend folder.

## Useful Links

- [MongoDB Documentation](https://www.mongodb.com/docs/)
- [MongoDB Manual](https://www.mongodb.com/docs/manual/)
- [MongoDB Compass](https://www.mongodb.com/products/tools/compass)
- [Mongoose Documentation](https://mongoosejs.com/docs/)
- [Mongoose Getting Started](https://mongoosejs.com/docs/index.html)
- [dotenv](https://www.npmjs.com/package/dotenv)
- [Express.js](https://expressjs.com/)

## Learning Outcome

This experiment introduces the connection between an Express backend and a MongoDB database through Mongoose and demonstrates why environment variables are used for database connection configuration.
