# Tradesarace

Tradesarace is a Next.js app that blends a crypto trading workspace with a Flappy-style betting mini-game. The Flappy run simulates PnL based on a wager and score, updating a wallet for guests (local storage) or authenticated users (server state).

## Features
- Wallet panel with total balance, available balance, and PnL messaging
- Flappy “Casino Run” with animated canvas, score-based payout curve, and responsive sizing
- Guest persistence via local storage, plus authenticated user state via API routes
- MUI theming and a dark workspace layout

## Tech Stack
- Next.js 15
- React 19
- MUI + Emotion
- D3 (for charts elsewhere in the app)
- Neon serverless (for data access)

## Getting Started
1. Install dependencies
```bash
npm install
```

2. Run the dev server
```bash
npm run dev
```

Open `http://localhost:3000` in your browser.

## Scripts
- `npm run dev` – start the dev server
- `npm run build` – build for production
- `npm run start` – run the production build
- `npm run lint` – lint the project

## Game Formula
The Flappy run uses an exponential reward curve:

```txt
delta = (bet * ((1.16 ^ score) - 1)) - bet
```

If score or bet is invalid, the wager is treated as a loss.

## Project Structure
- `app/` – Next.js app router pages
- `src/` – shared components, including the Flappy workspace
- `public/` – static assets
- `db/` – database-related files

## Local State
Guest users store wallet data in local storage under:
- `tradesarace_wallet_v1`
- `tradesarace_positions_v1`

## Environment
This project expects a `.env.local` file. See the existing `.env.local` for required variables.

## License
See `LICENSE`.
