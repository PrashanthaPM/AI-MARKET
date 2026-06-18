# Smart Farmer Market Advisor

Smart Farmer Market Advisor is a full-stack web application that helps farmers decide where and when to sell crops for the best expected profit. It combines mandi price comparison, location-aware logistics, weather context, a rule-based recommendation engine, and an optional OpenAI-powered chat assistant.

## What is included

- React + Tailwind CSS frontend with a mobile-friendly farmer workflow
- Express backend with modular services and clean REST endpoints
- Real-time ready market fetcher with a fallback demo dataset for offline or sandboxed use
- AI/rule-based market ranking using price, trend, distance, transport cost, reliability, and weather risk
- Interactive price trend charts and market profit comparison charts
- OpenStreetMap + Leaflet map with nearby markets and the top market highlighted
- Multilingual UI support for English, Hindi, and Telugu
- Offline-friendly behavior with service-worker caching and local result persistence
- Optional SMS alert subscriptions and optional PostgreSQL persistence

## Architecture

```text
client/   -> React UI, Tailwind styling, charts, map, chatbot
server/   -> Express API, data services, recommendation engine, AI integration
```

## Key API endpoints

- `GET /api/health` health check
- `GET /api/markets` fetch market prices, ranking inputs, and trend data
- `POST /api/analysis` generate ranked recommendations and sell-now vs wait advice
- `GET /api/location/search?q=...` search manual locations
- `POST /api/chat` ask the farm advisor assistant follow-up questions
- `POST /api/alerts` register an SMS price alert subscription

## External integrations

- Mandi prices: configurable via `MANDI_API_BASE_URL` and `MANDI_API_KEY`
- Geocoding: Open-Meteo geocoding API
- Weather: Open-Meteo forecast API
- Maps: OpenStreetMap tiles rendered with Leaflet
- Chat assistant: OpenAI Responses API when `OPENAI_API_KEY` and `OPENAI_MODEL` are both set

If external APIs are not configured or are unreachable, the app automatically falls back to seeded market intelligence so the full product experience still works in demos and offline-friendly development.

## Setup

1. Install Node.js 20+.
2. Copy `.env.example` to `.env` and fill in any optional keys you want to enable.
3. Install dependencies:

```bash
npm install
```

4. Start the app:

```bash
npm run dev
```

5. Open:

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:4000`

## PostgreSQL schema

The backend includes [`server/src/db/schema.sql`](./server/src/db/schema.sql) for optional alert persistence. The app works without a database, but if `DATABASE_URL` is provided it will create the alert table automatically at startup.

## Recommended next steps

- Point `MANDI_API_BASE_URL` to your preferred live mandi price endpoint
- Add your OpenAI key/model to unlock free-form advisor chat
- Wire Twilio credentials for real SMS alerts
- Extend crop and market coverage with local mandi data from your region
