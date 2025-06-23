# Notes App Backend

A Node.js backend for the Notes App with user authentication and note management.

## Features

- **User Authentication**: JWT-based authentication with signup/login
- **Note Management**: CRUD operations for user notes
- **Security**: Password hashing with bcrypt
- **Database**: MongoDB with Mongoose ODM
- **API**: RESTful API with Express.js

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn

## Installation

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Set up environment variables**:
   - Copy `config.env` and modify as needed
   - Update `MONGODB_URI` to point to your MongoDB instance
   - Change `JWT_SECRET` to a secure random string

3. **Start MongoDB**:
   - Local: Make sure MongoDB is running on `localhost:27017`
   - Atlas: Use your MongoDB Atlas connection string

## Running the Server

### Development Mode
```bash
npm run dev
```

### Production Mode
```bash
npm start
```

The server will start on `http://localhost:5000`

## API Endpoints

### Authentication
- `POST /api/auth/signup` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)
- `POST /api/auth/logout` - Logout user (protected)

### Notes
- `GET /api/notes` - Get all notes for user (protected)
- `GET /api/notes/:id` - Get specific note (protected)
- `POST /api/notes` - Create new note (protected)
- `PUT /api/notes/:id` - Update note (protected)
- `DELETE /api/notes/:id` - Delete note (protected)

### Health Check
- `GET /api/health` - Server health status

## Environment Variables

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/notes-app
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
NODE_ENV=development
```

## Database Schema

### User
- `username` (String, required, unique)
- `email` (String, required, unique)
- `password` (String, required, hashed)
- `timestamps` (createdAt, updatedAt)

### Note
- `title` (String, required)
- `content` (String, required)
- `user` (ObjectId, ref: User, required)
- `timestamps` (createdAt, updatedAt)

## Security Features

- Password hashing with bcrypt (12 salt rounds)
- JWT token authentication
- Input validation and sanitization
- CORS enabled for frontend integration
- Protected routes with middleware

## Error Handling

The API returns consistent error responses:
```json
{
  "success": false,
  "message": "Error description"
}
```

## Development

- Uses nodemon for auto-restart in development
- Comprehensive error logging
- Input validation with Mongoose schemas
- Proper HTTP status codes 