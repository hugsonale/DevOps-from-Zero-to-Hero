# 🐳 Docker Installation & Docker Hub Setup Guide (Step-by-Step)

This guide walks you through installing Docker, setting it up, and connecting it to Docker Hub from start to finish.

---

# 📌 STEP 1 — Update Your System

```bash
sudo apt update
sudo apt upgrade -y
```

---

# 📌 STEP 2 — Install Required Packages

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

---

# 📌 STEP 3 — Add Docker GPG Key

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

---

# 📌 STEP 4 — Add Docker Repository

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

> ⚠️ If using Ubuntu 22.04+, replace `focal` with `jammy`

---

# 📌 STEP 5 — Update Package List

```bash
sudo apt update
```

---

# 📌 STEP 6 — Install Docker

```bash
sudo apt install docker-ce -y
```

---

# 📌 STEP 7 — Verify Installation

```bash
docker --version
```

---

# 📌 STEP 8 — Start and Enable Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Check status:

```bash
sudo systemctl status docker
```

---

# 📌 STEP 9 — Run Docker Without sudo

```bash
sudo usermod -aG docker $USER
```

Apply changes:

```bash
newgrp docker
```

Test:

```bash
docker run hello-world
```

---

# 📌 STEP 10 — Install Docker Compose (Optional)

```bash
sudo apt install docker-compose-plugin -y
```

Verify:

```bash
docker compose version
```

---

# 📌 STEP 11 — Create Docker Hub Account

Visit:

[https://hub.docker.com](https://hub.docker.com)

Steps:

* Click **Sign Up**
* Enter username, email, and password

---

# 📌 STEP 12 — Login to Docker Hub

```bash
docker login
```

Enter your Docker Hub credentials.

---

# 📌 STEP 13 — Pull an Image

```bash
docker pull nginx
```

---

# 📌 STEP 14 — Run a Container

```bash
docker run -d -p 8080:80 nginx
```

Open browser:

[http://localhost:8080](http://localhost:8080)

---

# 📌 STEP 15 — Create a Dockerfile

```bash
nano Dockerfile
```

Paste:

```Dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html
```

---

# 📌 STEP 16 — Build Docker Image

```bash
docker build -t yourusername/myapp .
```

---

# 📌 STEP 17 — Tag Image

```bash
docker tag yourusername/myapp yourusername/myapp:latest
```

---

# 📌 STEP 18 — Push Image to Docker Hub

```bash
docker push yourusername/myapp:latest
```

---

# 📌 STEP 19 — Verify on Docker Hub

Go to your Docker Hub dashboard to confirm your image is uploaded.

---

# ⚠️ Common Mistakes to Avoid

* Not logging out after adding user to docker group
* Using wrong Ubuntu version codename
* Not tagging image before push
* Typo in Dockerfile
* Not logged in before pushing

---

# 🚀 Summary

1. Install Docker
2. Start Docker service
3. Enable non-root usage
4. Create Docker Hub account
5. Login via CLI
6. Pull and run images
7. Build your own image
8. Push to Docker Hub

---

You're now fully set up with Docker and Docker Hub 🎉
