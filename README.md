Here's a simple and complete `README.md` for your Docker Compose setup:

---

# 🐳 Local MySQL + Adminer with Docker Compose

This project provides a ready-to-run local MySQL database and Adminer interface using Docker Compose. It ensures cross-platform compatibility for Windows, macOS (Intel & Apple Silicon), and Linux using the `linux/amd64` platform target.

## 📦 Services Included

* **MySQL**
  Runs on port `3306` with preconfigured credentials.

* **Adminer**
  A lightweight database admin interface running on port `8080`.

---

## 🚀 Prerequisites

### ✅ Docker Installation

Install Docker Desktop from the official sources based on your OS:

### 🪟 Windows (x86/AMD64)

1. Download Docker Desktop: [https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe)
2. Run the installer and follow the instructions.
3. After installation, launch Docker Desktop and ensure it is running.

### 🍎 macOS Intel (x86)

1. Download: [https://desktop.docker.com/mac/main/amd64/Docker.dmg](https://desktop.docker.com/mac/main/amd64/Docker.dmg)
2. Open the `.dmg` and move Docker to Applications.
3. Launch Docker and allow it to run in the background.

### 🍏 macOS Apple Silicon (ARM/M1/M2)

1. Download: [https://desktop.docker.com/mac/main/arm64/Docker.dmg](https://desktop.docker.com/mac/main/arm64/Docker.dmg)
2. Open the `.dmg` and move Docker to Applications.
3. Launch Docker and allow it to run.

You can verify installation with:

```bash
docker --version
docker compose version
```

---

## ⚙️ Usage Instructions

### ▶️ Start the Services

In your terminal, navigate to the folder containing the `docker-compose.yml` file and run:

```bash
docker compose up -d
```

This will:

* Launch a local MySQL server on `localhost:3306`
* Start Adminer on `http://localhost:8080`

### ⏹️ Stop the Services

To shut everything down:

```bash
docker compose down
```

To stop but preserve data:

```bash
docker compose stop
```

### 🔁 Restart

```bash
docker compose restart
```

---

## 🔑 Database Credentials

| Property       | Value           |
| -------------- | --------------- |
| Host           | `localhost`     |
| Port           | `3306`          |
| Database Name  | `database`      |
| MySQL User     | `user`          |
| MySQL Password | `password`      |
| Root Password  | `root_password` |

---

## 🌐 Access Adminer

Go to: [http://localhost:8080](http://localhost:8080)

* **System**: MySQL
* **Server**: `mysql_db` or `localhost`
* **Username**: `user`
* **Password**: `password`
* **Database**: `database` (optional)

---

## 🗃️ Persisted Data

Database data is stored in a Docker volume named `mysql_data`. It persists between container restarts and shutdowns.

---

## 📌 Notes

* This Compose file targets the `linux/amd64` platform to ensure compatibility with both Intel and ARM-based systems (e.g., MacBooks with Rosetta).
* Adjust credentials or ports as needed for your project.

---

Let me know if you want a `.env` file or `.dockerignore` included too.
