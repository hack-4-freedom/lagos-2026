## KoboSats
Bitcoin Lightning payments for Nigeria's informal market traders — via smartphone app or USSD on any basic phone.

## Overview
KoboSats is a self-custody Bitcoin Lightning payment tool built for Nigeria's 40 million informal market traders — food vendors, fabric sellers, phone repair shops, and artisans. Traders can receive instant payments in naira, track customer debts with tamper-proof records, and access everything through a web app or by dialling a USSD code from any basic phone. No BVN. No bank account. No smartphone required. Bitcoin runs in the background; traders see naira.


## Problem
Nigeria's informal traders deal with three daily problems:
Payments are broken. Bank transfers fail or take days. POS machines charge fees and go offline. Cash gets stolen or miscounted. A trader selling ₦50,000 on credit may never see that money.
No infrastructure for debt tracking. Most traders use exercise books or memory to track what customers owe. Notebooks get lost, memories fail, and customers dispute debts with nothing to prove otherwise.
Financial tools leave out the people who need them most. Every Nigerian fintech product requires a BVN, bank account, and smartphone — yet less than half of Nigerians own a smartphone. Millions of traders have been locked out of digital finance entirely.


## Solution
KoboSats gives every trader a self-custody Bitcoin Lightning wallet with two ways to access it:
For smartphone users — a React web app:
Enter an amount in naira, get a Lightning invoice QR code, customer pays in under 3 seconds. Includes a live balance dashboard, debt tracker with SMS reminders, transaction history with permanent receipt links, and support for English, Yoruba, Hausa, and Igbo.
For feature phone users — USSD via Africa's Talking:
Dial *384*7287# from any phone, on any network — no internet or app needed. Full menu in all four languages. Receive payments, check balance, and log debts from a ₦5,000 Nokia or a ₦300,000 iPhone.
For both — permanent records on Nostr:
Every payment and debt is signed with the trader's private key and published to decentralised relays worldwide. Tamper-proof and permanent — no company can alter or delete it.

## Technology Stack
React, Tailwind CSS, Python, FastAPI, SQLite/PostgreSQL, Breez Spark SDK, CoinGecko API, Africa's Talking, Nostr Protocol, BIP340 Schnorr, Render, Netlify.

## Team
Olowookere Busayomi - Backend developer
Timilehin Olajolo - Frontend Developer
Rita Okam - Backend Developer 


## Repository & Links
Frontend — https://github.com/Team-Lumina/KoboSat-frontend.git
Backend — https://github.com/Team-Lumina/KoboSat-Backend.git

## Status
ongoing

## Next Steps
— eCash: Add Cashu protocol so traders can send payment tokens via SMS with no internet needed on the recipient's end.
— Lightning Address: Give every trader a personal address like amara@kobosats.app for easier payment requests.
— Africa expansion: Ghana, Kenya, Tanzania — with local currencies, languages, and USSD shortcodes.
