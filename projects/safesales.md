

## Overview
Trustless, Zero-Custody Escrow for Social-Commerce in Nigeria — Works Wherever You Can Paste a Link.

SafeSale is a decentralized escrow layer designed for Instagram, WhatsApp, TikTok, X, and Telegram micro-sellers in West Africa. It enables zero-trust peer-to-peer commerce without relying on centralized custodians who can freeze accounts or seize funds.


## Problem
In Nigeria alone, millions of transactions happen weekly via DMs on Instagram and WhatsApp between parties who do not know each other.

Buyers live in fear of "pay-before-delivery" scams (where sellers disappear after receiving bank transfers).
Sellers live in fear of "delivery-before-payment" theft (where buyers refuse to pay or claim items never arrived).
Centralized escrow platforms charge massive fees and act as custodians, meaning they can freeze user funds, block accounts, and require extensive intrusive KYC that excludes informal merchants.

## Solution
SafeSale operates as a decentralized escrow wedge:

Zero Custodian: SafeSale does not hold your funds. Money is locked into a Cashu ecash token on a federated mint. SafeSale cannot freeze, seize, or intercept these funds.
Buyer Sovereign Control: The Cashu token is P2PK-locked (NUT-11) to a one-time Nostr public key generated locally in the buyer's browser at checkout. Only a signature from the buyer's private key can unlock and redeem the funds.
Open Identity & Reputation: Sellers register using their own Nostr identities. Storefront listings are published directly as Nostr kind 30018 events. Reputation is censorship-resistant, self-owned, and globally portable.


## Technology Stack
Backend: Node.js 
DB: PostgreSQL 
Frontend: React Js

## Team
Joy — Backend Engineer,
Feyisara — Frontend Engineer

## Repository & Links
https://github.com/JSE19/safe-sales
https://safe-sales-weld.vercel.app/

## Status
Still In Progress

## Next Steps
