```markdown
# Relay Server Integration

This repository contains the environment configuration to run the [relay-server](https://github.com/trntuan/relay-server) project using Docker Compose. It sets up all necessary dependencies and securely passes secrets like Firebase credentials and application-specific config.


## 📁 Folder Structure


oripark-backend/
├── docker-compose.yml          # Docker Compose file
├── my-firebase.json            # Firebase Admin SDK credentials (DO NOT commit)
├── my_secrets.py               # Application-level secrets or settings
└── relay-server/               # Cloned source code of the relay-server

````

---

## 🚀 Getting Started

### 1. Clone this repository (or setup your own)

```bash
git clone https://github.com/trntuan/build-relay-server
cd oripark-backend
````

### 2. Clone the `relay-server` source

```bash
git clone https://github.com/trntuan/relay-server
```

### 3. Add required secret files

You must manually place the following files in the project root:

* `my-firebase.json`: Firebase Admin SDK credentials
* `my_secrets.py`: Any secret keys or environment-specific configs your app expects

> ⚠️ **Do NOT commit these files to Git.** Use `.gitignore` to keep them private.

---

## 🐳 Run with Docker Compose

To build and start the `relay-server` container:

```bash
docker-compose up --build
```

The server should now be running and accessible at: [http://localhost:8899](http://localhost:8899)

---

## 🔧 Configuration Details

* The `relay-server` is built from the local `relay-server/` folder.
* The Docker image uses Python 3.10.12 and installs all dependencies via `requirements.txt`.
* Environment variables and secret files are mounted into the container via `volumes` for security.

---

## 📦 Example `.gitignore`

```gitignore
my-firebase.json
my_secrets.py
.env
__pycache__/
*.pyc
*.log
```

---

## ✅ Requirements

* Docker
* Docker Compose

---

## 🧪 Troubleshooting

* Make sure `my-firebase.json` and `my_secrets.py` exist before running `docker-compose up`.
* If ports conflict with other services, change the `ports:` value in `docker-compose.yml`.

---
