# 📅 Schedular - Event & Task Management App

A modern, responsive, and lightweight web application designed for organizing, managing, and tracking event schedules, conference talks, and task sessions seamlessly.

---

## 🚀 Overview

**Schedular** provides conference attendees, event organizers, and team members with an intuitive dashboard to view scheduled talks, filter sessions by room, search agenda items in real-time, and dynamically add or remove events. The application is built with vanilla web technologies, ensuring zero build overhead, fast loading times, and instant responsiveness across all devices.

---

## ✨ Features & Functionality

### 1. 📋 Interactive Schedule Dashboard
- Displays all scheduled talks and sessions in clean, modern card layouts.
- Cards highlight essential metadata:
  - **Title & Description**
  - **Speaker / Presenter / Assignee**
  - **Location / Room Badge** (e.g., *Hall A*, *Hall B*, *Online*)
  - **Time Slot Badge** (e.g., *09:00 - 10:00*)
  - **Unique Task ID**

### 2. 🔍 Real-Time Search & Filtering
- **Live Search**: Instant multi-attribute search across talk titles, speaker names, room names, and session descriptions.
- **Dynamic Room Filter**: Automatically discovers and aggregates available rooms from existing sessions into a dropdown filter.

### 3. ➕ Session / Task Management
- **Add New Tasks / Talks**: Modal form to add custom talks with title, speaker, room/hall, time slot, and description.
- **Remove Sessions**: In-card delete controls with confirmation prompts to remove outdated or cancelled sessions.

### 4. 💾 Local Storage & Initial Data Fallback
- Persists user additions, modifications, and deletions directly in browser `localStorage`.
- Automatically fetches and bootstraps initial schedule data from [`talks.json`](talks.json) when launched for the first time.

### 5. 🔐 User Authentication & Account State
- **Sign In / Sign Up Modal**: Integrated modal for seamless authentication directly from the dashboard.
- **Standalone Login Page**: Dedicated [`login.html`](login.html) page with smooth tab toggling between Sign In and Sign Up.
- **Session State Management**: Dynamically updates the navigation bar with active user profile badges and one-click Sign Out.

### 6. 📱 Responsive & Accessible UI
- Clean interface powered by modern CSS custom properties (variables), responsive Flexbox, and CSS Grid.
- Polished visual effects including subtle hover transitions, soft shadows, and modal animations.

---

## 🛠️ Technology Stack

| Category | Technology / Specification |
| :--- | :--- |
| **Frontend Markup** | **HTML5** (Semantic structure, modal overlays, accessible form controls) |
| **Styling & Design** | **CSS3** (CSS Variables, Flexbox, Grid layout, Keyframe animations, Responsive design) |
| **Client Scripting** | **Vanilla JavaScript (ES6+)** (DOM API, Async/Await, Fetch API, LocalStorage API) |
| **Data Format** | **JSON** (Structured talk & session definitions) |

---

## 🧰 Tools & Development Workflow

This project was built and managed using modern developer tools and agentic workflows:

- **Google Antigravity**: Agentic AI pair programming environment for scaffolding, rapid feature iteration, refactoring, and documentation.
- **Git & GitHub CLI (`gh`)**: Distributed version control, commit tracking, and seamless GitHub repository creation and synchronization.
- **Linux & Cloud Shell Environment**: Headless execution environment with development and testing utilities.
- **Visual Studio Code / Code-OSS**: Code editing, formatting, and web previewing.

---

## 📂 Project Structure

```text
event-talks-app/
├── index.html          # Main application dashboard, session grid & modals
├── login.html          # Standalone authentication page (Sign In / Sign Up)
├── talks.json          # Default seeded session data for initial launch
├── README.md           # Comprehensive project documentation
├── summary_task3.md    # Repository inspection records
└── summary_task4.md    # Development milestone logs
```

---

## 🚀 Getting Started

No build tools, package managers, or compilers are required. You can run the application directly in any modern browser.

### Prerequisites
- Any modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).

### Quick Launch Options

#### Option A: Direct Browser Launch
Simply open [`index.html`](index.html) in your browser:
- On Linux / macOS:
  ```bash
  xdg-open index.html   # Linux
  open index.html       # macOS
  ```
- Or double-click the `index.html` file in your file explorer.

#### Option B: Using a Lightweight HTTP Server (Recommended)
Using a local server ensures full compatibility with the Fetch API for loading `talks.json`:

```bash
# Using Python 3 built-in server
python3 -m http.server 8000

# Or using Node.js npx serve
npx serve .
```
Then visit `http://localhost:8000` in your browser.

---

## 🗺️ Roadmap & Future Enhancements

- [ ] Connect with a persistent backend database (Firebase / PostgreSQL / REST API).
- [ ] Add calendar export support (`.ics` / Google Calendar integration).
- [ ] Real OAuth2 / JWT authentication integration.
- [ ] Speaker profile cards and attendee bookmarking / favorites list.
- [ ] Dark / Light theme toggle switch.

---

## 📄 License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
