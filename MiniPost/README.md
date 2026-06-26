# MiniPost — A Social Posting Platform

A full-stack social media mini-application built with **Express.js**, **MongoDB**, and **EJS**. Users can register, log in, create posts, like/unlike posts, edit content, and upload profile pictures — all with JWT-based authentication.

---

## Features

- **User Authentication** — Register & login with bcrypt-hashed passwords and JWT cookies
- **Create Posts** — Share text content from your profile
- **Like / Unlike** — Toggle likes on any post
- **Edit Posts** — Update your post content inline
- **Profile Picture Upload** — Upload and display a custom avatar via Multer
- **Session Management** — Cookie-based auth with logout support

---

## Tech Stack

| Layer      | Technology              |
| ---------- | ----------------------- |
| Runtime    | Node.js                 |
| Framework  | Express.js 5            |
| Database   | MongoDB (via Mongoose)  |
| Templating | EJS                     |
| Auth       | JWT + bcrypt            |
| Uploads    | Multer                  |

---

## Project Structure

```
.
├── app.js                  # Main server & routes
├── config/
│   └── multerconfig.js     # Multer file-upload configuration
├── models/
│   ├── user.js             # User schema (Mongoose)
│   └── post.js             # Post schema (Mongoose)
├── views/
│   ├── index.ejs           # Home / Register page
│   ├── login.ejs           # Login page
│   ├── profile.ejs         # User profile & feed
│   ├── profileupload.ejs   # Profile picture upload form
│   └── edit.ejs            # Edit post page
├── public/
│   ├── images/             # Uploaded profile pictures
│   ├── javascripts/        # Client-side JS
│   └── stylesheets/        # CSS files
├── package.json
└── README.md
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [MongoDB](https://www.mongodb.com/) running locally or a cloud URI

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Install dependencies
npm install
```

### Run the Server

```bash
node app.js
```

The app will start on **http://localhost:3000**.

---

## API Routes

| Method | Route              | Auth | Description                  |
| ------ | ------------------ | ---- | ---------------------------- |
| GET    | `/`                | No   | Home / Register page         |
| POST   | `/register`        | No   | Create a new user account    |
| GET    | `/login`           | No   | Login page                   |
| POST   | `/login`           | No   | Authenticate & set JWT       |
| GET    | `/profile`         | Yes  | View profile & posts         |
| POST   | `/post`            | Yes  | Create a new post            |
| GET    | `/like/:id`        | Yes  | Toggle like on a post        |
| GET    | `/edit/:id`        | Yes  | Edit post form               |
| POST   | `/update/:id`      | Yes  | Update post content          |
| GET    | `/profile/upload`  | No   | Profile picture upload form  |
| POST   | `/upload`          | Yes  | Upload profile picture       |
| GET    | `/logout`          | No   | Clear cookie & logout        |

---

## Environment Notes

> The JWT secret is currently hardcoded as `"shh"`. For production, move it to an environment variable.

---

## License

ISC
