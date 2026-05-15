# 📝 To-Do List Management App

<div align="center">

![Registration page]<img width="1598" height="883" alt="Regstration page" src="https://github.com/user-attachments/assets/97a4ca90-7a6d-4023-8dd4-fe5c061e8dbc" />

![Login Page]<img width="1236" height="860" alt="Login Page" src="https://github.com/user-attachments/assets/d44583fe-1c74-47ce-9ea4-99dc93543551" />

![Dashboard]<img width="1618" height="893" alt="Dashboard" src="https://github.com/user-attachments/assets/817e7c5b-b582-4a74-8bcc-99d45d3906dc" />

![Edit Task]<img width="1677" height="927" alt="edit" src="https://github.com/user-attachments/assets/85686aff-3926-471f-a4b2-0e6415a44d4c" />

![Tasks]<img width="1493" height="732" alt="tasks" src="https://github.com/user-attachments/assets/508b794b-d78b-4758-916c-8d201c13af25" />


**A modern, full-stack To-Do List web application built with Laravel.**
Secure authentication · Interactive charts · Beautiful dark UI 🚀

[Features](#-features) · [Screenshots](#-screenshots) · [Installation](#️-installation--setup) · [Tech Stack](#️-tech-stack)

</div>

---

## ✨ Features

### 🔐 Authentication
| Feature | Description |
|---|---|
| **Register** | Create a new account with name, email and password |
| **Login** | Secure login with email and password |
| **Logout** | One-click secure logout |
| **Private Tasks** | Every user sees only their own tasks |

### 📋 Task Management
| Feature | Description |
|---|---|
| ➕ **Add Tasks** | Create tasks with title, description, due date and priority |
| ✏️ **Edit Tasks** | Update any task detail at any time |
| 🗑️ **Delete Tasks** | Remove tasks with a confirmation prompt |
| ✅ **Toggle Status** | Switch tasks between Pending and Completed instantly |
| 🔍 **Search Tasks** | Search tasks by title or description in real time |
| 🔽 **Filter Tasks** | Filter by All, Pending, or Completed status |

### 📊 Interactive Dashboard
| Chart | Description |
|---|---|
| 🍩 **Doughnut Chart** | Visual breakdown of Pending vs Completed tasks |
| 📊 **Bar Chart** | Tasks grouped by priority — High, Medium, Low |
| 📈 **Line Chart** | Tasks created over the last 7 days |

---

## 🖥️ Screenshots

> **Login Page** — Modern split-panel design with feature highlights

> **Register Page** — Clean registration form with step-by-step guide panel

> **Dashboard** — Dark themed dashboard with stats, charts, and task list

> **Edit Page** — Pre-filled form to update task details

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Laravel 12, PHP 8.2+ |
| **Authentication** | Laravel Breeze |
| **Database** | MySQL via XAMPP |
| **Frontend** | Bootstrap 5.3, Font Awesome 6.4 |
| **Charts** | Chart.js 4.x |
| **Fonts** | Google Fonts — Poppins |
| **Dev Tools** | XAMPP, Composer, VS Code, Git |

---

## ⚙️ Installation & Setup

### Prerequisites
Make sure you have these installed:
- PHP 8.1+
- Composer
- XAMPP (Apache + MySQL)
- Node.js & npm
- Git

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/Moizahmad2399/Task-Management.git
cd todo-app
```

### Step 2 — Install PHP Dependencies

```bash
composer install
```

### Step 3 — Install Node Dependencies

```bash
npm install --legacy-peer-deps
```

### Step 4 — Build Frontend Assets

```bash
npm run build
```

### Step 5 — Create Environment File

```bash
cp .env.example .env
```

### Step 6 — Configure Database

Open `.env` and update:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=todo_db
DB_USERNAME=root
DB_PASSWORD=
```

### Step 7 — Generate App Key

```bash
php artisan key:generate
```

### Step 8 — Run Migrations

```bash
php artisan migrate
```

### Step 9 — Start the Server

```bash
php artisan serve
```

### Step 10 — Open in Browser

```
http://127.0.0.1:8000
```

---

## 🚀 Usage

1. **Register** a new account at `/register`
2. **Login** with your credentials at `/login`
3. **Add tasks** using the form on the left side
4. **View charts** showing your task statistics
5. **Toggle** task status with the green ✅ button
6. **Edit** tasks using the yellow ✏️ button
7. **Delete** tasks using the red 🗑️ button
8. **Search** tasks using the search bar
9. **Filter** tasks using All / Pending / Completed tabs
10. **Logout** using the button in the top navbar

---

## 📁 Project Structure

```
todo-app/
├── app/
│   ├── Http/
│   │   └── Controllers/
│   │       ├── TaskController.php        # All task logic
│   │       └── Auth/                     # Breeze auth controllers
│   └── Models/
│       ├── Task.php                      # Task model
│       └── User.php                      # User model
├── database/
│   └── migrations/
│       ├── xxxx_create_users_table.php
│       ├── xxxx_create_tasks_table.php
│       └── xxxx_add_user_id_to_tasks.php
├── resources/
│   └── views/
│       ├── auth/
│       │   ├── login.blade.php           # Login page
│       │   └── register.blade.php        # Register page
│       ├── layouts/
│       │   └── app.blade.php             # Main layout
│       └── tasks/
│           ├── index.blade.php           # Dashboard + Charts
│           └── edit.blade.php            # Edit task page
└── routes/
    ├── web.php                           # App routes
    └── auth.php                          # Breeze auth routes
```

---

## 🗄️ Database Schema

**Table: `tasks`**

| Column | Type | Description |
|---|---|---|
| `id` | BIGINT | Primary key, auto increment |
| `user_id` | BIGINT | Foreign key → users table |
| `title` | VARCHAR | Task title |
| `description` | TEXT | Task description (nullable) |
| `due_date` | DATE | Task due date (nullable) |
| `priority` | ENUM | High / Medium / Low |
| `status` | ENUM | Pending / Completed |
| `created_at` | TIMESTAMP | Auto generated |
| `updated_at` | TIMESTAMP | Auto generated |

---

## 🔗 Routes

| Method | URL | Action | Auth Required |
|---|---|---|---|
| GET | `/` | Redirect to tasks | ✅ |
| GET | `/tasks` | Show dashboard | ✅ |
| POST | `/tasks` | Store new task | ✅ |
| GET | `/tasks/{id}/edit` | Show edit form | ✅ |
| PUT | `/tasks/{id}` | Update task | ✅ |
| DELETE | `/tasks/{id}` | Delete task | ✅ |
| PATCH | `/tasks/{id}/toggle` | Toggle status | ✅ |
| GET | `/register` | Register page | ❌ |
| GET | `/login` | Login page | ❌ |
| POST | `/logout` | Logout | ✅ |

---

## 👨‍💻 Author

**Moiz Ahmad**
🎓 BSSE — COMSATS University Islamabad, Vehari Campus
📧 your-moizahmad2399@gmail.com
🌐 [github.com/Moizahmad2399](https://github.com/Moizahmad2399)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

Made with ❤️ using Laravel & Chart.js
⭐ Star this repo if you found it helpful!

**CSC336 Web Technologies — Assignment 3 · Spring 2026**

</div>
