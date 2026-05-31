# BitPath

**Hack4Freedom Lagos 2026**

---

## Overview

BitPath is an AI-powered learn-and-earn platform designed to make Bitcoin, digital literacy, and financial education more accessible through conversational learning experiences and reward systems.

The platform combines AI tutoring, gamified learning, and Bitcoin rewards into a modern educational experience that helps users learn interactively while staying engaged through progress tracking and incentives.


## Problem

Many people interested in Bitcoin and digital finance struggle with:

- Complex and overly technical educational materials
- Lack of beginner-friendly learning platforms
- Limited access to interactive tutoring experiences
- Low engagement and motivation during self-learning
- Difficulty understanding financial concepts in simple terms

Traditional educational platforms often fail to make learning personalized, conversational, and rewarding.


## Solution

BitPath provides a conversational AI-powered learning environment where users can:

- Learn Bitcoin and financial concepts interactively
- Receive AI-guided tutoring support
- Track learning progress
- Earn rewards through engagement and quizzes
- Access a simplified and beginner-friendly experience

The platform is designed to reduce the barrier to entry for Bitcoin and financial education while making learning more engaging and practical.


## Features

- AI-powered conversational learning
- Bitcoin and financial literacy education
- Gamified rewards system
- Interactive learning workspace
- Google OAuth and Email authentication
- Responsive modern UI
- Real-time chat-based learning flow
- Reward and progress tracking systems


## Technology Stack

### Frontend

- Next.js
- TypeScript
- Tailwind CSS
- Zustand

### Backend

- NestJS
- Prisma ORM
- PostgreSQL (Neon)
- Redis Cloud
- Bull Queue

### AI & Payments

- OpenAI GPT-4o-mini
- Breez SDK (Lightning Network)


## Project Architecture

```text
Frontend (Next.js) → Backend API (NestJS)
                          ├── PostgreSQL (Neon)
                          ├── Redis Queue
                          ├── OpenAI API
                          └── Lightning Network Service
```

## Authentication

BitPath supports:

* Google OAuth
* Email Authentication

Authentication is handled securely between the frontend and backend using JWT sessions and protected API communication.


## Frontend Architecture

The frontend is built using the Next.js App Router architecture.

### Key Frontend Systems

* Responsive learning workspace
* Zustand state management
* Shared reusable UI components
* Centralized API layer
* Dark and light mode support
* Mobile-first modern interface


## Backend Architecture

The backend is built using NestJS modular architecture.

### Core Backend Systems

* Authentication system
* AI tutoring engine
* Rewards system
* Lightning payment processing
* Queue-based background processing
* Conversation and chat management


## AI Learning Experience

BitPath focuses on conversational learning experiences where users interact with an AI tutor through a chat-based workspace.

The platform is designed to simplify technical Bitcoin concepts into beginner-friendly explanations while keeping users engaged through progress systems and rewards.


## Rewards System

Users can earn:

* XP rewards
* Bitcoin rewards
* Learning streaks
* Progress-based achievements

Rewards are processed through backend queues and Lightning Network infrastructure.


## Team Members

- Azeezat Ogunwande - Product Designer & Product Manager

- Miracle Adakole - Backend developer/Blockchain Developer

- Jemimah Ekong - Frontend developer/Blockchain Developer



## GitHub Repository

https://github.com/JemimahEkong/BitPath


## Current Status

BitPath is currently in active development.

### Completed

* Authentication system
* Frontend and backend integration
* AI workspace UI
* Responsive interface system
* Zustand store integration
* Backend queue processing
* Production AI integration
* Quiz automation system



### In Progress

* Lightning payout infrastructure
* Payment flow optimization
* Deployment and scalability improvements


## Next Steps

* Complete AI tutor backend functionality
* Finalize Bitcoin reward flows
* Improve onboarding and accessibility
* Expand course content
* Deploy production-ready infrastructure


## Open Source

BitPath is being developed as an open-source project as part of Hack4Freedom Lagos 2026.


