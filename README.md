# Civic Issue Reporter — Setup Guide

## Project Structure

```text
Civic-Issue-Reporter/
├── frontend/
├── backend/
└── ai-model/
```

## 1. Database

The project uses **Aiven MySQL 8.4**.

Database configuration is stored in `backend/.env`:

```env
DB_HOST=<AIVEN_HOST>
DB_PORT=16633
DB_USER=avnadmin
DB_PASSWORD=<AIVEN_PASSWORD>
DB_NAME=defaultdb
```

SSL is enabled using:

```text
backend/certs/ca.pem
```

The database contains:

```text
mandals
users
admins
issues
issue_images
issue_links
issue_status_history
ratings
counters
```

The local MySQL database was migrated to Aiven, including the existing application data.

**Never commit `backend/.env` to GitHub.**

---

## 2. Backend Setup

Open a terminal in the project folder:

```cmd
cd backend
```

Install dependencies:

```cmd
npm install
```

Start the backend:

```cmd
npm run dev
```

The backend runs on:

```text
http://localhost:5000
```

---

## 3. Frontend Setup

Open another terminal:

```cmd
cd frontend
```

Install dependencies:

```cmd
npm install
```

Start the frontend:

```cmd
npm run dev
```

The frontend normally runs on:

```text
http://localhost:5173
```

---

## 4. AI Model

The AI service is located in:

```text
ai-model/
```

It provides civic-issue image classification to the backend.

---

## 5. Local Development

Run the three services separately:

```text
Frontend  → localhost:5173
Backend   → localhost:5000
AI Model  → configured AI service port
```

Make sure the required `.env` configuration is present before starting the backend.
