# Miska Pho - Fullstack Restaurant Management System

[![MiskaPho CI/CD](https://github.com/vkhanht1/Full-Stack-Restaurant-Management-System/actions/workflows/cicd-pipeline.yml/badge.svg)](https://github.com/vkhanht1/Full-Stack-Restaurant-Management-System/actions)

Miska Pho is a comprehensive e-commerce and enterprise management solution tailored for a Vietnamese restaurant. This project demonstrates modern full-stack development using the MERN ecosystem, now fully containerized and integrated with automated delivery pipelines.

It features real-time menu synchronization, secure end-to-end online payments, and a robust administrative control panel.

---

## 🏗️ System Architecture

The project is architected as a **Monorepo**, cleanly decoupled into three specialized modules:

*   **`/frontend`**: The customer-facing single-page application (SPA). Allows users to browse dishes, manage a dynamic shopping cart, and book tables.
*   **`/admin`**: A secure portal for restaurant owners and staff to manage real-time orders, track inventory, and handle table reservations.
*   **`/backend`**: The central nervous system. A RESTful API handling stateful operations, JWT authentication, Stripe payment webhooks, and database mutations.

---

## 🌐 Live Demo Links

*   **Customer Web App:** [https://miska-pho-frontend.vercel.app/](https://miska-pho-frontend.vercel.app/)
*   **Administrative Panel:** [https://miska-pho-admin.vercel.app/](https://miska-pho-admin.vercel.app/)

---

## 🐳 Local Development via Docker

This ecosystem is fully dockerized. To spin up the entire application infrastructure locally—including Frontend, Admin Dashboard, and the Backend API Server—without setting up local runtimes, execute:

```bash
# Clone and navigate to root, then run:
docker-compose up --build

```

### Local Endpoint Map:

* **Customer Application:** `http://localhost:3000`
* **Admin Dashboard:** `http://localhost:3001`
* **Backend API Base:** `http://localhost:5000`

---

## ⚙️ CI/CD & DevOps Integration

The repository runs an automated **DevOps Pipeline** powered by **GitHub Actions** upon every push to the `main` branch:

1. **Continuous Integration (CI):** Automates dependency installation, workspace validation, and static compilation checks.
2. **Continuous Delivery (CD):** Leverages multi-registry targets to build, tag, and publish highly optimized Docker images concurrently to:
* **Docker Hub Registry**
* **GitHub Container Registry (GHCR)**



---

## ⚡ Key Technical Features

### 1. Secure Identity & Access Management (IAM)

* Stateless authentication implemented via **JSON Web Tokens (JWT)** secured in HTTP-only context.
* **Role-Based Access Control (RBAC)** mechanisms separating Customer actions from Admin escalation paths.
* Cryptographic password protection using multi-round **bcryptjs** salting.

### 2. Enterprise Payment Gateway

* Full **Stripe API** integration supporting atomic credit card transactions.
* Asynchronous **Webhook-ready logic** for secure, server-side payment verification and state durability.
* Hybrid checkout supporting both Online Payment settlement and Cash on Delivery (COD) workflows.

### 3. Cloud-Native Asset Pipelines

* Dynamic media abstraction and asset optimization handled via **Cloudinary CDN**.
* Automated multi-part image uploads for menu systems utilizing **Multer** stream middleware.

### 4. Smart Reservation Engine

* Deterministic booking logic structured to calculate and prevent overlapping time/table reservations.
* Reactive state flow allowing explicit Admin approval, modification, or cancellation.

---

## 🛠️ Technology Stack Summary

* **Frontend Ecosystem:** React.js, Tailwind CSS, React Router DOM, Axios Client.
* **Backend Runtime:** Node.js, Express.js REST Framework.
* **Database Infrastructure:** MongoDB Atlas Cloud Instance cloud cluster via Mongoose Object Data Modeling (ODM).
* **Infrastructure & Deployment:** Docker, Docker Compose, GitHub Actions (CI/CD), Vercel.
