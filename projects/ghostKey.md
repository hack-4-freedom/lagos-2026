# GhostKey

> Your Bitcoin shouldn’t die with you!

---

## Overview

GhostKey is a non-custodial Bitcoin inheritance solution built on a dead man's switch mechanism. It allows Bitcoin holders to ensure their on-chain assets are automatically transferred to a named heir if they become unreachable — no lawyer, no exchange, no middleman, and no technical knowledge required.

The product is built for everyday people. A user links their Bitcoin address, names who inherits, and taps once a month to say they are still here. If they stop tapping, a countdown begins. When it ends, the heir receives a notification with a claim link and can collect the Bitcoin directly — enforced by Bitcoin itself, not by GhostKey's servers.

The rules are encoded directly into a Taproot script on the Bitcoin blockchain. Even if GhostKey shut down tomorrow, an heir could still claim using only the pre-signed transaction.

---

## Problem

An estimated 3 to 4 million Bitcoin — worth hundreds of billions of dollars — is permanently lost because holders died without transferring access to their keys. This problem is worse in the Global South, where:

- Most people hold Bitcoin on custodial exchanges (Blink, Yellow Card, Binance). If they die, the account is locked with no inheritance path.
- Formal planning (lawyers, notaries, wills) is expensive and inaccessible for most families.
- Existing Bitcoin inheritance tools require technical setup — running a full node, understanding descriptors, managing seed phrases — that excludes most users.
- There is no simple, trustless, click-based way for an ordinary person in Lagos, Kano or Kwara to say: "when I'm gone, my Bitcoin goes to my daughter."

The result is that Bitcoin, designed to be sovereign money, becomes permanently unspendable the moment its holder dies — robbing families of value they were meant to receive.

---

## Solution

GhostKey removes every barrier between a Bitcoin holder and a secure inheritance setup:

**For the owner:**
- Paste a Bitcoin address from any self-custody wallet (Cake Wallet, Blue Wallet, Sparrow, hardware wallets)
- Enter the heir's phone number or email — the heir is never contacted during the owner's lifetime
- Choose how long to wait before the heir can claim (default: 3 months)
- Tap once a month to reset the clock, via a web link or a 1-sat Lightning payment

**For the heir:**
- Receives one message when the countdown expires — a claim link, nothing else
- Opens the link in any browser, follows guided steps, enters their Bitcoin wallet address
- The heir can broadcast the claim transaction using GhostKey
- No account required, no app download, no technical knowledge needed

**The guarantee:**
GhostKey uses a Taproot script with two spending paths:

```
or_d( pk(OWNER), and_v( v:pk(HEIR), older(N) ) )
```

The owner can spend at any time. The heir can spend only after N blocks have elapsed since the last check-in (OP_CSV / BIP68). Checking in moves the UTXO to a fresh vault address, resetting N. The keypath uses an unspendable NUMS internal key — both paths are explicit scripts with no hidden backdoors.

The server never holds keys. It holds one shard of an encrypted, pre-signed transaction — useless without the heir's shard, which is delivered only when the alarm fires.

---

## Technology Stack

**Backend — Rust**

| Crate | Purpose |
|---|---|
| `bdk_wallet 1.0` | Bitcoin wallet logic, UTXO management, descriptor building |
| `bdk_esplora` | Chain data via Esplora API — no Bitcoin Core required |
| `miniscript` | Taproot policy compilation (`or_d`, `and_v`, `older`) |
| `bitcoin` | Primitives — transactions, PSBTs, addresses, scripts |
| `bdk_bitcoind_rpc` (used by CLI for regtest / bitcoind-backed flows) |
| `chacha20poly1305`  `hkdf`, `sha2`, `subtle`, `base64` (at-rest encryption of heir contacts and notification payloads) |
| `lettre` (SMTP, rustls, tokio) — outbound email |

| `axum` | Async HTTP server for check-in API and vault management |
| `sqlx` + SQLite | Vault registry, check-in history, alarm events |
| `tokio` | Async runtime |
| `thiserror` | Domain error types across library crates |

**Frontend — TypeScript / React**

| Library | Purpose |
|---|---|
| React 18 + Vite | Component framework and build tooling |
| TypeScript | Type safety across the entire frontend |
| Tailwind CSS | Utility styling |

**Infrastructure**

| Tool | Purpose |
|---|---|
| Fly.io | Server deployment (see `fly.toml`) |
| Vercel | Frontend deployment (see `vercel.json`) |
| Docker | Containerised server build (see `Dockerfile`) |
| GitHub Actions: | cargo fmt, cargo clippy -D warnings, cargo test --workspace --locked on push/PR to main (.github/workflows/rust.yml) + a web.yml. Regtest e2e is gated behind --ignored and run manually.

**Bitcoin / Lightning integrations**

- **Esplora** — watch-only chain data, no full node required
- **Lightning (planned)** — 1-sat check-in payment via LNURL-pay; heir notification via Lightning address message
- **Nostr NIP-17 (planned)** — encrypted heir notification using gift-wrapped DMs; owner check-in reminders
- **ai onboarding for heir (planned)** - The hair my be a farmer. without any bitcoin knowlegde, this helps them understand whats happening better.

---

## Team

- Solo project — Jolade Okunlade (@jolah99) covers backend, frontend, and devops.
---

## Repository & Links

| | |
|---|---|
| **Repository** | https://github.com/Jolah1/ghostKey |
| **Live app** | https://ghostkeyapp.vercel.app |
| **Architecture** | [ARCHITECTURE.md](./ARCHITECTURE.md) |
| **Deployment guide** | [DEPLOY.md](./DEPLOY.md) |
| **Security policy** | [SECURITY.md](./SECURITY.md) |

---

## Status

**Alpha — testnet only.**

The cryptographic core is complete and tested end-to-end on regtest:

- [x] Taproot vault descriptor construction (`or_d` + `older` + NUMS keypath)
- [x] PSBT building and signing flow
- [x] OP_CSV relative timelock enforcement (BIP68)
- [x] Check-in via UTXO move to fresh vault address
- [x] Heir claim transaction broadcast
- [x] Watch-only server with SQLite vault registry
- [x] React dashboard with vault registration and check-in UI
- [x] Fly.io + Vercel deployment pipeline

Not yet production-ready:

- [ ] Server endpoint authentication (owner token)
- [ ] Heir notification fan-out (SMS / email / Lightning when alarm fires)
- [ ] Link-based heir claim UI (no account required)
- [ ] Esplora as default chain source (currently requires bitcoind RPC)
- [ ] PSBT export for hardware wallet / cold signing
- [ ] Multiple heirs (currently one heir per vault)
- [ ] Mainnet security review
- [ ] ai Integration

---

## Next Steps

**Immediate (complete before mainnet):**

1. **Server authentication** — issue a per-vault `owner_token` at registration; require it on all mutation endpoints. Without this, any client can reset check-in deadlines.

2. **Heir notification** — when an alarm fires, send the heir a single message (SMS via Termii or Africa's Talking for Nigerian numbers, or email) containing a claim link. This is the most critical missing feature — the inheritance system does not function without it.

3. **Heir claim page** — a browser-based flow, no account required. Heir opens the link, enters their Bitcoin address, and GhostKey broadcasts the pre-signed transaction.

4. **Esplora as default chain source** — swap `bdk_bitcoind_rpc` for `bdk_esplora`. Removes the Bitcoin Core dependency and makes the app accessible to users on any device.

5. **Replace descriptor input with address/xpub input** — the setup wizard currently asks for a raw Miniscript descriptor string. This should be generated internally from a pasted Bitcoin address or xpub.

**Short term (next development cycle):**

6. **Lightning check-in** — generate a unique LNURL-pay invoice per vault per month. Owner pays 1 sat from Blink, Yellow Card, or any Lightning wallet. Payment = check-in. Deliberate, human, impossible to automate accidentally.

7. **Nostr notifications (NIP-17)** — encrypted DM to owner as monthly check-in reminder; owner auth via Nostr key signing (no username/password).

8. **k-of-n heirs** — Miniscript supports threshold spending; expose this in the vault builder so a user can require 2-of-3 heirs to claim together.

9. **eCash (Cashu) support** — for amounts below practical on-chain fee thresholds, allow owners to pre-mint Cashu tokens that are released to the heir as part of the claim flow.

10. **Translations** — pidgin interfaces for the heir claim page. The heir may never have interacted with Bitcoin software before; the claim flow must be in their language.

