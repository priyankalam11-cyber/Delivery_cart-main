# Smart Logistics Management System

A full-stack logistics management system for managing orders, riders, deliveries, proof of delivery, disputes, and analytics.

## Tech Stack

- React + Vite
- Node.js + Express
- PostgreSQL
- JWT Authentication

## Features

- Role-based login
- Create and track orders
- Assign riders manually or automatically
- Update delivery status
- Upload and verify Proof of Delivery (POD)
- Manage disputes
- Audit logs
- Delivery and rider analytics
- Daily reports

## Project Structure

```text
project_1/
├── backend/
├── frontend/
└── database/
```

## Setup

### Requirements

- Node.js 18+
- PostgreSQL 14+

### 1. Create the Database

```sql
CREATE DATABASE logistics_db;
```

Run the database scripts:

```bash
psql -U postgres -d logistics_db -f database/schema.sql
psql -U postgres -d logistics_db -f database/seed.sql
```

### 2. Setup Backend

```bash
cd backend
copy .env.example .env
npm install
```

Update `.env` with your PostgreSQL details if needed.

### 3. Setup Frontend

```bash
cd frontend
npm install
```

### 4. Run the Project

Start the backend:

```bash
cd backend
npm run dev
```

Start the frontend in another terminal:

```bash
cd frontend
npm run dev
```

**Frontend:** `http://localhost:5173`  
**Backend:** `http://localhost:5000`

## Main API Endpoints

| Module | Method | Endpoint |
|---|---|---|
| Login | POST | `/api/auth/login` |
| Orders | GET | `/api/orders` |
| Orders | POST | `/api/orders` |
| Track Order | GET | `/api/orders/:id/track` |
| Update Order | PATCH | `/api/orders/:id/status` |
| Assign Rider | POST | `/api/assignments/:orderId/manual` |
| Auto Assign Rider | POST | `/api/assignments/:orderId/auto` |
| Riders | GET | `/api/riders` |
| Upload POD | POST | `/api/pod/:orderId` |
| Verify POD | GET | `/api/pod/:orderId` |
| Disputes | GET | `/api/disputes` |
| Analytics | GET | `/api/analytics` |

## Sample Users

Sample users are included in the seed data.

**Password:** `password123`

- Priya Mehta
- Rohan Yadav
- Ananya Verma
- Neha Singh
- Vikram Iyer

## Notes

- POD files are stored locally in `backend/uploads` during development.
- AWS S3 can be added later by replacing the current file storage implementation.
