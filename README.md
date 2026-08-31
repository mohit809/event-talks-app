# 🕒 Schedular - Smart Appointment & Event Management Platform

A modern, secure, and responsive web application designed for scheduling appointments, organizing event schedules, managing conference talks, and tracking sessions in real-time.

---

## 🚀 Overview

**Schedular** is an appointment and schedule management platform featuring **mandatory authentication gating**, **cryptographic security**, **calendar & clock appointment pickers**, and **instant .ics calendar export**. 

When users open the application, they are greeted with an **Authentication Gateway** (Sign In / Sign Up). Once logged in, they are seamlessly transferred to the dashboard where they can schedule appointments with interactive date and time pickers, search sessions in real time, filter by room and status, and export items directly to their calendar.

---

## ✨ Key Features & Functionality

### 1. 🕒 Clock Branding & Live Clock
- **Modern Clock Identity**: Vibrant gradient icon badge with crisp vector clock SVG.
- **Live Ticking Clock**: Real-time header badge showing the current day, date, and ticking time.

### 2. 🔐 Mandatory Authentication Gate & Account Flow
- **Access Control on Launch**: Unauthenticated visitors are presented with a modern login and registration portal before gaining access to the dashboard.
- **Seamless Session Transfer**: Once authenticated, the user is immediately granted access to the interactive schedule and appointment controls.
- **Persistent User Session**: Manages active user state with customized user avatar, name badge, and one-click Sign Out.
- **Standalone Auth Page**: Dedicated [`login.html`](login.html) with auto-redirect if already signed in.

### 3. 🛡️ Security & Anti-Injection Architecture
- **Web Crypto SHA-256 Password Hashing**: Passwords are never stored in plain text. Each user is provisioned with a cryptographic salt, and password verification is computed using the browser's native `crypto.subtle.digest('SHA-256', ...)`.
- **SQL & HTML Injection Prevention**: All text inputs (titles, speakers, descriptions, search queries) pass through strict sanitization routines to strip `<script>`, harmful tags, and malicious injection payloads.
- **Live Password Strength Meter**: Dynamic visual indicator evaluating password length, uppercase/lowercase casing, numbers, and special characters.
- **Secure Tokenized Sessions**: Session tokens generated with cryptographic timestamps and stored in browser local storage.

### 4. 📅 Date & Time Picker (Appointment Scheduling)
- **Interactive Calendar Date Picker**: Select appointment dates with constraints preventing past dates.
- **Start & End Time Controls**: Dedicated appointment time picker inputs (`<input type="time">`) for start and end intervals.
- **Category & Status Tracking**: Classify events (Conference Talk, 1-on-1 Meeting, Team Sync, Workshop, Keynote, Project Review) and mark them as *Upcoming*, *In Progress*, or *Completed*.
- **Location & Link Support**: Assign physical venues (e.g. *Hall A*, *Room 302*) or virtual links (*Zoom*, *Google Meet*).

### 5. 📆 Add to Calendar (.ics Export)
- Generate and download standard **iCalendar (`.ics`)** files for any scheduled appointment with one click, enabling instant import into **Google Calendar, Apple Calendar, and Microsoft Outlook**.

### 6. 🔍 Real-Time Search & Multi-Criteria Filtering
- Instant multi-field search across titles, hosts, speakers, locations, categories, and descriptions.
- Filter by **Date** (Today, Upcoming, All Dates), **Room / Location**, and **Status**.
- Dynamic room discovery auto-populating from scheduled items.

### 7. 📊 Live Statistics Dashboard
- Real-time counters showing **Total Appointments**, **Scheduled Today**, and **Active / Upcoming** sessions.

---

## 🛠️ Technology Stack & APIs

| Category | Technology / Specification | Purpose & Role |
| :--- | :--- | :--- |
| **Security & Cryptography** | **Web Crypto API (SubtleCrypto)** | Client-side SHA-256 hashing with salt for credentials |
| **Frontend Markup** | **HTML5** | Semantic structure, date/time pickers, modal dialogs |
| **Styling & Design** | **CSS3** | CSS variables, Flexbox, Grid, Glassmorphism, animations |
| **Client Scripting** | **Vanilla JavaScript (ES6+)** | State management, DOM manipulation, async storage |
| **Data Format** | **JSON** ([`talks.json`](talks.json)) | Default seeded session data |
| **Calendar Standard** | **iCalendar (.ics / RFC 5545)** | Cross-platform calendar file generation via Blob API |
| **Data Persistence** | **Web Storage API (LocalStorage)** | Multi-user database and appointment storage |

---

## 🧰 Development Tools & Workflow

- **Google Antigravity**: Agentic AI pair programming environment for scaffolding, code generation, refactoring, and security enhancements.
- **Git & GitHub CLI (`gh`)**: Distributed version control and automated GitHub repository synchronization.
- **Code-OSS / Linux Cloud Shell**: Cloud-based execution, linting, and development workspace.

---

## 📂 Project Structure

```text
event-talks-app/
├── index.html          # Main application dashboard, Auth Gate & appointment scheduler
├── login.html          # Standalone secure authentication portal (Sign In / Sign Up)
├── talks.json          # Default seeded appointment & talk schedule data
├── README.md           # Complete project documentation
├── summary_task3.md    # Repository inspection records
└── summary_task4.md    # Development milestone logs
```

---

## 🚀 Getting Started

### Prerequisites
Any modern browser (Google Chrome, Firefox, Microsoft Edge, Safari) supporting the Web Crypto API.

### Running the Project

#### Option 1: Lightweight Local Server (Recommended)
```bash
# Using Python 3
python3 -m http.server 8000

# Or using Node.js npx serve
npx serve .
```
Navigate to `http://localhost:8000` in your web browser.

#### Option 2: Direct File Launch
Simply open [`index.html`](index.html) in your browser:
- On Linux: `xdg-open index.html`
- On macOS: `open index.html`

---

## 🔒 Security Highlights

1. **Client-Side SHA-256 Cryptography**: Passwords are never stored in raw text; each account is hashed with unique salts.
2. **Input Sanitization**: Defense against Cross-Site Scripting (XSS) and SQL/HTML injection tokens.
3. **Session Token Expiration & Validation**: Robust authentication checking before allowing interaction with application data.

---

## 📄 License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
