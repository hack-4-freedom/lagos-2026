# Talk2Pay

**Hack4Freedom Lagos 2026**

---

## Overview

Talk2Pay is a lightweight crypto payment system built for small merchants in Nigeria. It makes Bitcoin payments simple, fast, and accessible using QR codes, payment links, WhatsApp, and USSD, so local businesses can accept digital payments without complex banking infrastructure or expensive fintech integrations.

## Problem

Across Nigeria and many parts of the Global South:

- Small merchants still rely heavily on cash
- Bank transfers are slow, unreliable, and require manual confirmation
- Most crypto payment tools are too complex or not designed for local usage
- Many merchants lack access to global payment systems due to onboarding and infrastructure barriers

This creates friction in everyday trade and limits financial inclusion for small businesses.

## Solution

Talk2Pay provides an API-first crypto payment backend that enables:

- Instant Bitcoin payment requests
- QR code generation for fast in-person payments
- Shareable payment links for WhatsApp
- USSD access for feature-phone users
- Merchant dashboards for transaction tracking
- CSV export for offline record keeping

The system is designed for real-world Nigerian commerce, where speed, simplicity, and accessibility matter more than complexity.

## How It Works

1. A merchant creates a payment request (for example, ?2,000 equivalent in BTC)
2. The system generates:
   - a payment link
   - a QR code for scanning
3. The customer pays using Bitcoin (or a Lightning-ready flow in future expansion)
4. The backend tracks the transaction and updates status
5. The merchant can view history, export reports, or simulate completion for testing

Additional features:

- WhatsApp bot lets merchants create payments with simple commands
- USSD integration enables wider inclusion for low-end mobile users

## Why Bitcoin / Lightning and Nostr

Talk2Pay is built for a Bitcoin hackathon because:

- Bitcoin provides a borderless payment rail
- Lightning and Nostr-style flows enable fast, low-fee transactions
- It reduces dependency on fragile local payment systems
- It aligns with the mission of financial freedom and open access

Talk2Pay is built because it leverages open, borderless technologies that make payments and communication faster, cheaper, and more accessible for local merchants.

Bitcoin provides a global, permissionless payment rail that reduces dependency on traditional banking systems. However, for everyday transactions, it can be slow and expensive.

The Lightning Network solves this by enabling instant, low-fee Bitcoin payments, making it practical for real-world purchases like food, retail goods, and local services.

Nostr complements this ecosystem by providing a decentralized communication layer where users can interact without relying on centralized platforms, using cryptographic identities instead of traditional accounts.

Together, these technologies form a stack for open financial and communication systems:

* **Bitcoin** → Global money layer
* **Lightning Network** → Fast payments layer
* **Nostr** → Decentralized communication layer

This combination supports the vision of building a Lightning-native, merchant-first payment system for Africa, designed for real-world usability in local markets.

## Technology Stack

* NestJS
* TypeScript
* PostgreSQL
* TypeORM
* JWT Authentication
* Swagger/OpenAPI
* Twilio WhatsApp API
* USSD Integration
* QR Code Generation
* Bitcoin / Lightning-ready Architecture/ Nostr

---

## Team

* Wuraola Omilabu - Frontend Engineer
* Daniella Abibi - Blockchain Engineer
* Hasbiyallah Oyebo - Backend Engineer
* Rebecca Ojo - Designer

---

## Repository & Links

* GitHub Repository: `https://github.com/hasbiyallah01/Talk2pay.git`

---

## Status

 Work in Progress

The project is currently in active development as part of Hack4Freedom Lagos 2026.

---

## Next Steps

* Add voice support
* Improve USSD interaction experience
* Expand WhatsApp payment automation
* Add merchant invoicing and analytics
* Deploy production-ready API infrastructure
* Explore Nostr-based merchant identity and communication features


The long-term vision is to evolve this into a Lightning-native merchant payment layer for Africa.
