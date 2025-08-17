# 🚀 React + Vite + Docker

[![React](https://img.shields.io/badge/React-18-blue?logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5-purple?logo=vite)](https://vitejs.dev/)
[![Docker](https://img.shields.io/badge/Docker-ready-blue?logo=docker)](https://www.docker.com/)

A lightweight **React application** bootstrapped with **Vite** and containerized using **Docker**.  
This project shows how to run a modern frontend app inside a container for easy development and deployment.

---

## 📂 Project Overview

- **Frontend:** React + Vite  
- **Containerization:** Docker (Node.js 18 base image)  
- **Entry Point:** `index.html` + `src/main.jsx`  
- **Port:** 5173 (default Vite dev server)  

---

## 🐳 Running in Docker

### 1️⃣ Build the image
```bash
docker build -t react-vite-docker .
2️⃣ Run the container
bash
Copy
Edit
docker run -p 5173:5173 react-vite-docker
Now open 👉 http://localhost:5173

⚡ Running Locally (without Docker)
bash
Copy
Edit
npm install
npm run dev
App will be live at http://localhost:5173

📦 Dockerfile Breakdown
dockerfile
Copy
Edit
FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host"]
Uses Node.js 18 official image.

Installs dependencies from package.json.

Exposes port 5173 for Vite.

Runs the dev server with npm run dev.
