# zappr

**Hack4Freedom Lagos 2026**

> Bitcoin you can talk to, in the language you think in.

---

## Overview

zappr is a self-custodial Bitcoin social + payments hub that unifies your Nostr
feed, a Lightning wallet, and an AI agent on a single screen — usable in any
language. Instead of juggling a separate social app, wallet app, and a wall of
English-only jargon, you read your feed, zap posts, check your balance, and send
payments by simply talking to an agent in English, Nigerian Pidgin, Yoruba,
Hausa, Swahili, and more.

A beginner can tap their fingerprint and get a working Lightning wallet plus a
Nostr identity in one step — no seed phrase to copy, no keys to lose.

---

## Problem

Getting onto Bitcoin and Nostr in the Global South means clearing several
barriers at once:

- **Fragmented** — your social identity (Nostr) and your money (Lightning) live
  in separate apps that don't talk to each other.
- **English-only** — wallets and clients assume English fluency, leaving out
  most first-language Pidgin, Yoruba, Hausa, and Swahili speakers.
- **Jargon wall** — newcomers face seed phrases, nsec/npub, NWC, and invoices
  with no plain-language guide.
- **False choice** — users are pushed to either give up custody for ease of use,
  or keep custody and wrestle with seed-phrase backups.

The result: tools built *for* people in Nigeria and the broader Global South are
often unusable *by* them.

---

## Solution

zappr collapses social, payments, and help into one surface:

- **Read** your Nostr feed in real time.
- **Zap** posts and send Lightning payments inline.
- **Ask** an AI agent — in your own language — to check your balance, zap a
  post, send sats, or explain what a "zap" even is.

Onboarding is seedless: a single WebAuthn passkey (Face ID / fingerprint)
deterministically derives both a Nostr identity and a Breez Liquid Lightning
wallet, so a first-time user is live in one tap. Power users keep their existing
setup via NIP-07 extension or direct nsec + NWC. Keys never leave the browser —
the server only ever proxies AI calls.

Payments stay accessible at the edges too: the agent can cash sats out to a
Nigerian bank account in NGN via a MavaPay offramp (currently on staging).

---

## Technology Stack

- **Framework:** Next.js 14 (App Router), TypeScript
- **Styling:** Tailwind CSS (neobrutalist theme)
- **Nostr:** `@nostr-dev-kit/ndk`
- **Lightning (bring-your-own):** `@getalby/sdk` (NWC — Alby, Mutiny, Primal)
- **Lightning (seedless):** `@breeztech/breez-sdk-liquid` (WASM)
- **Key derivation:** WebAuthn PRF → `@scure/bip32` (Nostr nsec) + `@scure/bip39`
  (Breez Liquid mnemonic)
- **Auth & vault:** WebAuthn PRF + AES-256-GCM in IndexedDB; tab-scoped
  sessionStorage
- **AI:** `@anthropic-ai/sdk` — Claude (server-side proxy only)
- **State:** Zustand
- **Fiat offramp:** MavaPay (sats → NGN bank payout, staging)

The only server-side secret is the Anthropic API key; Nostr keys and NWC strings
stay in the browser.

---

## Team

- **Abdullahi Salmat** ([@Salmatcre8](https://github.com/Salmatcre8))

---

## Repository & Links

- **Source:** https://github.com/Salmatcre8/zappr
- **Demo:** deployed on Vercel (staging) — run locally with `npm install`,
  set `ANTHROPIC_API_KEY` in `.env.local`, then `npm run dev`
  (see the repo README for the full setup and demo walkthrough).
- **License:** MIT

---

## Status

Working prototype, built during Hack4Freedom Lagos 2026.

Shipped:
- Unified Nostr feed + Lightning wallet + AI agent on one screen
- Four login paths: seedless passkey, biometric vault, NIP-07 extension, raw nsec
- Seedless onboarding via WebAuthn PRF (one tap → wallet + identity)
- Multilingual agent with confirm-before-send for payments, zaps, and posts
- MavaPay sats → NGN bank offramp through the agent (staging keys)

---

## Next Steps

- Move the MavaPay offramp from staging to production keys
- Add an NGN → sats onramp to complete the fiat round-trip
- Broaden language coverage and harden agent intent handling
- Custom domain + production deploy with per-origin passkey enrollment
- Wider device/browser testing for the WebAuthn PRF passkey flow
