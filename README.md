# 🕒 Schedular - Smart Appointment & Virtual Meeting Management Platform

A modern, high-security web application designed for scheduling appointments, organizing virtual meetings (**Google Meet**, **Zoom**, **Cisco Webex**), managing conference talks, and tracking sessions in real-time.

---

## 🚀 Overview

**Schedular** is an enterprise-grade appointment and virtual meeting management platform featuring **mandatory authentication gating**, **8-digit dual OTP verification (Email + SMS)**, **10-minute automated meeting reminders**, **cryptographic WebCrypto SHA-256 security**, and **instant .ics calendar export**.

When users open the application, they are greeted with a secure **Authentication Gateway**. After completing account verification via an **8-digit OTP sent to their email and mobile phone**, they gain full access to the dashboard where they can schedule virtual meetings with interactive calendar/time pickers, receive real-time pre-meeting alerts, and track reminder audit logs.

---

## ✨ Key Features & Functionality

### 1. 🕒 Clock Branding & Real-Time Live Clock
- **Modern Clock Identity**: Gradient icon badge with crisp vector clock SVG.
- **Live Ticking Clock**: Real-time navbar badge displaying current date, day, and live ticking clock with a pulsing status dot.

### 2. 🎥 Virtual Meeting Platform Integration
- **Google Meet, Zoom, & Cisco Webex**: Schedule appointments with direct platform link integration.
- **⚡ Secure Link Generator**: Automatically generates authentic, collision-free meeting URLs with passcodes for Zoom, Google Meet, and Webex.
- **One-Click "Join Meeting"**: High-contrast, branded join buttons right on the appointment cards.

### 3. ⏰ 10-Minute Pre-Meeting Automated Reminders
- **Real-Time Reminder Engine**: Continuously compares current time against scheduled meetings.
- **High-Priority Alert Banner**: Prominently highlights upcoming sessions starting within 10 minutes.
- **Audio Chime Alerts**: Plays a gentle audio chime using the browser's native **Web Audio API**.
- **SMS & Email Dispatch Simulation**: Automatically dispatches notification payloads to the user's registered email and mobile phone.
- **Audit Logs & Notification History**: View full history of sent 10-minute reminders in a dedicated modal.

### 4. 🔒 8-Digit Dual OTP Verification (Email & Mobile Phone)
- **Two-Factor Account Creation**: Registration requires Full Name, Email Address, Mobile Phone Number, and Password.
- **8-Digit OTP Generation**: Dispatches separate, cryptographically secure 8-digit OTPs to both the user's **Email** and **Mobile SMS**.
- **Account Verification Status**: Validates both codes before activating the account and granting dashboard access (`emailVerified: true`, `phoneVerified: true`).

### 5. 🛡️ Enterprise-Grade Security & Anti-Injection Architecture
- **Native Web Crypto SHA-256 Hashing**: Passwords are never stored in raw plaintext; each account is salted and hashed using `crypto.subtle.digest('SHA-256', ...)`.
- **SQL & HTML Injection Prevention**: Strict regex sanitizer strips `<script>` tags, dangerous HTML elements, and SQL injection syntax across all form fields and search queries.
- **Live Password Strength Meter**: Real-time evaluation bar testing length, uppercase/lowercase casing, numbers, and special symbols.

### 6. 📅 Interactive Appointment Scheduling
- **Calendar Date Picker**: Select dates with validation preventing past bookings.
- **Start & End Time Controls**: Dedicated `<input type="time">` pickers for start and end intervals.
- **Category & Status Tracking**: Categorize events (*Conference Talk, 1-on-1 Meeting, Team Sync, Workshop, Keynote, Client Demo*) with live statuses (*Upcoming, In Progress, Completed*).

### 7. 📆 Add to Calendar (.ics Export)
- Generate and download standard **iCalendar (`.ics`)** files for any scheduled appointment with one click, enabling instant import into **Google Calendar, Apple Calendar, and Microsoft Outlook**.

### 8. 🔍 Real-Time Search & Multi-Filter Controls
- Filter by **Meeting Type** (Google Meet, Zoom, Webex, In-Person), **Date** (Today, Upcoming, All), and **Status**.
- Search instantly across titles, speakers, room names, and meeting links.

---

## 🛠️ Technology Stack & APIs

| Category | Technology / Specification | Purpose & Role |
| :--- | :--- | :--- |
| **Security & Cryptography** | **Web Crypto API (SubtleCrypto)** | Client-side SHA-256 password hashing with user-specific cryptographic salts |
| **Verification System** | **8-Digit Dual OTP Engine** | Cryptographic random generation for Email and SMS Mobile verification |
| **Audio Notification** | **Web Audio API** | Real-time audio chime sound synthesis for 10-minute meeting reminders |
| **Frontend Markup** | **HTML5** | Semantic structure, date/time pickers, modal dialogs, accessible forms |
| **Styling & Design** | **CSS3** | CSS variables, Flexbox, Grid, Glassmorphism, keyframe animations |
| **Client Scripting** | **Vanilla JavaScript (ES6+)** | State management, automated reminder loop, DOM manipulation |
| **Data Format** | **JSON** ([`talks.json`](talks.json)) | Default seeded session data |
| **Calendar Standard** | **iCalendar (.ics / RFC 5545)** | Cross-platform calendar event generation via Blob API |
| **Persistence** | **Web Storage API (LocalStorage)** | Multi-user database, appointment storage, and reminder audit logs |

---

## 🧰 Development Tools & Workflow

- **Google Antigravity**: Agentic AI pair programming environment for rapid iteration, feature scaffolding, and documentation.
- **Git & GitHub CLI (`gh`)**: Distributed version control and automated GitHub repository synchronization.
- **Code-OSS / Linux Cloud Shell**: Cloud workspace execution, testing, and development environment.

---

## 📂 Project Structure

```text
event-talks-app/
├── index.html          # Main application dashboard, Auth Gate, Virtual Meetings & 10-Min Reminders
├── login.html          # Standalone secure authentication portal with 8-digit OTP verification
├── talks.json          # Default seeded appointment & virtual meeting schedule data
├── README.md           # Comprehensive project documentation
├── summary_task3.md    # Repository inspection records
└── summary_task4.md    # Development milestone logs
```

---

## 🚀 Getting Started

### Prerequisites
Any modern browser (Google Chrome, Firefox, Microsoft Edge, Safari) supporting the Web Crypto API and Web Audio API.

### Running the Project

#### Option 1: Lightweight Local Server (Recommended)
```bash
# Using Python 3
python3 -m http.server 8000

# Or using Node.js npx serve
npx serve .
```
Navigate to `http://localhost:8000` in your web browser.

#### Option 2: Direct Browser Launch
Simply open [`index.html`](index.html) in your browser:
- On Linux: `xdg-open index.html`
- On macOS: `open index.html`

---

## 🔒 Security Highlights

1. **Client-Side SHA-256 Cryptography**: Passwords are never stored in raw text; each account is hashed with unique salts.
2. **Dual 8-Digit OTP Verification**: Confirms authenticity of both email and phone number.
3. **Anti-Injection Sanitization**: Defense against Cross-Site Scripting (XSS) and SQL/HTML injection tokens.
4. **Session Token Validation**: Tokenized sessions with automatic expiration and active user verification.

---

## 📄 License

This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
