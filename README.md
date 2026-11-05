
# SkillShare – Peer-to-Peer Skill Sharing Platform 🎓🚀

A modern, full-featured MERN stack web application where students and professionals can **teach skills they know** and **learn new skills from peers**. Users can become both teachers and learners in an open, collaborative ecosystem.

---

## 🌟 Key Features

### 1. 16 Complete Application Pages
1. **Home Page**: Hero banner with dual CTAs, live skill search, statistics counters, popular categories, featured skill cards, how-it-works workflow, why-peer-learning benefits, testimonials, and footer.
2. **About Us Page**: Story, mission statement, philosophy of peer learning, core values, community principles & code of conduct.
3. **Explore Skills Page**: Complete discovery hub with keyword search, category filters, skill level filters, teaching mode filters, sort options (newest, rating, title), and pagination.
4. **Skill Details Page**: Deep-dive curriculum view with banner, prerequisites, learning outcomes, availability, teacher summary card, related category skills, and interactive "Request to Learn" modal.
5. **Login Page**: JWT authentication with email & password, error handling, redirect preservation, and **1-click demo login buttons**.
6. **Register Page**: User registration with name, email, password confirmation, preset avatar selection, custom image URL, bio, and desired skills tags.
7. **User Dashboard (Overview)**: Central workspace with total skills taught, sent learning requests, approved connections, incoming teaching applications, and quick-action shortcuts.
8. **Add New Skill Page**: Full form to post a skill with category, difficulty level, teaching mode (Online/Offline/Both), duration, availability, prerequisites, learning outcomes, and banner presets.
9. **My Skills Page**: Owner management page with view preview, edit skill, and safe inline delete confirmation.
10. **Edit Skill Page**: Form to update existing skill parameters, schedule, curriculum, and tags (protected by owner authorization).
11. **My Learning Requests Page**: Sent requests tracker with status filter tabs (All, Pending, Accepted, Completed, Cancelled, Rejected), teacher contact info, and cancel option.
12. **My Teaching Requests Page**: Incoming applications manager where teachers can review student notes, accept requests with custom welcome messages, decline, or mark completed.
13. **User Profile Page**: Public and personal profile showcasing teacher bio, skills offered, skills interested in, completed mentorship sessions, and feedback rating.
14. **Edit Profile Page**: Form to update avatar, bio, location, direct contact handles, and learning goals.
15. **Contact Page**: Interactive inquiry form, direct support hotlines, global headquarters details, and FAQ accordion.
16. **404 Not Found Page**: Polished 404 page with navigation links back to Home and Explore.

---

## 💻 Tech Stack

### Frontend
- **React.js (Vite)**
- **Tailwind CSS** (Soft purple & indigo startup palette)
- **Lucide React** (Modern clean vector iconography)
- **React Router DOM v6** (Nested layout routing & protected route guards)
- **Axios** (With automatic JWT Authorization interceptor)
- **Context API** (`AuthContext` for persistent sessions, `ToastContext` for animated notifications)

### Backend
- **Node.js & Express.js**
- **MongoDB & Mongoose** (With automated in-memory MongoDB fallback out-of-the-box!)
- **JWT (JSON Web Tokens)** for secure stateless sessions
- **bcryptjs** for 10-round salted password hashing
- **CORS & Centralized Error Middleware**

---

## 🔑 Demo Accounts (Pre-Seeded)

The application automatically seeds realistic demo data on initial startup! You can sign in immediately with any of the accounts below:

| Role | Email | Password | Details |
| :--- | :--- | :--- | :--- |
| **Demo User** | `demo@skillshare.com` | `demo1234` | Has active learning & teaching requests, pre-set skills |
| **Web Dev Mentor** | `alex@example.com` | `password123` | Senior Engineer teaching React & Node.js |
| **Photographer** | `sophia@example.com` | `password123` | Natural Light Portrait Director |
| **Language Coach** | `marcus@example.com` | `password123` | Polyglot teaching Spanish & Public Speaking |
| **Culinary Chef** | `elena@example.com` | `password123` | Pastry Chef teaching Sourdough Bread |
| **UI/UX Designer** | `david@example.com` | `password123` | Lead Product Designer teaching Figma |

*You can also register a brand new account with any email anytime.*

---

## 🚀 Getting Started

### 1. Prerequisites
- Node.js (v18+)
- npm (v9+)

### 2. Installation
Both backend and frontend dependencies are already installed in `server/` and `client/`. If starting afresh:
```bash
# In server directory
cd server
npm install

# In client directory
cd ../client
npm install
```

### 3. Running the Application

You can start both backend and frontend concurrently with one command from the project root:
```bash
npm run dev
```

Or start them in separate terminals:

**Backend Server (Port 5000):**
```bash
cd server
npm run dev
```

**Frontend Client (Port 5173):**
```bash
cd client
npm run dev
```

Open your browser at **`http://localhost:5173`**.

---

## 📡 REST API Documentation

### Auth
- `POST /api/auth/register` – Register a new user account
- `POST /api/auth/login` – Login existing user & return JWT token
- `GET /api/auth/me` – Retrieve current authenticated user profile

### Skills
- `GET /api/skills` – Search & filter skills (supports `search`, `category`, `level`, `teachingMode`, `sort`, `page`, `limit`)
- `GET /api/skills/:id` – Fetch single skill with teacher details & related category skills
- `POST /api/skills` – Create new skill (Protected)
- `PUT /api/skills/:id` – Update existing skill (Protected, owner only)
- `DELETE /api/skills/:id` – Delete skill & associated requests (Protected, owner only)

### Learning Requests
- `POST /api/requests` – Send a learning request to a teacher (Protected)
- `GET /api/requests/sent` – View sent learning requests (Protected)
- `GET /api/requests/received` – View incoming teaching requests (Protected)
- `PUT /api/requests/:id/status` – Update request status: `Accepted`, `Rejected`, `Completed`, `Cancelled` (Protected)
- `DELETE /api/requests/:id` – Delete or cancel request (Protected)

### Users
- `GET /api/users/profile` – Fetch current user profile with dashboard counters (Protected)
- `PUT /api/users/profile/:id` – Update profile bio, avatar, skills, and contact info (Protected)
- `GET /api/users/:id` – Public profile of any member with skills taught & statistics
