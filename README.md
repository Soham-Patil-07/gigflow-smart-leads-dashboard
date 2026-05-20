# Smart Leads Dashboard (MERN Stack with TypeScript)

A production-ready full-stack Lead Management Dashboard built using clean architecture, robust state management, and real-world engineering practices.

## 🚀 Live Deployments
* **Frontend Dashboard (Vercel):** [Insert Your Vercel Live URL Here]
* **Backend API Gateway (Render):** `https://gigflow-backend-ctno.onrender.com`

---

## 🛠️ Production Tech Stack
* **Frontend:** React.js, TypeScript, TailwindCSS, Axios
* **Backend:** Node.js, Express.js, TypeScript, JWT (jsonwebtoken), Bcryptjs
* **Database:** MongoDB Atlas + Mongoose ODM
* **Containerization:** Docker & Docker Compose

---

## ✨ Core Application Features
1. **JWT Authentication & RBAC:** Secure token-based user workflows supporting **Admin** and **Sales** tier roles. 
   * *Admin Tier:* Full CRUD permissions + exclusive clearance to execute data removals (`DELETE`).
   * *Sales Tier:* Read and write access (`GET`, `POST`, `PUT`) without delete authorization.
2. **Advanced Multi-Filter & Search Engine:** Combines status queries, source metrics, and a fully **Debounced Search** engine to maximize pipeline search performance.
3. **Server-Driven Pagination:** Optimized via MongoDB native `skip` and `limit` cursors delivering 10 records per page accompanied by dynamic meta footers.
4. **CSV Export Engine:** Generates and processes valid structured spreadsheets of current lead vectors client-side.

---

## 📂 API Reference Documentation

### 🔑 Authentication Routes (`/api/auth`)
* `POST /api/auth/register` - Create a new user identifier (`Admin` or `Sales`).
* `POST /api/auth/login` - Authenticate account and retrieve a custom signed 24h JWT.

### 📋 Leads Dashboard Routes (`/api/leads`) — *Requires Authorization Header*
* `GET /api/leads` - Fetch page-paginated, filtered leads collection.
* `GET /api/leads/:id` - Inspect metadata of a single distinct pipeline lead.
* `POST /api/leads` - Appends a fresh record instance to the cloud database.
* `PUT /api/leads/:id` - Updates specific fields on an existing lead object.
* `DELETE /api/leads/:id` - **(Admin Only)** Erases the target record permanently.

---

## ⚙️ Execution & Setup Instructions

### Option A: Local Terminal Setup

#### 1. Configure Environmental Variables
Add `.env` configurations inside both respective runtime directories matching the structure presented in their `.env.example` twins.

#### 2. Run Backend Environment
```bash
cd backend
npm install
npm run build
npm start