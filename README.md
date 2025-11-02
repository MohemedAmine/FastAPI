# 🧩 FastAPI Users & Posts Management App

A simple **FastAPI + SQLAlchemy + Jinja2** web application for managing **users and their posts**, featuring both a **RESTful API** and a small **interactive web interface** built with HTML, CSS, and JavaScript.

---

## 🚀 Features

- Create, read, and list **users**
- Create, view, and delete **posts** for each user
- View all posts in a dedicated page
- Interactive **frontend UI** (HTML + JS + Fetch API)
- SQLite database with **SQLAlchemy ORM**
- Templating using **Jinja2**

---

## 🧱 Tech Stack

| Layer | Technology |
|--------|-------------|
| **Backend** | [FastAPI](https://fastapi.tiangolo.com/) |
| **Database** | SQLite + SQLAlchemy ORM |
| **Frontend** | HTML, CSS, JavaScript (Fetch API) |
| **Templates** | Jinja2 |
| **Validation** | Pydantic |

---

## ⚙️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/MohemedAmine/FastApi.git
cd FastApi
```

### 2. Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate      # On Linux/Mac
venv\Scripts\activate         # On Windows
```

### 3. Install Dependencies
```bash
pip install fastapi uvicorn sqlalchemy jinja2 pydantic
```

### 4. Run the App
```bash
uvicorn main:app --reload
```

The app will be available at 👉 **http://127.0.0.1:8000**

---

## 🌐 Available Endpoints

### 🧑 User Endpoints
| Method | Endpoint | Description |
|--------|-----------|-------------|
| **GET** | `/users/` | Get all users |
| **GET** | `/users/{user_id}` | Get user by ID |
| **POST** | `/users/new` | Create a new user |
| **GET** | `/users/{user_id}/posts/` | Get all posts by a user |
| **POST** | `/users/{user_id}/posts/new` | Create a post for a user |
| **DELETE** | `/users/{user_id}/delete_post/{post_id}` | Delete a user’s post |

### 📰 Post Endpoints
| Method | Endpoint | Description |
|--------|-----------|-------------|
| **GET** | `/posts` | View all posts (HTML view) |

---

## 🖥️ Web Interface

### Main Page (`/`)
- Create a user  
- List users  
- View, create, or delete posts per user  

### Posts Page (`/posts`)
- View all posts in a table format

---

## 🧰 Example Usage

### ➕ Create a User
**POST** `/users/new`
```json
{
  "name": "John Doe",
  "email": "john@example.com"
}
```

### ➕ Create a Post
**POST** `/users/1/posts/new`
```json
{
  "title": "My First Post",
  "content": "Hello FastAPI!"
}
```

---

## 🗃️ Database Models

**User**
| Field | Type | Description |
|--------|------|-------------|
| id | Integer | Primary key |
| name | String | User name |
| email | String | Unique email |
| posts | Relationship | One-to-many with posts |

**Post**
| Field | Type | Description |
|--------|------|-------------|
| id | Integer | Primary key |
| title | String | Post title |
| content | Text | Post content |
| author | ForeignKey | References `users.id` |
| publishedAt | DateTime | Auto-generated timestamp |

---

## 🧑‍💻 Author
**Mohamed amine OULAD SAID**  
📧 Email: mohamedamineouledsaid10@gmail.com

---

## 🪪 License
This project is open-source under the [MIT License](LICENSE).

---

## 💡 Notes
- The SQLite database (`db.db`) is automatically created in the project directory.
- You can easily switch to another database (e.g., PostgreSQL, MySQL) by changing the `DB_URI` in `db.py`.
- Run with `--reload` for automatic updates during development.

---

✨ **Enjoy building with FastAPI!**
