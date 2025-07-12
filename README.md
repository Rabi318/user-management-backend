# 🔐 Backend – RBAC User Management System

This is the **Node.js + Express** backend API for a **Role-Based Access Control (RBAC)** user management system. It provides secure endpoints for **authentication**, **resource management**, and **user control**, integrating **JWT authentication** and **MongoDB** for data storage.

---

## 🌐 Deployed Links

- 🔗 **Backend API**: [API Endpoint](https://user-management-backend-3440.onrender.com)

## ✨ Features

- 🛡️ **JWT Authentication**
- 🔑 **Role-Based Access Control**
  - `admin`: Full access (users & resources)
  - `moderator`: Limited resource management
  - `user`: View-only access
- 📦 **RESTful API Endpoints**
- 🧾 **MongoDB** with Mongoose ODM
- ✅ **Input Validation** and error handling
- 🔐 Password hashing using **bcrypt**

---

## 🛠️ Tech Stack

| Tech       | Description                     |
| ---------- | ------------------------------- |
| Node.js    | Backend JavaScript runtime      |
| Express.js | Web framework                   |
| MongoDB    | NoSQL Database                  |
| Mongoose   | MongoDB ODM                     |
| JWT        | Authentication via tokens       |
| bcrypt     | Password hashing                |
| dotenv     | Environment variable management |
| cors       | Cross-origin requests support   |

---

## 📦 Project Structure

```
backend/
├── middleware/
│ ├── authMiddleware.js
├── models/
│ ├── userModel.js
│ └── resourceModel.js
├── routes/
│ ├── authRoutes.js
│ ├── resourceRoutes.js
│ └── userRoutes.js
├── .env
├── server.js
├── config/
│ └── db.js
├── package.json
└── README.md
```

### 3. 🛠️ Setup Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

<details>
<summary><code>.env</code></summary>

```env
PORT=3000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/your-db
JWT_SECRET=your_jwt_secret_key
```
## 📬 API Endpoints

### 🔐 Auth

| Method | Route         | Access | Description          |
|--------|---------------|--------|----------------------|
| POST   | `/api/register` | Public | Register new user     |
| POST   | `/api/login`    | Public | Login & get token     |


---

### 👤 User (Admin Only)

| Method | Route       | Access | Description     |
|--------|-------------|--------|-----------------|
| GET    | `/api/users` | Admin  | Get all users   |

---

### 📄 Resources

| Method | Route                     | Access     | Description         |
|--------|---------------------------|------------|---------------------|
| GET    | `/api/resources`          | All Roles  | Get all resources   |
| POST   | `/api/resources`          | Admin      | Create a resource   |
| PUT    | `/api/resources/:id`      | Admin      | Update a resource   |
| DELETE | `/api/resources/:id`      | Admin      | Delete a resource   |


