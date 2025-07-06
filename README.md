# Create Express Starter

A modern open-source starter template for building secure, scalable Express.js applications. Use this project to kickstart your backend API with all the essentials built-in.

---

## Features

- **Pre-built starter files**: Immediate project structure for rapid development 🚀
- **Security headers**: All essential security headers included via middleware 🛡️
- **Rate limiter**: Protects your APIs from brute-force attacks ⚡
- **Authentication with JWT**: Secure user authentication and authorization 🔑
- **Common user routes**: Includes login, signup, forgot/reset password, etc. 👤
- **Syntax & runtime error handling**: Comprehensive error logging and handling 🪲
- **Password encryption/decryption**: Secure password management 🔒
- **MongoDB Atlas & Mongoose@5**: Ready for production-grade cloud databases ☁️

---

## Getting Started

### 1. Installation

There are two ways to use this starter:

#### Method 1: Use NPX (Recommended)
```bash
npx @kapvm/create-express-app <your-app-name>
```

#### Method 2: Clone the GitHub Repo
```bash
git clone https://github.com/kapvm4444/create-express-starter.git
cd create-express-starter
npm install
npm start
```

### 2. Configuration Steps 🛠️

Before you blast off, a few things to check! (Don’t skip these or you’ll be lost in space 🚀✨):

1. **Configure your `.env` file**
  - Copy `.env.example` to `.env`:
    ```bash
    cp .env.example .env
    ```
  - Open up `.env` and fill in every variable (especially your MongoDB URI, JWT secrets, etc).  
    _If you miss any, things might get mysterious! 🕵️_

2. **Adjust the user model**
  - Head to `models/userModel.js` and tweak the user schema to match what your app needs.  
    _Want to store favorite pizza toppings? Go for it! 🍕_

3. **Keep the files where they are**
  - Seriously, don’t move stuff around (unless you’re ready to update all the paths).  
    _Everything is wired together based on the current file structure—shuffle at your own risk!_ 🗂️

4. **Make sure you’re using the right database setup**
  - This starter uses `mongoose@5` and expects a MongoDB Atlas database.  
    _If you’re new to Atlas, check out their [free cluster](https://www.mongodb.com/atlas/database)!_

---

## API Routes

The core user-related API routes are defined in [`routes/userRoutes.js`](https://github.com/kapvm4444/create-express-starter/blob/main/routes/userRoutes.js):

### Public Routes

| Method | Endpoint                   | Description                               |
|--------|----------------------------|-------------------------------------------|
| POST   | `/api/v1/users/signup`     | Register a new user (sign up)             |
| POST   | `/api/v1/users/login`      | Log in with email and password            |
| GET    | `/api/v1/users/logout`     | Log out the current user                  |
| POST   | `/api/v1/users/forgot-password` | Initiate password reset (send email)  |
| PATCH  | `/api/v1/users/reset-password/:token` | Reset user password using token    |

### Protected Routes (require login)

| Method | Endpoint                   | Description                               |
|--------|----------------------------|-------------------------------------------|
| PATCH  | `/api/v1/users/update-password` | Change password when logged in         |
| GET    | `/api/v1/users/me`         | Get current user's profile                |
| PATCH  | `/api/v1/users/update-info`| Update profile info (not password)        |
| DELETE | `/api/v1/users/delete-me`  | Soft-delete (deactivate) current user     |

### Admin-only Routes

| Method | Endpoint                   | Description                               |
|--------|----------------------------|-------------------------------------------|
| GET    | `/api/v1/users/`           | Get all users (admin only)                |
| POST   | `/api/v1/users/`           | Create a new user (admin only)            |
| GET    | `/api/v1/users/:id`        | Get a user by ID (admin only)             |
| PATCH  | `/api/v1/users/:id`        | Update a user by ID (admin only)          |
| DELETE | `/api/v1/users/:id`        | Delete a user by ID (admin only)          |

- **JWT Authentication**: Used for all protected and admin routes.
- **Rate Limiting**: All endpoints are protected by a rate limiter.
- **Security Headers**: HTTP headers like Helmet are set for all responses.
- **Password Handling**: Passwords are encrypted and never returned in API responses.
- **Error Handling**: All API errors are logged with details for troubleshooting.

---

## Using Mongoose & MongoDB Atlas

- The app is configured to use `mongoose@5` for MongoDB Atlas.
- Make sure your `.env` file includes your MongoDB Atlas connection string and relevant credentials.
- You can use any cloud MongoDB provider, but Atlas is easiest to get started!

---

## Contributing

PRs, issues, and feature suggestions are welcome!  
See [issues](https://github.com/kapvm4444/create-express-starter/issues) and [pull requests](https://github.com/kapvm4444/create-express-starter/pulls).

---

> May your bugs be few and your endpoints speedy—deploy with swagger! 🦄✨