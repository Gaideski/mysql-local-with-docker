# 🐳 Run MySQL + Adminer Locally with Docker

This project lets you run a MySQL database and a simple admin interface (Adminer) on your computer with **just one command** using Docker. No coding required.

---

## ✅ Step 1: Install Docker

Docker lets you run software like MySQL in a safe, isolated environment on your computer.

### 🔗 Use this official guide to install Docker:

👉 **[Docker Installation Guide (Official)](https://docs.docker.com/get-docker/)**

Or download Docker directly based on your computer type:

* **Windows (Intel/AMD)**
  👉 [Download for Windows](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe)

* **macOS (Intel – older Macs)**
  👉 [Download for macOS Intel](https://desktop.docker.com/mac/main/amd64/Docker.dmg)

* **macOS (Apple Silicon – M1, M2, M3 chips)**
  👉 [Download for macOS Apple Silicon](https://desktop.docker.com/mac/main/arm64/Docker.dmg)


### After Installation:

* **Open Docker Desktop:**
    * Locate and launch the Docker Desktop application from your Applications folder (macOS), Start Menu (Windows), or applications launcher (Linux).
    * You may be prompted to grant necessary permissions or restart your computer to complete the installation process. Follow any on-screen instructions.

* **Verify Docker is Running in the Background:**
    * Docker Desktop needs to be actively running for Docker commands to work. You can verify its status using a few methods:

    **1. Universal Verification (Recommended for all OS):**
        * Open your terminal or command prompt.
        * Run a Docker command that requires communication with the Docker daemon:
            ```bash
            docker info
            ```
            or
            ```bash
            docker ps
            ```
        * **If Docker is running:** You will see detailed information about your Docker installation (`docker info`) or a list of running containers (empty if none are running for `docker ps`).
        * **If Docker is NOT running:** You will typically receive an error message indicating that it cannot connect to the Docker daemon (e.g., "Cannot connect to the Docker daemon. Is the docker daemon running?").

    **2. Visual Verification:**
        * **macOS:** Look for the Docker whale icon in your macOS menu bar (top right). A solid white/black icon indicates it's running.
        * **Windows:** Look for the Docker whale icon in your system tray (bottom right, you might need to click the "Show hidden icons" arrow). A solid icon indicates it's running.
        * **Linux:** Open the Docker Desktop application itself; its user interface will clearly indicate its running status.

    * **If Docker Desktop is not running:** Launch the application again. It might take a moment to start up and initialize.

---

## 📁 Step 2: Download the Project

You’ll get the folder and files from this GitHub repository.

### 1. Open your terminal:

* On **Windows**: Press `Windows + R`, type `cmd`, and press Enter
* On **macOS**: Open the **Terminal** app (found in Applications > Utilities)

### 2. Clone the repo

In the terminal, run the following command:

```bash
git clone https://github.com/Gaideski/mysql-local-with-docker.git
```


### 3. Enter the project folder:

```bash
cd mysql-local-with-docker
```

---

## 💻 Step 3: Start the Database and Admin Interface

In the same terminal window:

```bash
docker compose up -d
```

✅ This will:

* Start a local MySQL database on `localhost:3306`
* Start Adminer on your browser at `http://localhost:8080`

---

## 🌐 Step 4: Use Adminer to View the Database

1. Open your browser
2. Go to: [http://localhost:8080](http://localhost:8080)

Fill out the login form like this:

| Field        | Value     |
| ------------ | --------- |
| **System**   | MySQL     |
| **Server**   | mysql\_db |
| **Username** | user      |
| **Password** | password  |
| **Database** | database  |

Click **Login** – now you're in!

---

## 🛑 Step 5: Stop or Restart

### ✅ To **stop everything** (but keep your data):

In the same terminal:

```bash
docker compose stop
```

### 🔁 To **start again** later:

```bash
docker compose start
```

### ❌ To **shut down and remove everything**:

```bash
docker compose down
```

---

## 🗃️ Where Your Data Is Stored

Your MySQL database is saved in a special Docker volume called `mysql_data`. It will not be lost unless you manually delete it or call `docker composer down`.

---


