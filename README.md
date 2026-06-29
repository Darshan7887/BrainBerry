# 🍓 BrainBerry

[![CI/CD](https://github.com/Darshan7887/brainberry/actions/workflows/deploy.yml/badge.svg)](https://github.com/Darshan7887/brainberry/actions)
[![Docker](https://img.shields.io/badge/Docker-darshan7887%2Fbrainberry-2496ED?logo=docker&logoColor=white)](https://hub.docker.com/r/darshan7887/brainberry)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Firebase](https://img.shields.io/badge/Firebase-Auth%20%2B%20Firestore-FFCA28?logo=firebase&logoColor=black)](https://firebase.google.com/)

> **A voice-driven, interactive learning platform for children with special learning needs.**

BrainBerry makes education fun, inclusive, and accessible — combining voice recognition, gamification, emotion detection, and parental controls into a single platform designed for children with Specific Learning Difficulties (SLDs).

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Our Solution](#-our-solution)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Quick Start](#-quick-start)
- [Docker Deployment](#-docker-deployment)
- [Cloud Deployment](#-cloud-deployment)
- [CI/CD Pipeline](#-cicd-pipeline)
- [Project Structure](#-project-structure)
- [Module Documentation](#-module-documentation)
- [Data Sync](#-data-sync)
- [Screenshots](#-screenshots)
- [Future Scope](#-future-scope)
- [Contributors](#-contributors)
- [License](#-license)

---

## 🎯 Problem Statement

**1 in 5 children** worldwide faces some form of learning difficulty — including dyslexia, dyscalculia, ADHD, and other Specific Learning Difficulties (SLDs). Traditional education often leaves these children behind because:

- 📖 Text-heavy content is inaccessible to children with reading difficulties
- 🔇 Lack of multi-sensory learning approaches
- 👨‍👩‍👧 Parents lack tools to monitor and guide their child's learning journey
- 🎮 Educational content fails to engage and retain attention

---

## 💡 Our Solution

BrainBerry is a **playful, voice-first learning platform** that transforms education through:

- **🎤 Voice-Driven Interaction** — Children learn by speaking, not typing. Our speech recognition engine provides real-time feedback using fuzzy matching (Levenshtein distance).
- **😊 Emotion Detection** — Webcam-based facial expression analysis (using face-api.js) helps track engagement and emotional state during lessons.
- **👨‍👩‍👧 Parental Dashboard** — Parents can set screen time limits, lock/unlock lessons, track progress, and connect across devices using a unique connection code system.
- **🎮 Gamified Learning** — Educational games (Tetris, Simon Says, Memory Match, River Crossing) and challenge modes keep children motivated.
- **🔗 Real-Time Sync** — Firebase Firestore enables instant parent ↔ child device synchronization — settings update in real-time across all linked devices.

---

## ✨ Key Features

### 📚 Learning Modules
| Module | Description |
|--------|-------------|
| **Phonics (Say & Repeat)** | Voice-based alphabet learning with speech recognition feedback |
| **Animals** | Interactive animal identification with sounds and videos |
| **Hindi (हिन्दी)** | Hindi Swar (vowels) and Vyanjan (consonants) learning |
| **Colors & Shapes** | Color identification, shape recognition with audio cues |
| **Colour Mixing** | Interactive colour mixing experiments |
| **Civic Sense** | Real-world civic responsibility scenarios |
| **Counting & Numbers** | Number recognition with voice practice |
| **Syllabus Words** | Vocabulary building with pronunciation practice |

### 📖 Interactive Stories
- 🦊 The Fox and the Grapes
- 🦁 The Lion and the Mouse
- 🐦 The Clever Crow

### 🎮 Educational Games
| Game | Type |
|------|------|
| **Tetris** | Spatial reasoning & pattern recognition |
| **Simon Says** | Memory & sequence recall |
| **Memory Match** | Visual memory training |
| **River Crossing** | Logic & problem-solving |
| **Fill-in-the-Blanks** | Vocabulary & comprehension |
| **Air Writing** | Fine motor skills via webcam hand tracking |

### 👨‍👩‍👧 Parental Controls
- 🔐 PIN-protected parental dashboard
- ⏱️ Screen time limits with auto-lock overlay
- 📝 Lesson assignment — lock/unlock specific lessons
- 📊 Learning progress tracking (correct/wrong/completed)
- 🔗 Connection code system for parent ↔ child device linking
- 📋 Shared to-do list with completion tracking

### 📱 Parent Apps (PWA)
- **Desktop Dashboard** (`parent-app.html`) — Full-featured parental control panel
- **Mobile App** (`parent-mobile.html`) — Mobile-optimized PWA with installable shortcut
- **Download Page** (`parent-download.html`) — PWA installation guide

### 🤖 AI & ML Features
- **Emotion Detection** — Real-time facial expression analysis via face-api.js
- **Air Writing** — Webcam-based hand tracking with MediaPipe Hands
- **Voice Recognition** — Web Speech API with Levenshtein distance fuzzy matching

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                      Client (Browser)                        │
│                                                              │
│  ┌─────────────┐  ┌──────────────┐  ┌────────────────────┐  │
│  │  index.html  │  │  front.html  │  │    Less.html       │  │
│  │   (Login)    │  │(Home Dashboard)│ │   (Lessons Grid)   │  │
│  └──────┬───────┘  └──────┬───────┘  └────────┬───────────┘  │
│         │                 │                    │              │
│  ┌──────┴─────────────────┴────────────────────┴──────────┐  │
│  │                Shared JS Modules                        │  │
│  │  ┌──────────────────┐  ┌───────────────────────┐       │  │
│  │  │  assets/js/bb-user-data.js │  │  assets/js/parental-control.js  │       │  │
│  │  │  (User Namespace) │  │  (Screen Time + Lock) │       │  │
│  │  ├──────────────────┤  ├───────────────────────┤       │  │
│  │  │  assets/js/profile-panel.js│  │  assets/js/subscription.js      │       │  │
│  │  │  (Profile Sidebar)│  │  (Plan Management)    │       │  │
│  │  ├──────────────────┤  ├───────────────────────┤       │  │
│  │  │  assets/js/bb-sync.js      │  │  bb-monitoring.js     │       │  │
│  │  │  (Firestore Sync) │  │  (Activity Tracking)  │       │  │
│  │  └──────────────────┘  └───────────────────────┘       │  │
│  └────────────────────────────┬────────────────────────────┘  │
│                               │                               │
│            ┌──────────────────┴──────────────────┐           │
│            │        localStorage (User-Scoped)    │           │
│            │     bb_user:<email>:<setting_key>    │           │
│            └──────────────────┬──────────────────┘           │
└───────────────────────────────┼───────────────────────────────┘
                                │
                    ┌───────────┴───────────┐
                    │    Firebase Cloud      │
                    │  ┌─────────────────┐  │
                    │  │   Firestore DB   │  │
                    │  │  • bb_sync      │  │
                    │  │  • users        │  │
                    │  │  • bb_codes     │  │
                    │  ├─────────────────┤  │
                    │  │   Firebase Auth  │  │
                    │  │  • Email/Pass   │  │
                    │  │  • Google       │  │
                    │  │  • Facebook     │  │
                    │  │  • Twitter      │  │
                    │  └─────────────────┘  │
                    └───────────────────────┘
```

### Connection Code Flow

```
Parent Dashboard                       Parent Mobile App
      │                                       │
      ├── Generate 6-digit Code ──────────►   │
      │   (stored in Firestore)               │
      │                                       │
      │                          ◄── Enter Code
      │                          ◄── Validated vs Firestore
      │                                       │
      │  ◄──────── Accounts Linked ───────────┤
      │                                       │
      ├── Settings sync ◄────────────────────►├── Settings sync
      │   (bidirectional via Firestore)       │
```

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | HTML5, CSS3, JavaScript (ES6+) |
| **UI Framework** | Vanilla CSS with Glassmorphism design, responsive layouts |
| **Fonts** | Google Fonts (Fugaz One, Funnel Display) |
| **Authentication** | Firebase Auth (Email, Google, Facebook, Twitter) |
| **Database** | Firebase Firestore (real-time sync) + localStorage (offline-first) |
| **ML / AI** | face-api.js (emotion detection), MediaPipe Hands (air writing) |
| **Voice** | Web Speech API (recognition + synthesis) |
| **PWA** | Service Worker + Web App Manifest (parent mobile app) |
| **Server** | Nginx (Alpine) — static file serving |
| **Container** | Docker with health checks |
| **CI/CD** | GitHub Actions → Docker Hub (darshan7887/brainberry) |
| **Deployment** | Netlify, Render, Railway, Docker Hub |

---

## 🚀 Quick Start

### Prerequisites

- A modern web browser (**Chrome recommended** for voice features)
- [Docker](https://www.docker.com/) (for containerized deployment)
- [Node.js 18+](https://nodejs.org/) (optional, for local dev server)

### Option 1: Local Dev Server (Recommended)

```bash
# Clone the repository
git clone https://github.com/Darshan7887/brainberry.git
cd brainberry

# Start the dev server
npm start

# Open http://localhost:3000 in your browser
```

### Option 2: Open Directly

Simply open `index.html` in your browser. Some features (voice recognition, Firebase auth) require HTTPS or localhost.

---

## 🐳 Docker Deployment

### Build & Run

```bash
# Build the Docker image
docker build -t brainberry:latest .

# Run the container
docker run -d --name brainberry -p 8080:80 brainberry:latest

# Open http://localhost:8080
```

### Using Docker Compose

```bash
docker compose up -d        # Start
docker compose down         # Stop
docker compose logs -f      # View logs
```

### NPM Docker Scripts

| Script | Description |
|--------|-------------|
| `npm run docker:build` | Build Docker image |
| `npm run docker:run` | Run container on port 8080 |
| `npm run docker:stop` | Stop and remove container |
| `npm run docker:logs` | View container logs |

---

## ☁️ Cloud Deployment

### Netlify
1. **Drag & Drop**: Go to [Netlify Drop](https://app.netlify.com/drop), drag the project folder
2. **CLI**: `npx -y netlify-cli deploy --prod --dir .`
3. **Git**: Connect your GitHub repo → auto-deploys on push

### Render
1. Connect your GitHub repo at [Render](https://dashboard.render.com)
2. Select **Web Service** → **Docker** environment
3. Render auto-detects `Dockerfile` and `render.yaml`

### Railway
1. Connect your GitHub repo at [Railway](https://railway.app)
2. Railway auto-detects the `Dockerfile`
3. Set port to `80` in settings

---

## ⚙️ CI/CD Pipeline

The project includes a GitHub Actions workflow (`.github/workflows/deploy.yml`):

| Step | Description |
|------|-------------|
| **Checkout** | Pulls latest code |
| **Build** | Builds Docker image |
| **Start** | Runs container on port 8080 |
| **Health Check** | Verifies index.html returns HTTP 200 |
| **Page Verification** | Checks all key pages are accessible |
| **Asset Verification** | Validates CSS/JS files load correctly |
| **Docker Hub Push** | Pushes to `darshan7887/brainberry:latest` |
| **Cleanup** | Stops and removes test container |

**Triggers:**
- **Push to `main`** → Full build + test + Docker Hub push
- **Pull Request to `main`** → Build + test only (no push)

---

## 📁 Project Structure

```
brainberry/
│
├── index.html                 # Landing page (login/register)
├── front.html                 # Home dashboard (after login)
├── register.html              # Registration page
├── Less.html                  # Lessons grid page
├── parent.html                # Parental dashboard
├── parent-app.html            # Parent app (desktop PWA)
├── parent-mobile.html         # Parent mobile app (mobile PWA)
├── parent-download.html       # App download page
│
├── ── Learning Modules ──
├── phonics.html               # Phonics learning module
├── animals.html               # Animals learning module
├── hindi.html                 # Hindi language hub
├── hindi_swar.html            # Hindi vowels (स्वर) module
├── hindi_vyanjan.html         # Hindi consonants (व्यंजन) module
├── color.html                 # Colors module
├── shapes.html                # Shapes module
├── color-shape.html           # Colors & Shapes combined
├── colour-mixing.html         # Colour mixing experiments
├── colormix.html              # Colour mixing page
├── counting.html              # Counting module
├── civicsense.html            # Civic sense module
├── syllabuswords.html         # Syllabus words module
├── alp.html                   # Alphabets module
├── no1.html                   # Numbers module
├── NunInd.html                # Numbers (India) module
├── gsa.html                   # Golden sentences activity
│
├── ── Stories ──
├── story.html                 # Story hub page
├── clever-crow.html           # The Clever Crow story
├── lion-mouse.html            # The Lion & The Mouse story
├── fox.html                   # The Fox & The Grapes story
│
├── ── Games & Challenges ──
├── chal.html                  # Games hub
├── challen.html               # Challenges hub
├── challenge4.html            # Challenge mode
├── colorschallenge.html       # Colors challenge
├── civicchal1.html            # Civic sense challenge
├── gamesbg.html               # Games background page
├── simongbg.html              # Simon Says game
├── tetris.html                # Tetris game
├── river.html                 # River Crossing puzzle
├── memory.html                # Memory match game
├── fibc.html                  # Fill-in-the-Blanks challenge
├── airwriting.html            # Air writing (webcam)
├── emotion.html               # Emotion detection (webcam)
│
├── ── Shared JS Modules ──
├── assets/js/bb-user-data.js            # Per-user localStorage namespace utility
├── assets/js/profile-panel.js           # Profile sidebar component
├── assets/js/parental-control.js        # Screen time + progress engine
├── assets/js/subscription.js            # Subscription plan management
├── sw-parent.js               # Service worker for parent PWA
├── assets/js/counting.js                # Counting game logic
├── assets/js/memory.js                  # Memory game logic
├── assets/js/teetris.js                 # Tetris game engine
├── assets/js/river.js / assets/css/river.css       # River Crossing game
├── assets/js/fibc.js                    # Fill-in-the-Blanks engine
├── assets/js/airwriting-opencv.js       # Air writing with MediaPipe
├── face-api.js                # Face detection ML library
│
├── src/
│   └── js/
│       ├── assets/js/bb-sync.js         # Firebase Firestore real-time sync
│       └── bb-monitoring.js   # Activity & progress tracking
│
├── ── Stylesheets ──
├── assets/css/style.css                  # Main stylesheet
├── assets/css/fr.css                     # Home dashboard styles
├── assets/css/tetris.css                 # Tetris game styles
├── assets/css/river.css                  # River Crossing styles
│
├── ── Assets ──
├── assets/audio/                     # Color & shape audio files (MP3)
├── assets/models/                    # face-api.js ML model weights
│
├── ── Configuration ──
├── config/
│   ├── nginx.conf             # Nginx server configuration
│   ├── firebase-config.js     # Centralized Firebase configuration
│   └── firestore.rules        # Firebase Security Rules
│
├── ── Help & Info ──
├── help.html                  # Help page
├── rewards.html               # Rewards page
├── FIhelp/                    # Help center (About, Contact, Feedback, News)
├── help/                      # Challenge pages with video previews
├── l1/                        # Say & Repeat learning module
│
├── ── Documentation ──
├── docs/
│   ├── PROJECT_OVERVIEW.md
│   ├── SYSTEM_ARCHITECTURE.md
│   ├── API_DOCUMENTATION.md
│   ├── DEPLOYMENT_GUIDE.md
│   ├── DATABASE_SCHEMA.md
│   ├── TESTING_GUIDE.md
│   ├── USER_GUIDE.md
│   └── TROUBLESHOOTING.md
│
├── ── Deployment ──
├── Dockerfile                 # Production Docker config (nginx:alpine)
├── docker-compose.yml         # Docker Compose for local run
├── netlify.toml               # Netlify deployment config
├── render.yaml                # Render deployment blueprint
├── manifest-parent.json       # PWA manifest for parent app
│
├── ── GitHub ──
├── .github/
│   ├── workflows/deploy.yml   # CI/CD pipeline
│   ├── ISSUE_TEMPLATE/        # Bug report & feature request templates
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── CODEOWNERS
│
├── ── Project Config ──
├── package.json               # Project metadata & npm scripts
├── .gitignore                 # Git exclusions
├── .dockerignore              # Docker build exclusions
├── .env.example               # Environment variables template
├── CONTRIBUTING.md            # Contribution guidelines
├── SECURITY.md                # Security policy
├── LICENSE                    # MIT License
└── README.md                  # This file
```

---

## 📦 Module Documentation

### Core Modules

| Module | File | Purpose |
|--------|------|---------|
| **BB_UserData** | `assets/js/bb-user-data.js` | Per-user localStorage namespace (`bb_user:<email>:<key>`) |
| **BB_Sync** | `assets/js/bb-sync.js` | Firebase Firestore real-time sync (push/pull/listen) |
| **BB_Monitor** | `assets/js/bb-monitoring.js` | Activity tracking (page views, lessons, sessions) |
| **Parental Controls** | `assets/js/parental-control.js` | Screen time tracking, lock overlay, progress API |
| **Profile Panel** | `assets/js/profile-panel.js` | Slide-in profile sidebar with Firestore sync |
| **Subscription** | `assets/js/subscription.js` | Premium subscription plan management |

### BB_Monitor Usage

```javascript
// Automatic page view tracking (runs on every page load)
BB_Monitor.logPageView('phonics.html');

// Manual tracking
BB_Monitor.logLessonStart('phonics');
BB_Monitor.logLessonComplete('phonics', 85);  // with score
BB_Monitor.logEvent('custom_event', { key: 'value' });

// Read data
BB_Monitor.getActivityLog();   // Full activity log
BB_Monitor.getUsageStats();    // Aggregated statistics
```

### BB_Sync Usage

```javascript
// Push local settings to cloud
BB_Sync.pushSettings();

// Pull cloud settings to local
BB_Sync.pullSettings();

// Real-time sync (auto-updates when parent changes settings)
BB_Sync.startRealtimeSync((data) => {
  console.log('Settings updated:', data);
});

// Connection code management
BB_Sync.syncConnectionCode('ABC123');
BB_Sync.validateConnectionCode('ABC123', (email) => {
  if (email) console.log('Linked to:', email);
});
```

---

## 🔄 Data Sync

### How It Works

1. **User-scoped storage**: All data stored under `bb_user:<email>:<setting_key>`
2. **Local-first**: Data saved to localStorage first (instant, works offline)
3. **Cloud sync**: When online, data pushed/pulled to Firebase Firestore
4. **Real-time updates**: Firestore `onSnapshot` provides instant cross-device sync

### Synced Data

- Parent PIN
- Lesson assignments (locked/unlocked)
- Screen time limit & elapsed
- Learning progress (correct/wrong/completed)
- Connection codes
- To-do lists

---

## 📸 Screenshots

> Screenshots of the application can be found in the `demo/` directory.

---

## 🔮 Future Scope

- 🌐 **Multi-language Support** — Expand to Marathi, Tamil, Bengali, and more
- 📊 **AI-Powered Analytics** — Personalized learning paths based on performance
- 🎵 **Music & Rhythm Therapy** — Audio-based learning modules for auditory learners
- 🏆 **Achievement System** — Badges, streaks, and leaderboards
- 📱 **Native Mobile App** — React Native app for iOS and Android
- 🔊 **Advanced Voice AI** — Real-time pronunciation scoring with accent detection
- 🧠 **Adaptive Difficulty** — ML-based difficulty adjustment per child
- 👥 **Teacher Dashboard** — Classroom management for schools
- 🎨 **Custom Avatar System** — Personalized learning companions
- 📝 **Assessment Reports** — Downloadable PDF progress reports for parents

---

## 👥 Contributors

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/Darshan7887">
        <img src="https://github.com/Darshan7887.png" width="80px;" alt="Darshan7887"/><br />
        <sub><b>Darshan7887</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/avishkar12006">
        <img src="https://github.com/avishkar12006.png" width="80px;" alt="avishkar12006"/><br />
        <sub><b>avishkar12006</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Saurav-20-30">
        <img src="https://github.com/Saurav-20-30.png" width="80px;" alt="Saurav-20-30"/><br />
        <sub><b>Saurav-20-30</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/SkiteSight">
        <img src="https://github.com/SkiteSight.png" width="80px;" alt="SkiteSight"/><br />
        <sub><b>SkiteSight</b></sub>
      </a>
    </td>
  </tr>
</table>

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

- **Email**: sauravpatil0506@gmail.com
- **GitHub**: [github.com/Darshan7887/brainberry](https://github.com/Darshan7887/brainberry)

---

## 📖 Documentation

For detailed documentation, see the [`docs/`](docs/) directory:

| Document | Description |
|----------|-------------|
| [Project Overview](docs/PROJECT_OVERVIEW.md) | Mission, target audience, and approach |
| [System Architecture](docs/SYSTEM_ARCHITECTURE.md) | Technical architecture and data flow |
| [API Documentation](docs/API_DOCUMENTATION.md) | Internal module APIs and protocols |
| [Deployment Guide](docs/DEPLOYMENT_GUIDE.md) | Step-by-step deployment instructions |
| [Database Schema](docs/DATABASE_SCHEMA.md) | Firestore and localStorage schemas |
| [Testing Guide](docs/TESTING_GUIDE.md) | CI/CD and manual testing |
| [User Guide](docs/USER_GUIDE.md) | End-user documentation |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | Common issues and FAQ |

---

**Made with ❤️ by the BrainBerry Team**

