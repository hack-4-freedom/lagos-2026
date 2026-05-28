# KoboSat

**Hack4Freedom Lagos 2026**

### Overview
KoboSat is a digital payment and debt-tracking solution designed specifically for informal market traders in Nigeria. It bridges the gap between basic feature phones and the Bitcoin Lightning Network, allowing merchants to accept digital payments and log customer debts completely offline via a USSD interface.

### Problem
Informal traders in the Global South face significant barriers to modern financial tools:
* Reliance on physical paper notebooks for debt tracking, which are easily lost or destroyed, leading to lost revenue.
* A lack of consistent internet access and smartphone ownership.
* Exclusion from fast, borderless digital payment networks due to hardware constraints.

### Solution
KoboSat solves this by providing a dual-interface ecosystem:
* **The USSD Gateway:** A basic feature phone interface (dialing `*384*7287#`) that allows offline traders to interact with the Lightning Network and log debts via SMS.
* **The Web Dashboard:** A clean, mobile-first frontend application for traders who *do* have internet access, featuring 4-language local translation, Lightning QR code generation, and a persistent digital debt ledger backed up securely.

### Technology Stack
* **Frontend:** React, Tailwind CSS, Context API (Mobile-first UI/UX)
* **Backend:** Python, FastAPI, SQLite
* **Bitcoin/Decentralized Infrastructure:** Breez Nodeless SDK (Lightning integration), Nostr (Decentralized identity and state backup)
* **Telecom:** Africa's Talking API (USSD and SMS routing)

### Team Members
* **Timilehin Olajolo** - Frontend Developer [![GitHub](https://img.shields.io/badge/GitHub-timilehinOlajolo-181717?logo=github&logoColor=white)](https://github.com/timilehinOlajolo)
* **Busayomi Olowookere** - Backend Developer [![GitHub](https://img.shields.io/badge/GitHub-busayo524-181717?logo=github&logoColor=white)](https://github.com/busayo524)
* **Rita Okam** - Backend Developer [![GitHub](https://img.shields.io/badge/GitHub-SannaVanna-181717?logo=github&logoColor=white)](https://github.com/SannaVanna)

### Links
* **Source Code:** <br />
    Frontend Repo [![Here](https://img.shields.io/badge/KoboSat_Frontend-181717?logo=github&logoColor=white)](https://github.com/Team-Lumina/KoboSat-frontend)<br />
    Backend Repo [![Here](https://img.shields.io/badge/KoboSat_Backend-181717?logo=github&logoColor=white)](https://github.com/Team-Lumina/KoboSat-Backend)
* **Deployment:**<br />
    Live Demo [![Here](https://img.shields.io/badge/Live_Demo-00C7B7?logo=netlify&logoColor=white)](https://kobosat.netlify.app/)
