# ZW Auth API

A secure authentication REST API built with Node.js, Express, Prisma, bcrypt, and JWT.

## Features

- User registration
- Secure password hashing with bcrypt
- User login
- JWT authentication
- Protected user profile endpoint
- Logout
- Authentication middleware
- Prisma ORM
- Environment variables
- Git/GitHub version control

## Tech Stack

- Node.js
- Express.js
- Prisma
- SQLite
- bcrypt
- JSON Web Token (JWT)
- dotenv

## API Endpoints

### Register

POST `/api/auth/register`

Creates a new user.

### Login

POST `/api/auth/login`

Authenticates a user and returns a JWT token.

### Logout

POST `/api/auth/logout`

Logs the user out on the frontend by removing the stored JWT token.

### Current User

GET `/api/auth/me`

Returns the currently authenticated user.

Requires:

`Authorization: Bearer YOUR_JWT_TOKEN`

## Authentication Flow

Register
↓
Password hashed with bcrypt
↓
User saved to database
↓
Login
↓
JWT token generated
↓
Token stored in frontend
↓
Protected `/me` request
↓
JWT middleware verifies token
↓
Authenticated user returned

## Environment Variables

Create a `.env` file containing:

DATABASE_URL="file:./dev.db"

JWT_SECRET="your-secret-key"

PORT=5000

Never commit `.env` to GitHub.

## Running the API

Install dependencies:

npm install

Generate Prisma Client:

npx prisma generate

Start the server:

npm run dev

The API runs on:

http://localhost:5000

## Project Structure

zw-auth-api/
├── controllers/
│   └── authController.js
├── middleware/
│   └── authMiddleware.js
├── routes/
│   └── auth.js
├── prisma/
├── .env
├── .gitignore
├── package.json
└── server.js

## Security

- Passwords are hashed with bcrypt.
- Passwords are never stored as plain text.
- JWT tokens are used for authentication.
- Protected routes require a valid Bearer token.
- Environment secrets are excluded from Git.
- The local database is excluded from Git.

## Project Status

Completed authentication API for the ZW BIZZ TOOLS full-stack roadmap.

Next project: CRUD + Pagination API
