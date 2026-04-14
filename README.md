# 🧠 Task Management API (Conversly Assignment)

## 🚀 Tech Stack

* Node.js
* Express.js
* MongoDB (Mongoose for Tasks)
* Prisma ORM (PostgreSQL for Users)
* Zod (Validation)
* JWT Authentication
* pnpm (Package Manager)
* tsx (Run TypeScript directly)

---

## ⚙️ Setup Instructions

### 1. Clone Repository

git clone https://github.com/Farhandev097/conversely-assigment.git
cd conversely-assigment

---

### 2. Install Dependencies

pnpm install

---

### 3. Setup Environment Variables

Create a `.env` file in the root directory:

PORT=3000
MONGO_URL=your_mongodb_connection_string
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_secret_key

---

### 4. Setup Prisma (User Database)

npx prisma generate
npx prisma migrate dev

---

### 5. Start the Server

pnpm start

Or run in development mode:

pnpm dev

---

## 🔐 Authentication APIs

### ➤ Register User

**POST** `user/signup`

```json
{
  "email": "test@example.com",
  "name": "Farhan",
  "password": "123456"
}
```

---

### ➤ Login User

**POST** `user/signin`

```json
{
  "email": "test@example.com",
  "password": "123456"
}
```

📌 Response: JWT Token

---

## 📋 Task APIs (Protected Routes)

🔒 Add Header:
Authorization: Bearer <token>

---

### ➤ Create Task

**POST** `/tasks/add-task`

```json
{
  "title": "Learn Backend",
  "description": "Practice APIs",
  "dueDate": "2026-04-15",
  "status": "pending"
}
```

---

### ➤ Get All Tasks

**GET** `/tasks/all-task`

✔ Returns all tasks of logged-in user

---

### ➤ Update Task

**PUT** `/tasks/update-task`

```json
{
  "taskId": "taskId"
  "title": "Updated Task"
}
```

✔ Supports partial updates

---

### ➤ Delete Task

**DELETE** `/tasks/delete-task`

---

## 🧠 Folder Structure

src/
├── controllers/
├── models/
├── routes/
├── middlewares/
├── validators/
├── config/
└── server.ts

---

## 🧩 Design Decisions

* Prisma used for User management (structured & scalable)
* Mongoose used for Tasks (flexible schema)
* Zod used for request validation
* JWT used for authentication
* Tasks linked with users using `userId`

---

## 🔐 Security Features

* Users can only access their own tasks
* JWT-based authentication for protected routes
* Attempt to access another user’s task will fail

---

## ⚠️ Validation & Error Handling

* Zod validates all inputs (body + params)
* Proper error messages returned
* Handles:

  * Invalid IDs
  * Missing fields
  * Invalid dates
  * Unauthorized access

---

## 🧪 Postman Collection

Download and import into Postman:

https://github.com/Farhandev097/conversely-assigment/blob/main/postman/task-api.postman_collection.json

### How to use:

1. Download the JSON file
2. Open Postman
3. Click **Import**
4. Select the file

---

## 🎥 Demo Video

https://drive.google.com/file/d/1LNj4qWy0dQmL8zdx22DMsMiVjZCJkWIx/view?usp=sharing

### Video should include:

* User registration & login
* Task CRUD operations
* Unauthorized access test
* Validation error handling

---

## 👨‍💻 Author

Farhan Khan

---

## ⭐ Final Notes

This project demonstrates:

* Clean backend architecture
* Secure authentication system
* Scalable API design
* Real-world validation & error handling

---
