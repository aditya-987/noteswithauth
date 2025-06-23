# Notes App with Authorisation

A full-stack notes application with user authentication, built with React, Node.js, Express, and MongoDB (Atlas). Users can sign up, log in, and manage their personal notes securely.

---

## Features
- **User Signup & Login** (JWT authentication)
- **Personal Notes**: Each user sees only their notes
- **Create, Edit, Delete Notes**
- **MongoDB Atlas** for cloud data storage
- **Password Hashing** with bcrypt
- **Responsive UI** with React
- **RESTful API** with Express

---

## Project Structure
```
Notes App with authorisation/
├── backend/           # Node.js/Express/MongoDB API
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── server.js
│   ├── config.env
│   └── ...
├── notes-app/         # React frontend
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
└── README.md          # (this file)
```

---

## Getting Started

### 1. **Clone the Repository**
```sh
git clone <repo-url>
cd "Notes App with authorisation"
```

### 2. **Setup MongoDB Atlas**
- Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- Create a cluster and database user
- Whitelist your IP address
- Copy your connection string

### 3. **Configure Backend**
- Go to the `backend/` folder
- Create or edit `config.env`:
  ```env
  PORT=5000
  MONGODB_URI=your-mongodb-atlas-connection-string
  JWT_SECRET=your-very-secret-key
  NODE_ENV=development
  ```
- Install dependencies:
  ```sh
  npm install
  ```

### 4. **Start the Backend**
```sh
npm start
```
- The backend runs on [http://localhost:5000](http://localhost:5000)

### 5. **Start the Frontend**
- Open a new terminal, go to `notes-app/`:
  ```sh
  cd notes-app
  npm install
  npm start
  ```
- The frontend runs on [http://localhost:3000](http://localhost:3000)

---

## Usage
- Open [http://localhost:3000](http://localhost:3000)
- Sign up for a new account
- Log in
- Add, edit, and delete your notes
- Log out when done

---

## Security
- Passwords are hashed with bcrypt before storage
- JWT tokens are used for authentication
- All notes are private to each user
- CORS enabled for frontend-backend communication

---
