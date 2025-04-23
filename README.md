# TaskMaster Backend API

![Node.js](https://img.shields.io/badge/Node.js-18.x-green)
![Express](https://img.shields.io/badge/Express-4.x-lightgrey)
![MongoDB](https://img.shields.io/badge/MongoDB-6.x-green)

A robust backend API for TaskMaster task management application with JWT authentication and CRUD operations.

## 📦 Features

- **User Authentication**
  - Registration with email/password
  - Login with JWT token
  - Protected routes middleware
  - Password hashing with bcrypt

- **Task Management**
  - Create, Read, Update, Delete tasks
  - Task synchronization
  - User-specific task isolation
  - Timestamps for all operations

## 🛠 Technologies

- **Runtime**: Node.js
- **Framework**: Express
- **Database**: MongoDB (Mongoose ODM)
- **Authentication**: JWT
- **Security**: bcrypt password hashing
- **Middleware**: CORS, JSON body parsing

## 📂 Project Structure
backend/    
├── controllers/    
│ ├── authController.js    
│ └── taskController.js    
├── models/    
│ ├── taskModel.js    
│ └── userModel.js    
├── middleware/ # Auth middleware    
│ └── authMiddleware.js    
├── routes/ # API endpoints    
│ ├── authRoutes.js    
│ └── taskRoutes.js    
├── server.js     
└── .env     


## 🚀 Installation



```bash
git clone https://github.com/zwezdica/task_master_backend.git
cd taskmaster-backend
npm install
```

## ⚙️ Configuration

Create .env file:

```env
MONGO_URI=mongodb://localhost:27017/taskmaster
JWT_SECRET=your_strong_secret_here
PORT=5000
```

## 🏃 Running the Server

```bash
npm start
```

## 📡 API Endpoints

### 🔒 Authentication

#### User Registration
```http
POST /api/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securepassword123"
}
```

#### User Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "securepassword123"
}
```

### 📝 Task Endpoints

#### Get All Tasks
```http
GET /api/tasks
Authorization: Bearer <JWT_TOKEN>
```

#### Create New Task
```http
POST /api/tasks
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json

{
  "title": "Complete project",
  "description": "Finish the TaskMaster app", 
  "completed": false
}
```




## 🔒 Security Features

| Feature               | Implementation Details                  | Status  |
|-----------------------|----------------------------------------|---------|
| 🔐 JWT Expiration     | 1 day token validity                   | ✅ Live |
| 🗝️ Password Hashing   | bcrypt with 12 salt rounds             | ✅ Live |
| 🚧 Protected Routes   | JWT verification middleware            | ✅ Live |
| 🛡️ NoSQL Prevention   | Data sanitization + query validation   | ✅ Live |
| 🌐 CORS               | Strict origin policy                   | ✅ Live |
