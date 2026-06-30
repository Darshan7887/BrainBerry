<div align="center">

<img src="https://github.com/user-attachments/assets/3ed1d821-9ff5-4b43-b752-a1bc8e4b5bca" width="120"/>

# 🧠 BrainBerry
## AI-Powered Voice-Driven Gamified Learning Platform

### Learn • Speak • Play • Grow

[![Docker Ready](https://img.shields.io/badge/Docker-Ready-blue?logo=docker)]()
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)]()
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)]()
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)]()
[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?logo=firebase&logoColor=black)]()
[![GitHub Actions](https://img.shields.io/badge/CI/CD-GitHub%20Actions-2088FF?logo=githubactions)]()
[![License](https://img.shields.io/badge/License-MIT-green)]()

---

### 🎥 Demo
https://youtu.be/siYO2NgPIww?si=lJ4Js-FGc-LyniJ1

---

### 🚀 Live Demo
*(Will be added after AWS deployment.)*

</div>

---

# 📖 Table of Contents

- Project Overview
- Problem Statement
- Solution
- Vision
- Features
- Screenshots
- System Architecture
- Workflow
- Technology Stack
- Project Structure
- Installation
- Running with Docker
- Running Locally
- Parent Dashboard
- AI Features
- Authentication
- Gamification
- Roadmap
- NEP 2020 Alignment
- Sustainable Development Goals
- Demo
- Team
- License
- Contributing

---

# 📌 Project Overview

BrainBerry is an AI-powered voice-driven gamified learning platform that transforms early childhood education through interactive voice experiences, speech recognition, educational games, and parental supervision.

Instead of relying only on passive videos or reading-based learning, BrainBerry enables children to **learn by speaking, listening, exploring, and playing**.

The platform combines:

- 🎤 Voice Recognition
- 🎮 Gamification
- 📚 Interactive Learning
- 👨‍👩‍👧 Parent Dashboard
- ☁ Firebase Backend
- 🤖 AI-powered interaction

to provide an engaging educational experience.

---

# ❗ Problem Statement

Many educational platforms are still based on passive learning where children watch videos or read static content.

Some major challenges include:

- Low engagement among young learners
- Limited interactive learning experiences
- Lack of parental monitoring
- Minimal support for multilingual education
- Poor motivation and reward systems
- Traditional learning methods that fail to sustain attention

These limitations reduce learning effectiveness and make education less enjoyable.

---

# 💡 Our Solution

BrainBerry addresses these challenges by combining voice interaction, gamification, AI, and parental controls into a single educational platform.

Children can:

- Speak instead of typing
- Learn through interactive activities
- Receive rewards for completing lessons
- Practice pronunciation
- Learn through stories, games and activities

Parents can:

- Monitor progress
- Assign lessons
- Manage screen time
- Track achievements
- Synchronize learning across devices

---

# 🌍 Vision

BrainBerry aims to bridge the gap between education and engagement by enabling children to learn through voice, interaction, visual experiences, and play rather than passive text-based learning.

The platform aligns with:

- 🇮🇳 National Education Policy (NEP) 2020
- 🌍 Sustainable Development Goal 4 – Quality Education

---

# ✨ Features

## 🎤 Voice-Driven Learning

- Speech Recognition
- Pronunciation Practice
- Voice Commands
- Hands-free Learning
- Interactive Voice Responses

---

## 📚 Interactive Learning Modules

### ✨ Magic of Words

- Vocabulary Building
- Word Recognition
- Listening Activities
- Speaking Activities

---

### 🔢 Numbers

- Counting
- Number Identification
- Number Games
- Interactive Exercises

---

### 🎨 Colours & Shapes

- Colour Recognition
- Shape Recognition
- Matching Activities
- Visual Learning

---

### 🧪 Colour Mixing Lab

- Real-time Colour Mixing
- Primary Colours
- Secondary Colours
- Voice Guidance
- Interactive Experiments

---

### 🐾 Animals World

- Animal Identification
- Animal Sounds
- Interactive Exploration

---

### 🇮🇳 Hindi Learning

#### स्वर

- Pronunciation
- Recognition
- Voice Practice

#### व्यंजन

- Character Recognition
- Speaking Practice
- Flash Cards

---

### 🏛 Civic Sense

- Good Habits
- Social Awareness
- Community Learning

---

### ✍ Golden Words & Sentences

- Daily Vocabulary
- Sentence Formation
- Communication Skills

---

# 🎮 Gamification

BrainBerry transforms education into a rewarding adventure.

Features include:

- XP System
- Coins
- Achievement Badges
- Learning Streaks
- Progress Tracking
- Rewards
- Challenges
- Milestones

---

# 📸 Screenshots

## 🏠 Home

> *(Insert Screenshot)*

## 📚 Learning Dashboard

> *(Insert Screenshot)*

## 🎤 Voice Learning

> *(Insert Screenshot)*

## 🎨 Colour Mixing

> *(Insert Screenshot)*

## 🇮🇳 Hindi Learning

> *(Insert Screenshot)*

## 👨‍👩‍👧 Parent Dashboard

> *(Insert Screenshot)*

## 🏆 Rewards

> *(Insert Screenshot)*

---

# 🏗 System Architecture

```text
                Parent Dashboard
                      │
                      │
          Firebase Authentication
                      │
                      │
        Firebase Realtime Database
                      │
      ┌───────────────┴──────────────┐
      │                              │
 Child Learning                Parent App
      │                              │
 Voice Recognition           Screen Controls
      │                              │
 Speech API                Progress Monitoring
      │                              │
 Learning Modules       Remote Synchronization
---

# 👨‍👩‍👧 Parent Dashboard

BrainBerry includes a dedicated Parent Dashboard that empowers parents to actively participate in their child's learning journey.

### Features

- 📊 Learning Progress Analytics
- ⏱ Screen Time Management
- 📚 Lesson Assignment
- 🔓 Lesson Lock / Unlock
- 🔔 Real-Time Progress Tracking
- 🎯 Goal Setting
- 📈 XP Monitoring
- 🏆 Achievement Tracking
- 📱 Remote Learning Management

---

# 📱 Parent Companion App

Parents can securely connect to their child's device using a unique pairing code.

The companion application allows parents to:

- Monitor learning progress
- Assign lessons remotely
- Lock or unlock educational modules
- Set daily screen time limits
- Track achievements
- View detailed analytics

---

# 🔗 Parent–Child Synchronization

BrainBerry introduces a secure pairing mechanism that synchronizes both devices in real time.

### Workflow

1. Parent creates an account.
2. Parent generates a unique connection code.
3. Child enters the connection code.
4. Devices become securely paired.
5. Parent dashboard automatically syncs with the child's application.
6. Learning progress updates instantly.

---

# 🔐 Authentication

BrainBerry uses Firebase Authentication for secure user management.

### Authentication Features

- Email & Password Login
- Secure Registration
- Session Management
- User Profiles
- Password Reset
- Protected Routes

---

# ☁ Firebase Services

BrainBerry leverages Firebase to provide reliable backend services.

### Firebase Authentication

- Secure Login
- Secure Signup
- User Sessions

### Firebase Realtime Database

- Learning Progress
- Parent Dashboard
- Lesson Synchronization
- XP Tracking
- Coins
- Rewards
- Analytics

---

# 📊 Learning Analytics

BrainBerry continuously tracks student progress.

Metrics include:

- Lessons Completed
- XP Earned
- Coins Collected
- Achievement Badges
- Learning Streak
- Daily Progress
- Weekly Progress
- Overall Completion Rate

---

# 🤖 AI Features

## Current AI Features

- Speech Recognition
- Voice Commands
- Voice Validation
- Interactive Voice Feedback

---

## Upcoming AI Features

- AI Tutor
- Personalized Learning
- Adaptive Difficulty
- AI Recommendations
- Learning Prediction
- Personalized Study Plans

---

# 🎮 Gamification Engine

BrainBerry motivates children through an engaging reward system.

### Rewards

- XP
- Coins
- Stars
- Badges
- Unlockables

### Progress

- Learning Streak
- Daily Goals
- Weekly Goals
- Completion Percentage

### Achievements

- First Lesson
- First Voice Activity
- 100 XP
- Perfect Score
- Daily Champion
- Learning Master

---

# 🧩 Educational Modules

BrainBerry currently includes multiple educational experiences.

### Language Learning

- Vocabulary
- Word Recognition
- Speaking Practice
- Sentence Formation

### Mathematics

- Numbers
- Counting
- Recognition
- Interactive Exercises

### Environmental Learning

- Animals
- Colours
- Shapes

### Hindi Learning

- स्वर
- व्यंजन
- Pronunciation
- Character Recognition

### Social Learning

- Civic Sense
- Good Habits
- Daily Life Skills

---

# ⚙ Technology Stack

## Frontend

- HTML5
- CSS3
- JavaScript

---

## Backend

- Firebase Authentication
- Firebase Realtime Database

---

## Voice Processing

- Web Speech API
- Speech Recognition API

---

## Deployment

- Docker
- Docker Compose
- GitHub Actions
- AWS (Planned)

---

## Development Tools

- Git
- GitHub
- VS Code

---

# 📂 Project Structure

```
BrainBerry
│
├── assets/
│   ├── audio/
│   ├── css/
│   ├── images/
│   ├── js/
│   ├── models/
│   └── videos/
│
├── config/
├── demo/
├── docs/
├── screenshots/
├── .github/
│
├── Dockerfile
├── docker-compose.yml
├── package.json
├── README.md
├── LICENSE
└── .env.example
```

---

# 🏗 Application Workflow

```
User Opens BrainBerry
            │
            ▼
Authentication
            │
            ▼
Select Learning Module
            │
            ▼
Voice Interaction
            │
            ▼
Educational Activity
            │
            ▼
XP & Rewards
            │
            ▼
Firebase Database
            │
            ▼
Parent Dashboard Updates
```

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/BrainBerry.git

cd BrainBerry
```

---

## Configure Environment

```bash
cp .env.example .env
```

Update the environment variables with your Firebase configuration.

---

# 🐳 Run Using Docker (Recommended)

```bash
docker compose up --build
```

Open:

```
http://localhost:8080
```

---

# 💻 Run Without Docker

Install dependencies

```bash
npm install
```

Start application

```bash
npm start
```

Open

```
http://localhost:3000
```

---

# 📋 Requirements

Before running BrainBerry ensure you have:

- Git
- Docker Desktop
- Docker Compose
- Node.js
- Modern Browser
- Internet Connection (Firebase)

---
---

# 💼 Use Cases

BrainBerry is designed to support a wide range of educational environments.

### 🏡 Home Learning
Parents can guide and monitor their child's education from home while encouraging independent learning.

### 🏫 Schools
Teachers can use BrainBerry as an interactive digital learning companion inside classrooms.

### 📚 Early Childhood Education Centers
Provides engaging educational experiences for preschool and kindergarten learners.

### 🌐 Digital Learning Platforms
Can be integrated into online educational ecosystems to enhance engagement.

### 🗣 Language Development Programs
Supports pronunciation, vocabulary building, listening, and speaking skills.

---

# 🎯 Why BrainBerry?

Unlike traditional educational platforms that rely heavily on passive videos and text, BrainBerry encourages children to actively participate in the learning process.

### Traditional Learning

- Passive learning
- Video-based interaction
- Limited parental involvement
- Low engagement
- Minimal personalization

### BrainBerry

- 🎤 Voice-driven learning
- 🎮 Gamified education
- 👨‍👩‍👧 Parent dashboard
- 📊 Learning analytics
- 🤖 AI-powered interaction
- 🌍 Multilingual learning
- ☁ Cloud synchronized

---

# 🌍 National Education Policy (NEP 2020)

BrainBerry supports the vision of India's National Education Policy by promoting:

## Foundational Literacy & Numeracy

- Reading Skills
- Vocabulary Building
- Number Learning
- Interactive Activities

---

## Experiential Learning

Children learn through:

- Speaking
- Listening
- Exploration
- Activities
- Play

---

## Multilingual Education

Current Support

- English
- Hindi

Future Support

- Marathi
- Gujarati
- Bengali
- Tamil
- Telugu
- Kannada
- Malayalam

---

## Digital Education

BrainBerry leverages modern technologies including AI, speech recognition, and cloud computing to make education engaging and accessible.

---

# 🌎 Sustainable Development Goals (SDGs)

BrainBerry contributes towards several United Nations Sustainable Development Goals.

### SDG 4 — Quality Education

Providing accessible, engaging, and inclusive education for children.

---

### SDG 9 — Industry, Innovation & Infrastructure

Applying Artificial Intelligence and digital technologies to modernize education.

---

### SDG 10 — Reduced Inequalities

Supporting learners from different educational and linguistic backgrounds.

---

### SDG 11 — Sustainable Communities

Encouraging cultural preservation and multilingual education.

---

### SDG 3 — Good Health & Well-being

Reducing learning stress through enjoyable and interactive educational experiences.

---

# 🚀 Future Roadmap

## Phase 1

- Improved Hindi Learning
- Better Parent Analytics
- Additional Educational Games
- More Voice Activities

---

## Phase 2

- AI Tutor
- Personalized Learning Paths
- Adaptive Difficulty
- AI Learning Recommendations
- Learning Prediction

---

## Phase 3

- Teacher Dashboard
- School Management Portal
- Institution Dashboard
- Classroom Management
- Student Performance Analytics

---

## Phase 4

- Mobile Applications
- Offline Learning Mode
- International Language Support
- AI Voice Assistant
- Advanced Learning Analytics

---

# 📈 Project Impact

BrainBerry aims to create a positive educational impact by helping children:

- Build confidence through voice interaction.
- Improve communication skills.
- Strengthen vocabulary.
- Develop foundational literacy.
- Learn independently.
- Stay motivated through rewards.
- Enhance cognitive development.
- Build problem-solving abilities.

---

# 🔒 Security

BrainBerry follows secure development practices.

- Firebase Authentication
- Secure User Sessions
- Protected User Data
- Environment Variables
- Cloud-based Authentication

Sensitive credentials are not stored in the repository.

---

# ⚡ Performance

BrainBerry is optimized for:

- Fast Loading
- Responsive Interface
- Smooth Animations
- Efficient Voice Processing
- Cloud Synchronization

---

# 🐳 Docker Commands

Build

```bash
docker compose build
```

Run

```bash
docker compose up
```

Stop

```bash
docker compose down
```

Rebuild

```bash
docker compose up --build
```

---

# 🤝 Contributing

Contributions are always welcome.

If you'd like to improve BrainBerry:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push your branch.
5. Open a Pull Request.

Please ensure your code follows the project's coding standards and documentation guidelines.

---

# 📝 License

This project is licensed under the MIT License.

See the `LICENSE` file for complete details.

---

# 🎥 Demo Video

Watch BrainBerry in action:

▶ **YouTube Demo**

https://youtu.be/siYO2NgPIww?si=lJ4Js-FGc-LyniJ1

---

# 👨‍💻 Team BrainBerry

### Darshan Jayant Nerkar

Project Lead

Cloud • DevOps • Full Stack Development

---

### Avishkar Vijay Kapadnis

Frontend Development

UI/UX Design

---

### Parag Bharat Watane

Backend Development

Firebase Integration

---

### Saurav Gajanan Patil

Testing

Documentation

Quality Assurance

---

# 🙏 Acknowledgements

We sincerely thank:

- Smart India Hackathon
- National Education Policy (NEP 2020)
- Firebase
- Docker
- GitHub
- Open Source Community

for providing the tools and inspiration that helped make BrainBerry possible.

---

# ⭐ Support the Project

If you like BrainBerry and believe in transforming education through technology,

please consider giving this repository a ⭐ on GitHub.

It motivates us to continue improving the platform.

---

<div align="center">

# 🧠 BrainBerry

### Learn • Speak • Play • Grow

**Transforming Early Childhood Education through Artificial Intelligence, Voice Interaction, and Gamification.**

Made with ❤️ by Team BrainBerry

</div>
