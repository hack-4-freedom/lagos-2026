# KoboSats

> **Empowering the informal economy through offline-first Lightning integration.**
> *Submitted for Hack4Freedom Lagos 2026*

### Overview
KoboSats is a digital payment and debt-tracking solution designed specifically for informal market traders in Nigeria. It bridges the gap between basic feature phones and the Bitcoin Lightning Network, allowing merchants to accept digital payments and log customer debts completely offline via a USSD interface.

### Problem
Informal traders in the Global South face significant barriers to modern financial tools:
* Reliance on physical paper notebooks for debt tracking, which are easily lost or destroyed, leading to lost revenue.
* A lack of consistent internet access and smartphone ownership.
* Exclusion from fast, borderless digital payment networks due to hardware constraints.

### Solution
KoboSats solves this by providing a dual-interface ecosystem:
* **The USSD Gateway:** A basic feature phone interface (dialing `*384*7287#`) that allows offline traders to interact with the Lightning Network and log debts via SMS.
* **The Web Dashboard:** A clean, mobile-first frontend application for traders who *do* have internet access, featuring 4-language local translation, Lightning QR code generation, and a persistent digital debt ledger backed up securely.

### Technology Stack
| Layer | Technologies Used |
| :--- | :--- |
| **Client / UX** | React, Tailwind CSS, Context API |
| **Core Services** | Python, FastAPI, SQLite |
| **Protocol Layer** | Breez Nodeless SDK (Lightning), Nostr (Decentralized State Backup) |
| **Telecom Integration** | Africa's Talking API (USSD & SMS Routing) |

### Team Members
* **Timilehin** - Frontend Developer
* **Busayomi** - Backend Developer
* **Rita** - Backend Developer
* **Rufai** - Product Designer

### Links

[![Frontend Repo](https://img.shields.io/badge/Frontend_Repo-7E22CE?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Team-Lumina/KoboStat-frontend)
[![Backend Repo](https://img.shields.io/badge/Backend_Repo-7E22CE?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Team-Lumina/KoboStat-frontend)
[![Live Demo](https://img.shields.io/badge/Live_Demo-7E22CE?style=for-the-badge&logo=vercel&logoColor=white)](#) *(Deployment pending)*

### Current Status and Next Steps
The KoboSats frontend UI architecture is fully mapped, styled, and actively consuming mock endpoints, complete with a fully interactive web-based Nokia USSD emulator for demonstration. The backend team is currently finalizing the integration of the Breez SDK for live Lightning invoice generation. 

**Next Steps:**
* Deploy the USSD logic to a live Africa's Talking shortcode.
* Finalize the Nostr event publishing for decentralized debt backups.
* Conduct live field testing with local Lagos merchants.
