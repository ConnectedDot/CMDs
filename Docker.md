# Docker + Azure Container Deployment Quick Guide

## 1. What is Docker?

Docker allows you to package your application together with:

* Node.js runtime
* Dependencies
* Environment
* Server configuration

into a single portable unit called a:

```text
Container
```

This means:

```text
"It works on my machine"
```

becomes:

```text
"It works everywhere"
```

---

# 2. Core Docker Concepts

| Concept          | Meaning                          |
| ---------------- | -------------------------------- |
| Dockerfile       | Blueprint for building container |
| Image            | Built application snapshot       |
| Container        | Running instance of image        |
| Docker Hub / ACR | Registry to store images         |
| Port Mapping     | Connect local/server ports       |
| Volume           | Persistent storage               |
| Docker Compose   | Run multiple services together   |

---

# 3. Docker Installation

## Windows

Install:

* Docker Desktop
* WSL2

Verify:

```bash
docker --version
```

Check running:

```bash
docker ps
```

---

# 4. Typical Docker Workflow

```text
Code App
   ↓
Create Dockerfile
   ↓
Build Image
   ↓
Run Container
   ↓
Push Image to Registry
   ↓
Deploy to Cloud
```

---

# 5. Basic Docker Commands

## Build Image

```bash
docker build -t myapp .
```

Explanation:

| Part         | Meaning        |
| ------------ | -------------- |
| docker build | Build image    |
| -t           | Tag/name       |
| myapp        | Image name     |
| .            | Current folder |

---

## Run Container

```bash
docker run -p 8080:8080 myapp
```

Format:

```text
HOST_PORT:CONTAINER_PORT
```

Example:

```text
localhost:8080 → container:8080
```

---

## View Running Containers

```bash
docker ps
```

---

## Stop Container

```bash
docker stop CONTAINER_ID
```

---

## Remove Container

```bash
docker rm CONTAINER_ID
```

---

## View Images

```bash
docker images
```

---

## Remove Image

```bash
docker rmi IMAGE_NAME
```

---

# 6. Basic Node.js Dockerfile

## Express API

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install --omit=dev

COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
```

---

# 7. React Frontend Dockerfile

## Standalone React App

```dockerfile
FROM oven/bun:1-alpine AS build

WORKDIR /app

COPY package.json bun.lockb* ./

RUN bun install

COPY . .

RUN bun run build

FROM nginx:1.27-alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

# 8. Why React Uses Nginx

React production build becomes:

```text
Static HTML/CSS/JS files
```

Nginx serves them efficiently.

---

# 9. Express + React Together

If React build is inside:

```text
/public
```

then use only:

```text
Node.js Dockerfile
```

because Express serves frontend.

---

# 10. Environment Variables

## Local

```env
PORT=8080
MONGO_URI=...
JWT_SECRET=...
```

---

## Run With Env

```bash
docker run --env-file ./config/.env -p 8080:8080 myapp
```

---

# 11. Docker Ignore

Create:

```text
.dockerignore
```

Example:

```text
node_modules
.git
.env
dist
build
```

Prevents huge image sizes.

---

# 12. Azure Container Registry (ACR)

Azure registry stores Docker images.

Example:

```text
lbaappscr.azurecr.io
```

---

# 13. Install Azure CLI

Verify:

```bash
az --version
```

Login:

```bash
az login
```

---

# 14. Login to Azure Container Registry

```bash
az acr login --name lbaappscr
```

---

# 15. Tag Docker Image

```bash
docker tag lbanblogapi lbaappscr.azurecr.io/lbanblogapi:latest
```

Format:

```text
LOCAL_IMAGE REGISTRY/IMAGE:TAG
```

---

# 16. Push Image

```bash
docker push lbaappscr.azurecr.io/lbanblogapi:latest
```

---

# 17. Azure App Service Container Setup

## Deployment Center

Select:

```text
Container Registry
```

Then:

| Setting  | Value       |
| -------- | ----------- |
| Registry | lbaappscr   |
| Image    | lbanblogapi |
| Tag      | latest      |

---

# 18. Important Azure Settings

## App Service → Environment Variables

Add:

```text
WEBSITES_PORT=8080
PORT=8080
NODE_ENV=production
```

---

# 19. Important Express Listen Setup

Always use:

```js
const PORT = process.env.PORT || process.env.WEBSITES_PORT || 8080;

app.listen(PORT, "0.0.0.0", () => {
  console.log(`Server running on ${PORT}`);
});
```

Avoid:

```js
app.listen(5000)
```

or:

```js
app.listen(PORT, "localhost")
```

---

# 20. Common Docker Errors

## Port Already Allocated

```text
Bind for 0.0.0.0 failed
```

Fix:

```bash
docker ps
docker stop CONTAINER_ID
```

or use another port:

```bash
docker run -p 8081:8080 app
```

---

## Env File Missing

```text
docker: open .env: no such file
```

Fix:

```bash
docker run --env-file ./config/.env ...
```

---

## Azure Warmup Timeout

```text
Container did not start within expected time
```

Usually:

* wrong port
* app crashing
* missing env vars
* server listening on localhost

---

# 21. Docker Compose

Used for multi-service apps.

Example:

```yaml
version: "3"

services:
  api:
    build: .
    ports:
      - "8080:8080"

  mongodb:
    image: mongo
```

Run:

```bash
docker compose up
```

---

# 22. Production Best Practices

## Avoid

```yaml
volumes:
  - .:/app
```

in production.

---

## Avoid

```text
nodemon
```

in production.

Use:

```text
node server.js
```

---

## Use Multi-stage Builds

Reduces image size.

---

## Never Push `.env`

Use:

```text
Azure Environment Variables
Azure Key Vault
GitHub Secrets
```

---

# 23. Suggested Architecture

## Frontend

```text
React + Nginx Container
```

## Backend

```text
Express API Container
```

## Database

```text
MongoDB Atlas / Azure DB
```

## Deployment

```text
Azure App Service Containers
```

---

# 24. Final Deployment Flow

```text
Write App
   ↓
Create Dockerfile
   ↓
docker build
   ↓
docker run
   ↓
Test locally
   ↓
az login
   ↓
az acr login
   ↓
docker tag
   ↓
docker push
   ↓
Azure App Service pulls image
   ↓
Production Live
```












Yes. Set up **GitHub Actions CI/CD** so every push builds and deploys the Docker image automatically.

## 1. Add GitHub Secrets

In GitHub repo:

```text
Settings → Secrets and variables → Actions → New repository secret
```

Add these:

```text
ACR_LOGIN_SERVER = your_acr_login_server
ACR_USERNAME = your_acr_username
ACR_PASSWORD = your_acr_password
AZURE_WEBAPP_NAME = your_azure_webapp_name
AZURE_RESOURCE_GROUP = your_azure_resource_group
```

Get ACR username/password from:

```text
Azure Portal → Container Registry → lbaappscr → Access keys
```

Enable **Admin user** if needed.

---

## 2. Create workflow file

Create:

```text
.github/workflows/deploy-container.yml
```

Paste:

```yaml
name: Build and Deploy Docker Image

on:
  push:
    branches:
      - main

env:
  IMAGE_NAME: lbanblogapi

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout source code
        uses: actions/checkout@v4

      - name: Login to Azure Container Registry
        uses: docker/login-action@v3
        with:
          registry: ${{ secrets.ACR_LOGIN_SERVER }}
          username: ${{ secrets.ACR_USERNAME }}
          password: ${{ secrets.ACR_PASSWORD }}

      - name: Build Docker image
        run: |
          docker build -t ${{ secrets.ACR_LOGIN_SERVER }}/${{ env.IMAGE_NAME }}:latest .

      - name: Push Docker image
        run: |
          docker push ${{ secrets.ACR_LOGIN_SERVER }}/${{ env.IMAGE_NAME }}:latest

      - name: Restart Azure App Service
        uses: azure/webapps-deploy@v3
        with:
          app-name: ${{ secrets.AZURE_WEBAPP_NAME }}
          images: ${{ secrets.ACR_LOGIN_SERVER }}/${{ env.IMAGE_NAME }}:latest
```

## 3. Commit and push

```bash
git add .
git commit -m "Setup Docker CI/CD deployment"
git push origin main
```

## 4. Final flow after this

Once setup is done:

```text
Code change
   ↓
git push
   ↓
GitHub Actions builds Docker image
   ↓
Pushes image to ACR
   ↓
Azure App Service updates container
```

After this, you won’t need to manually run `docker build`, `docker tag`, or `docker push` locally.
