# 🔗 Simplified LinkedIn-Style Web App

A modern full-stack web application inspired by LinkedIn.  
Users can register, log in, create posts, edit their profile, and view a public feed.

Built with:
- **ReactJS** (frontend)
- **NodeJS + ExpressJS** (backend)
- **MySQL** (database)
- **JWT** for authentication
- **bcrypt** for password hashing

---

## ✨ Features

### 🔐 Authentication
- Register with name, email, and password
- Secure login with JWT token
- Password hashing using bcrypt
- Token-based route protection

### 👤 Profile Page
- View user info: name, bio, profile picture
- Edit profile details
- Change password with validation

### 📝 Post Feed
- View all user posts on a public feed
- Create a new post
- View post content, author name, and timestamp

### ✅ Optional Stretch Features
- Upload profile picture via image URL
- Like button on posts
- Edit/delete own posts
- Pagination (Load More feature)

---

## 🛠 Tech Stack

| Frontend      | Backend        | Database | Auth        |
|---------------|----------------|----------|-------------|
| ReactJS       | NodeJS         | MySQL    | JWT         |
| Axios         | ExpressJS      |          | bcrypt      |
| React Router  | RESTful API    |          |             |
| (TailwindCSS) |                |          |             |

---

## 🗂 Folder Structure


---

## 🧱 Database Schema (ERD)

### `users` table
| Column        | Type          | Description              |
|---------------|---------------|--------------------------|
| id            | INT, PK       | User ID (auto increment) |
| name          | VARCHAR       | Full name                |
| email         | VARCHAR       | Unique email             |
| password      | VARCHAR       | Hashed password          |
| bio           | TEXT          | Short bio                |
| profile_pic   | TEXT          | Profile picture URL      |
| created_at    | DATETIME      | Auto timestamp           |

### `posts` table
| Column        | Type          | Description              |
|---------------|---------------|--------------------------|
| id            | INT, PK       | Post ID (auto increment) |
| user_id       | INT, FK       | Author (users.id)        |
| content       | TEXT          | Post text                |
| created_at    | DATETIME      | Auto timestamp           |

---

## 🔌 API Endpoints

### 🔐 Auth Routes (`/api/auth`)
| Method | Endpoint      | Description         |
|--------|---------------|---------------------|
| POST   | `/register`   | Register new user   |
| POST   | `/login`      | Authenticate & get token |

### 👤 User Routes (`/api/users`)
| Method | Endpoint         | Description              |
|--------|------------------|--------------------------|
| GET    | `/me`            | Get current user profile |
| PUT    | `/me`            | Update profile info      |
| PUT    | `/me/password`   | Change user password     |

### 📝 Post Routes (`/api/posts`)
| Method | Endpoint      | Description                |
|--------|---------------|----------------------------|
| GET    | `/`           | Get all posts (feed)       |
| POST   | `/`           | Create new post            |
| PUT    | `/:id`        | Edit own post              |
| DELETE | `/:id`        | Delete own post            |

---

## ⚙️ Environment Variables

Create `.env` file inside `/backend` folder:

```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=linkedin_clone
JWT_SECRET=your_secret_key
