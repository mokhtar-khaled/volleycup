# 🏐 VolleyCup 4.0

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Status](https://img.shields.io/badge/status-actively%20upgrading-orange?style=for-the-badge)](https://github.com/mokhtar-khaled/VolleyCup-4.0)

> 🏫 **Real Academic Project** · 🏐 **Real Tournament** · 🇹🇳 **ENSI, Tunisia**

**VolleyCup 4.0** is the official web platform for the intercollegiate volleyball tournament organized every year at ENSI (École Nationale des Sciences de l'Informatique). Built by a team of 3 students, it handles the full tournament lifecycle — from team registration and scheduling to results display and team management. This is not a mockup: it was actively used by real teams participating in the 2026 edition.

The project is currently being upgraded from a PHP/MySQL stack to a modern full-stack architecture with Node.js, React, and an AI tournament assistant.

---

## 📸 Platform Overview

### 🏠 Home — Event Landing Page
A dynamic landing page featuring event highlights, a media gallery, and organizer profiles. Built to generate excitement and drive team registrations.

### 📅 Schedule — Tournament Day Timeline
A structured timeline page covering the full tournament day — from check-in to the closing celebration — with match slots and venue details.

### 📋 Register — Team Registration
A multi-field registration form with live client-side validation, optional team photo upload, and server-side persistence via PHP and MySQL. Includes a confirmation page with full registration details and a cancellation flow.

### 👥 Teams — Registered Teams Directory
A dynamic page loading registered teams directly from the database, featuring both featured/seeded teams and all submitted registrations.

---

## ✨ Current Features

- **Responsive 4-page website** — Home, Schedule, Register, Teams — works across all screen sizes
- **Full registration pipeline** — client-side validation → server-side validation → MySQL persistence via PDO
- **Optional team photo upload** — with file type and size validation
- **Repository pattern** — clean separation between data access and business logic in PHP
- **Confirmation & cancellation flow** — teams receive a full summary and can cancel their registration
- **Dynamic teams directory** — registered teams loaded in real time from the database
- **Tournament timeline** — full day schedule from check-in to closing ceremony

---

## 🛠️ Current Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Backend | PHP (Native, no frameworks) |
| Database | MySQL with PDO prepared statements |
| Architecture | Repository Pattern |
| Environment | XAMPP (Apache + MySQL) |

---

## 🚀 Getting Started

### Prerequisites
- [XAMPP](https://www.apachefriends.org/) installed and running

### Setup

1. Clone the repository into your XAMPP `htdocs` directory:
   ```bash
   git clone https://github.com/mokhtar-khaled/VolleyCup-4.0.git
   cd VolleyCup-4.0
   ```
2. Start **Apache** and **MySQL** from the XAMPP Control Panel
3. Open **phpMyAdmin** at `http://localhost/phpmyadmin`
4. Create a database named `volleycup4` and import `database/volleycup4_setup.sql`
5. Open the app at `http://localhost/VolleyCup-4.0/home.html`

---

## 🗂️ Project Structure

```
VolleyCup-4.0/
├── home.html                        ← Landing page (highlights, gallery, organizers)
├── schedule.html                    ← Tournament day timeline
├── register.html                    ← Team registration form
├── success.php                      ← Confirmation + cancellation page
├── teams.php                        ← Dynamic teams directory
├── submit_registration.php          ← Form handler
├── config/
│   └── database.php                 ← PDO database connection
├── database/
│   └── volleycup4_setup.sql         ← Schema + seed data
├── includes/
│   ├── Registration.php             ← Registration model
│   └── RegistrationRepository.php   ← Data access layer (PDO)
├── src/
│   ├── assets/
│   │   ├── images/
│   │   └── video/
│   └── js/
│       ├── home.js
│       ├── register.js
│       └── teams.js
├── style.css
└── schedule.css
```

---

## 🗺️ Upgrade Roadmap

This project is actively being upgraded to a modern full-stack architecture. Progress is tracked below.

---

### Phase 1 — Node.js + Express REST API &nbsp; `🔄 In Progress`

Replacing the PHP backend with a clean Node.js + Express API.

- [ ] Scaffold Node.js + Express server in `/backend`
- [ ] `GET /api/teams` — return all registered teams as JSON
- [ ] `POST /api/register` — validate and persist new registrations
- [ ] `DELETE /api/register/:id` — handle cancellations
- [ ] Connect to MySQL using the `mysql2` package
- [ ] Secure all credentials with `.env` + `dotenv`
- [ ] Test all routes with Thunder Client

**Stack added:** `Node.js` `Express` `mysql2` `dotenv`

---

### Phase 2 — Migrate Frontend to Node API &nbsp; `📋 Planned`

Disconnecting the HTML frontend from PHP and wiring it to the new REST API.

- [ ] Replace PHP `form action` submissions with `fetch()` calls
- [ ] Convert `teams.php` → `teams.html` with dynamic JS rendering
- [ ] Handle CORS configuration between frontend and API
- [ ] Remove all PHP dependencies from the frontend layer

**Stack added:** `Fetch API` `CORS` `async/await`

---

### Phase 3 — AI Tournament Assistant &nbsp; `📋 Planned`

Embedding an AI chatbot that knows the tournament inside out.

- [ ] Integrate Groq API (Llama 3.3 70b) as the AI engine
- [ ] Build a system prompt with live tournament data (teams, schedule, rules)
- [ ] Pull real registered team data from the Node API into AI context
- [ ] Add a floating chat widget across all pages
- [ ] Example queries: *"Who is playing at 14:00?"*, *"How many teams are registered?"*

**Stack added:** `Groq API` `Llama 3.3 70b` `Prompt Engineering`

---

### Phase 4 — React Frontend &nbsp; `📋 Planned`

Rebuilding the frontend as a modern React application.

- [ ] Scaffold with Vite + React
- [ ] Rebuild all pages as React components: Home, Schedule, Teams, Register
- [ ] Add React Router for client-side navigation
- [ ] Connect all components to the Node.js REST API via Axios
- [ ] Migrate styles to a component-scoped CSS system

**Stack added:** `React` `Vite` `React Router` `Axios`

---

### Phase 5 — Deploy to Production &nbsp; `📋 Planned`

Making the platform publicly accessible with a live URL.

- [ ] Deploy React frontend to **Vercel**
- [ ] Deploy Node.js backend + MySQL to **Railway**
- [ ] Set up environment variables in production
- [ ] Add live demo link to README

**Stack added:** `Vercel` `Railway` `CI/CD`

---

## 🎓 Academic Context

This project was developed as part of coursework at **ENSI (École Nationale des Sciences de l'Informatique)**, Tunisia. Unlike a purely academic simulation, VolleyCup runs against a real tournament that ENSI organizes every year — meaning the registration data, team listings, and schedule reflect actual participants. The upgrade roadmap reflects independent learning beyond the coursework requirements, driven by a goal to master modern full-stack development.

---

## 👥 Team

Developed by a team of 3 ENSI students.

**Mohamed Mokhtar Khaled**
- GitHub: [@mokhtar-khaled](https://github.com/mokhtar-khaled)
- LinkedIn: [mohamed-mokhtar-khaled](https://linkedin.com/in/mohamed-mokhtar-khaled)

---

## 📄 License

MIT — free to use and modify for educational purposes.