# Skill Hub - Premium MERN Stack LMS

A complete, production-ready Skill Hub Learning Management System (LMS) built with the MERN Stack.

## Tech Stack
- **Frontend**: React 19, Vite, Redux Toolkit, React Router, Recharts, Framer Motion, Tailwind CSS, Lucide Icons, React Hot Toast
- **Backend**: Node.js, Express.js, MongoDB (Mongoose), Socket.io (Real-time notifications), bcrypt, JSON Web Token (JWT), Multer
- **Integrations**: Stripe checkout mock system, Cloudinary API structures

---

## Workspace Setup & Folder Structure

We recommend setting `/Users/adityashrama/.gemini/antigravity/scratch/skill-hub-lms` as your active IDE workspace.

```
skill-hub-lms/
├── docker-compose.yml
├── Dockerfile.backend
├── Dockerfile.frontend
├── README.md
├── backend/
│   ├── controllers/        # Auth, Courses, Enrollments, Quizzes, Payments...
│   ├── models/             # Mongoose Schemas (Users, Courses, Orders, Reviews...)
│   ├── routes/             # Express Endpoint routers
│   ├── middlewares/        # JWT auth protectors, role checks, uploads, error handling
│   ├── sockets/            # Socket.io notification broker mapping
│   ├── seed.js             # Seeding script (Generates 100 students, 20 instructors, 50 courses...)
│   └── server.js
└── frontend/
    ├── src/
    │   ├── context/        # Dark/Light Mode Theme Context
    │   ├── redux/          # Redux Store, slices (auth, courses, cart...)
    │   ├── hooks/          # Socket.io real-time listener hook
    │   └── pages/          # Home, Courses, Classroom, Dashboards (Student/Instructor/Admin)
```

---

## Local Development Instructions

### 1. Database & Environment Variables
Confirm that MongoDB is running locally on your machine at `mongodb://localhost:27017/skillhub`, or update the MONGODB_URI in `backend/.env` to point to a cloud Atlas instance.

Active configuration files have already been initialized under:
- `backend/.env`

### 2. Install Dependencies

**Start the Backend:**
```bash
cd backend
npm install
```

**Start the Frontend:**
```bash
cd ../frontend
npm install
```

### 3. Seed Database Content
Run the database seeder to instantly populate the application with 100 students, 20 instructors, 50 courses containing 500 lessons, and historical sales trends spanning 6 months (to show rich analytics graphs immediately!):
```bash
cd ../backend
npm run seed
```

### 4. Launch Servers

**Run Express Backend Server (runs on Port 5001):**
```bash
npm run dev
```

**Run React Vite Frontend Dev Server (runs on Port 5173):**
```bash
cd ../frontend
npm run dev
```

Visit the application at: `http://localhost:5173`

---

## Production / Docker Setup

You can containerize and spin up the complete ecosystem (DB + Server + Nginx Web) using Docker Compose:
```bash
docker-compose up --build
```
Once initialized, visit the portal at: `http://localhost`.

---

## Seed Login Credentials Checklist
You can log in as any of these pre-seeded roles to review customized dashboards immediately:

- **Platform Admin Dashboard:**
  - **Email:** `admin@skillhub.com`
  - **Password:** `password`

- **Instructor Dashboard (Wizard, Recharts):**
  - **Email:** `instructor1@skillhub.com` (up to `instructor20@skillhub.com`)
  - **Password:** `password`

- **Student Dashboard (Confetti, Netflix-Player, Streaks):**
  - **Email:** `student1@skillhub.com` (up to `student100@skillhub.com`)
  - **Password:** `password`
