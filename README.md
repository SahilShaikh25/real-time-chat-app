# 💬 Real-Time Chat Application (`rtchatapp`)

A modern, fast, and feature-rich real-time chat application built with **Django**, **Django Channels**, **Daphne**, and **HTMX**. This project allows users to communicate instantly through WebSockets without page reloads, manage profiles, and participate in dynamic chat rooms.

---

## 🚀 Features

* **Real-Time Messaging:** Powered by WebSockets and Django Channels for instant, bi-directional communication.
* **Modern Frontend Interactivity:** Uses **HTMX** for seamless partial page updates and smooth UI interactions.
* **User Authentication & Profiles:** Secure sign-up, login, and email verification managed via **Django Allauth**, accompanied by customizable user profiles.
* **Unique Chat Identifiers:** Clean, URL-friendly unique IDs generated via `shortuuid` for chat rooms.
* **ASGI Server Support:** Runs on **Daphne** to handle asynchronous protocols alongside standard HTTP requests.

---

## 🧰 Tech Stack

* **Backend:** Python, Django 4.2+
* **Real-Time / Async:** Django Channels, Daphne, WebSockets
* **Frontend:** HTML5, CSS (Tailwind/Custom), JavaScript, HTMX
* **Authentication:** Django Allauth
* **Database:** SQLite3 (Development)

---

## 📂 Project Structure

```text
rtchatapp/
│
├── a_core/             # Project configuration files (settings, asgi, wsgi, urls)
├── a_home/             # Landing/Home app handling general views and homepage logic
├── a_rtchat/           # Core chat application (models, consumers, routing, views)
├── a_users/            # User management, profile settings, and authentication views
├── media/              # User-uploaded media (profile pictures, attachments)
├── static/             # Global static assets (CSS, JS, images)
├── templates/          # Global HTML templates
├── venv/               # Python virtual environment
├── db.sqlite3          # SQLite database file
├── manage.py           # Django command-line utility
├── requirements.txt    # Project Python dependencies
└── README.md           # Project documentation
```

* **`a_core/`**: Houses core project settings, ASGI configuration for WebSockets, and main URL routings.
* **`a_home/`**: Manages the public-facing homepage and general routing.
* **`a_rtchat/`**: The heart of the chat system containing WebSocket consumers, message models, and room handlers.
* **`a_users/`**: Manages user profiles, custom user logic, and authentication extensions.

---

## ⚙️ Prerequisites

Make sure you have the following installed on your local machine:
* Python 3.9 or higher
* Git
* Homebrew (if running on macOS for OpenSSL dependencies)

---

## 📥 Installation & Setup Guide

Follow these steps to set up and run the project locally:

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/rtchatapp.git
cd rtchatapp
```

### 2. Create and Activate Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies
Install all required Python packages:
```bash
pip install -r requirements.txt
```
*(If you encounter OpenSSL/Rust build errors on macOS, ensure your dependencies like `cryptography` and `daphne` are installed using pre-compiled wheels).*

### 4. Apply Database Migrations
Set up your SQLite database tables:
```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create a Superuser (Optional)
To access the Django admin panel:
```bash
python manage.py createsuperuser
```

### 6. Run the Development Server
Start the application using Daphne/Django runserver (which automatically handles ASGI/WebSockets via Daphne configuration):
```bash
python manage.py runserver
```

Open your browser and navigate to: `http://127.0.0.1:8000/`

---

## 🔐 Environment Configuration

For local development, SQLite is configured by default. If you plan to extend this project for production, ensure you manage sensitive variables (like `SECRET_KEY` and `DEBUG`) using environment variables (`.env`).

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check out the [issues page](https://github.com/your-username/rtchatapp/issues).

---

## 📝 License

This project is open-source and available under the [MIT License](LICENSE).