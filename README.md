# 🚀 DevOps Project: Docker + GitHub Actions CI/CD

## 📌 Project Overview

This project demonstrates a **basic DevOps workflow** by combining **Linux commands, Git, Docker, and CI/CD using GitHub Actions**. A simple Node.js web application is containerized using Docker and automatically built using a CI pipeline whenever code is pushed to GitHub.


---

## 🧰 Tech Stack Used

* **Operating System:** Windows (PowerShell) / Linux (Ubuntu inside Docker & CI)
* **Application:** Node.js (Simple HTTP Server)
* **Containerization:** Docker
* **Version Control:** Git & GitHub
* **CI/CD Tool:** GitHub Actions

---

## 📁 Project Structure

```
devops-docker-ci/
├── app.js
├── package.json
├── Dockerfile
├── public/
│   └── index.html
└── .github/
    └── workflows/
        └── ci.yml
```

---

## 🔹 Application Description

The app runs on **port 3000** inside a Docker container.

---

## 🔹 Dockerfile

The Dockerfile is used to containerize the Node.js application.

```dockerfile
FROM node:18

WORKDIR /app

COPY package.json .
RUN npm install

COPY app.js .
COPY public ./public

EXPOSE 3000

CMD ["npm", "start"]
```

---

## 🔹 Build and Run Docker Container (Local)

```bash
docker build -t devops-app .
docker run -d -p 3000:3000 devops-app
```

Open browser:

```
http://localhost:3000
```

---

## 🔹 GitHub Actions CI/CD Pipeline

The CI pipeline automatically triggers on every push to the `main` branch.

### Workflow File Location

```
.github/workflows/ci.yml
```

### Pipeline Stages

1. Checkout source code
2. Build Docker image
3. Run Docker container

---

## 🔹 How to Trigger CI/CD

1. Make a small code change (UI or app logic)
2. Commit the change
3. Push to GitHub

```bash
git add .
git commit -m "Trigger CI pipeline"
git push origin main
```

Check pipeline status under the **Actions** tab in GitHub.

---

## 🧠 Key DevOps Learnings

* Basic Linux file and directory operations
* Git branch management (`main` branch)
* Docker image and container concepts
* CI/CD automation using GitHub Actions
* Understanding OS abstraction using Docker

---


## 👩‍💻 Author

**Priyanka Raut**

---
