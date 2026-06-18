# 🌾 Smart Farmer Market Advisor

Smart Farmer Market Advisor is an AI-powered decision support platform designed to help farmers maximize profits by identifying the best market and time to sell their crops. The application combines real-time market intelligence, weather forecasting, transportation cost analysis, and AI-driven recommendations to provide actionable insights for farmers.

---

## 🚀 Features

### 📊 Market Price Intelligence

* Compare crop prices across multiple mandis (markets)
* Analyze historical price trends
* Identify high-profit selling opportunities

### 🤖 AI-Powered Recommendations

* Smart market ranking engine
* Profit estimation based on:

  * Market prices
  * Transportation costs
  * Distance to market
  * Price trends
  * Weather conditions
  * Market reliability

### 🌦 Weather-Aware Planning

* Real-time weather forecasts
* Weather risk assessment
* Harvest and selling strategy suggestions

### 📍 Location-Based Market Discovery

* Interactive map using OpenStreetMap and Leaflet
* Nearby mandi identification
* Distance and logistics calculations
* Highlighted best market recommendations

### 💬 AI Farm Assistant

* OpenAI-powered chatbot support
* Market-related queries
* Crop selling guidance
* Personalized recommendations

### 🌐 Multilingual Support

* English
* Hindi
* Telugu

### 📱 Farmer-Friendly Experience

* Responsive mobile-first design
* Offline-friendly functionality
* Cached market data for low-connectivity areas

### 🔔 Smart Alerts

* SMS notification support
* Price alerts for selected crops
* Future integration with messaging platforms

---

## 🏗 System Architecture

```text
smart-farmer-market-advisor/
│
├── client/        # React frontend
├── server/        # Express backend
├── public/        # Static assets
└── docs/          # Documentation
```

### Frontend

* React.js
* Tailwind CSS
* Recharts
* Leaflet Maps
* Responsive UI Components

### Backend

* Node.js
* Express.js
* REST APIs
* Recommendation Engine
* OpenAI Integration

---

## 📡 API Endpoints

### Health Check

```http
GET /api/health
```

Returns application health status.

### Market Data

```http
GET /api/markets
```

Fetches market prices, trends, and recommendation inputs.

### Market Analysis

```http
POST /api/analysis
```

Generates market rankings and sell-now vs wait recommendations.

### Location Search

```http
GET /api/location/search?q=location
```

Searches locations for market discovery.

### AI Chat Assistant

```http
POST /api/chat
```

Provides AI-powered farming and market assistance.

### Alert Subscription

```http
POST /api/alerts
```

Registers users for SMS price alerts.

---

## 🔗 External Integrations

| Service              | Purpose                |
| -------------------- | ---------------------- |
| Mandi API            | Live market price data |
| Open-Meteo Geocoding | Location search        |
| Open-Meteo Weather   | Weather forecasts      |
| OpenStreetMap        | Interactive maps       |
| OpenAI API           | AI chatbot assistance  |
| Twilio (Optional)    | SMS notifications      |

The application includes fallback datasets to ensure functionality even when external APIs are unavailable.

---

## ⚙️ Installation

### Prerequisites

* Node.js 20+
* npm or yarn

### Clone Repository

```bash
git clone https://github.com/PrashanthaPM/AI-MARKET.git
cd AI-MARKET
```

### Install Dependencies

```bash
npm install
```

### Configure Environment

Create a `.env` file from `.env.example` and configure optional API keys:

```env
OPENAI_API_KEY=
OPENAI_MODEL=
MANDI_API_BASE_URL=
MANDI_API_KEY=
DATABASE_URL=
```

### Start Development Server

```bash
npm run dev
```

Application URLs:

* Frontend: http://localhost:5173
* Backend: http://localhost:4000

---

## 🗄 Database Support

The project supports PostgreSQL for storing user alert subscriptions.

Schema file:

```text
server/src/db/schema.sql
```

If a `DATABASE_URL` is provided, required tables are automatically initialized during startup.

---

## 📈 Future Enhancements

* Live mandi integrations across India
* Crop demand forecasting using Machine Learning
* Voice-enabled farmer assistant
* WhatsApp notifications
* Regional language expansion
* Personalized farmer dashboards
* Government scheme recommendations
* Harvest planning and yield prediction

---

## 🎯 Project Goal

To empower farmers with data-driven insights that improve decision-making, reduce uncertainty, and maximize crop-selling profits through technology and AI.

---

## 👨‍💻 Developed By

**Priyanka M**
AI-MARKET Project – Smart Farmer Market Advisor
