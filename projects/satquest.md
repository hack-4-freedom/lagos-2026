# SatQuest

This file documents the SatQuest project built during **Hack4Freedom Lagos 2026**.

---

## Overview

SatQuest is an open-source, mobile-first PWA (Progressive Web App) that teaches Bitcoin and Lightning through gameplay, built with a Nigerian lens. You pick an avatar, choose a username, and work through 26 levels mixing Match-the-Pair puzzles with timed Word Hunt challenges. Every level you complete earns you real satoshis. It works offline, installs on any phone, and does not need a bank account to get started.

---

## Problem

Most Bitcoin products out there were built for people who are already in the Bitcoin space. They assume you know the terminology, you have used a wallet before, and you already believe in what Bitcoin is. That is a small circle. If you look at global adoption numbers, only a tiny percentage of the world actually uses Bitcoin, and most of that percentage already came in through tech or finance. The knowledge has not spread far enough.

The bigger issue is the second mentality. Walk up to a regular person on the street in Lagos and say "come and do Bitcoin" and the first thing you get is suspicion. Not because Bitcoin is bad, but because they have never been taught what it actually is. Nobody caught them young. Nobody made it simple and fun before the noise and complexity arrived.

On top of that, Nigerians and people across the Global South are dealing with 25%+ annual inflation, frozen accounts, PayPal restrictions, SWIFT delays, and currencies that lose half their value within a year. Bitcoin is literally a solution to these problems, but people cannot benefit from something they do not understand and do not trust.

Yes, Bitcoin falls too. The price goes up and down, and anyone who tells you otherwise is not being honest. But there is a difference between an asset that falls and recovers and a currency that only goes one direction. The naira does not come back. Bitcoin has a fixed supply, no government can print more of it, and over its entire history the long-term direction has been up. That is not a guarantee, but it is a fundamentally different situation from holding a currency that is being inflated away every single year with no ceiling.

There is also a deeper side to Bitcoin that most people never even get to hear about. Bitcoin was built on the ideas of privacy, decentralization, and individual freedom. It was never meant to be another investment product. It was meant to give people control over their own money without needing permission from a bank, a government, or any third party. That vision is documented in the Bitcoin whitepaper and has been the foundation of the community from the beginning. But if you have never been introduced to Bitcoin the right way, you never get to that part. You just hear the noise and walk away.

---

## Solution

SatQuest is built around one idea: catch them young. If we can get this into schools, into secondary school classrooms, into the hands of children who are still forming their understanding of money, then by the time they grow up Bitcoin will not feel foreign or suspicious. It will just be something they already know.

The game makes Bitcoin education something people actually want to do. You do not need to already believe in Bitcoin to play. You do not need any prior knowledge at all. Zero. If you have never heard the word Bitcoin before in your life, you can pick up SatQuest and start learning from level one. You just need a phone. There are two game modes that rotate through the 26 levels:

- **Match**: tap a picture, tap its meaning. Vocabulary teaching through illustrated cards.
- **Word Hunt**: a timed puzzle every 4th level where you find real Bitcoin words hidden among legacy finance terms like bank, IBAN, and SWIFT. Beat the clock to earn sats.

Every level is rooted in real Nigerian life: Mama Titi's market savings, Emeka sending money to Aba, Dayo's account being frozen during EndSARS. By level 26, a player understands Bitcoin and Lightning better than most people who have held it for years. And the goal is not just to finish the game. The goal is that when someone walks away they have the basics. If they want to go deeper, they can. But at least the foundation is there. At least we have more people in the system who understand what Bitcoin actually is and why it matters.

Finishing a level earns real satoshis. Each player gets their own non-custodial Lightning wallet the moment they sign up. No bank account, no middleman.

---

## Technology Stack

**Frontend**
- Vite + React (PWA, installable on any phone, works offline)
- CSS Modules
- localStorage for progress, syncs to the backend when online

**Backend**
- NestJS 10 (TypeScript)
- PostgreSQL with TypeORM for persistent storage
- Breez SDK (Spark) for non-custodial Lightning wallets, one per player
- BIP-39 mnemonic generation for wallet recovery
- Deferred reward system: sats are queued per level and paid out on claim
- Global leaderboard ranked by lifetime sats, with best total time as tiebreaker

**Infrastructure**
- Frontend: Netlify
- Backend: Docker Compose
- Monorepo: `frontend/` + `backend/`

---

## Team

| Name | GitHub | Role |
|---|---|---|
| Stephanie Ademuyiwa | [@aizuanjeme](https://github.com/aizuanjeme) | Creator and maintainer |

---

## Repository & Links

- **GitHub:** https://github.com/aizuanjeme/satquest
- **Live demo:** coming soon
- **Live Test Link:** https://mainsatquest.netlify.app
- **Live Test Game Link:** https://satquests.netlify.app/

---

## Status

The frontend and backend are fully integrated. Players can create profiles, sync progress across devices, earn deferred sats rewards on level completion, claim payouts via Lightning, and appear on a real global leaderboard ranked by sats. The app is ready for deployment.

---

## Next Steps

- Add music and sound effects to make the game feel alive
- Encrypt player mnemonics at rest so wallets are properly secured before going live
- Launch the community leaderboard with real sats rankings visible to all players
- Expand game content to go deeper on Lightning Network and financial sovereignty topics
- Translations into Yoruba, Igbo, Hausa, and Pidgin so more people can play in their own language
- Live tournaments and quiz competitions where players go head to head, fastest finger style, with real sats as the prize. Once people see that there is something to win, curiosity does the rest. They will go back, study the levels, practice, and come back ready. That is Bitcoin education happening without anyone forcing it.
- An in-app store where players can spend their earned sats on perks, items, or rewards inside the game. Earning Bitcoin through gameplay and then using it inside the same app closes the loop and makes the whole experience feel real.
