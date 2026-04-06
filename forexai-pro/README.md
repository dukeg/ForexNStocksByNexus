# NEXUS·FX — Forex & Stocks AI Trading Intelligence

> A real-time AI-powered trading intelligence platform integrating live forex exchange rates, global stock market data, and Claude AI for profit opportunity analysis.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![AI](https://img.shields.io/badge/AI-Claude%20Sonnet-orange)

---

## ✨ Features

### 📊 Forex Intelligence
- **30+ currency pairs** with live simulated rate engine (±0.18% tick every 3.5s)
- **Universal converter** — convert any pair with mid-market rates
- **Quick Compare panel** — 6-pair simultaneous conversion
- **Searchable FX table** with animated sparkline trend charts
- **Favourites system** — star your most-used pairs

### 📈 Stocks & Indices
- **Major indices**: S&P 500, NASDAQ 100, Dow Jones, VIX, DXY Dollar Index
- **15 top stocks**: AAPL, MSFT, NVDA, GOOGL, TSLA, AMZN, META, JPM, GS + more
- **Sector heatmap**: 8 sectors with live performance colouring
- **Top Movers** sorted by absolute % change

### 🎯 AI Profit Opportunity Engine
- **20 forex pairs** scored every tick using:
  - Momentum score (24h rate change)
  - Volatility index (rolling standard deviation)
  - Equity correlation (S&P 500 risk-on/off signal)
  - Random walk component (simulating volume proxy)
- **BUY / SELL / HOLD** signals auto-generated
- **Top 5 leaderboard** ranked by composite score with trade reasons
- **Opportunity cards** — click any card to ask the AI for a full trade plan

### 🔗 FX / Equity Correlation Matrix
- 5×5 heatmap: major forex pairs vs S&P, NASDAQ, DXY, VIX, Gold
- Colour-coded from green (positive) to red (inverse correlation)
- Updates every tick

### 🤖 Claude AI Trading Analyst
- Full conversational intelligence via **Claude Sonnet** (Anthropic API)
- **Live market context** injected into every prompt:
  - Current FX rates snapshot
  - Index levels and % changes
  - Top 3 AI-scored opportunities
- **6 quick-prompt buttons** for common trading questions
- Responds with trade setups, entry/exit levels, macro analysis

### 🎨 Design
- Dark terminal aesthetic: deep navy/black with cyan + gold accents
- Syne + Syne Mono + Playfair Display typography
- Dual live ticker (FX + Equities)
- Animated sparklines, pulse indicators, gradient score bars
- Fully responsive

---

## 🚀 Quick Start

### Option 1 — Open directly
```bash
# Clone the repo
git clone https://github.com/dukeg/nexusfx.git
cd nexusfx

# Open in browser (no build step required)
open index.html
# or
start index.html   # Windows
xdg-open index.html  # Linux
```

### Option 2 — Local dev server
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# Then open: http://localhost:8080
```

---

## 🔑 API Key Setup

The AI chat agent requires an **Anthropic API key**.

The app is designed to run inside **Claude.ai** where the API is pre-authenticated. To run standalone:

1. Open `index.html` in a text editor
2. Find the `fetch('https://api.anthropic.com/v1/messages'` call
3. Add your API key to the headers:

```javascript
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'YOUR_ANTHROPIC_API_KEY',
  'anthropic-version': '2023-06-01'
}
```

Get your API key at: https://console.anthropic.com

---

## 📁 Project Structure

```
nexusfx/
├── index.html          # Main application (self-contained)
├── README.md           # This file
├── CHANGELOG.md        # Version history
├── LICENSE             # MIT License
└── .gitignore          # Git ignore rules
```

> The app is intentionally a **single HTML file** for portability. No build tools, no node_modules, no dependencies — just open and run.

---

## 📡 Data Sources

| Data | Source | Notes |
|------|--------|-------|
| Forex rates | Simulated engine | Seeded from real March 2026 mid-market rates |
| Stock prices | Simulated engine | Seeded from real March 2026 prices |
| AI analysis | Anthropic Claude Sonnet | Live API, requires key |
| Indices | Simulated engine | SPX, NDX, DJI, VIX, DXY |

**To connect real data**: Replace the simulation tick engine with calls to:
- [Frankfurter API](https://www.frankfurter.app) — free FX rates
- [Alpha Vantage](https://www.alphavantage.co) — stocks (free tier)
- [Yahoo Finance](https://finance.yahoo.com) — via proxy

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────┐
│                   NEXUS·FX v1.0                     │
├────────────┬────────────────────┬───────────────────┤
│  FX Engine │   Stocks Engine    │   AI Agent        │
│  ─────────  │   ──────────────   │   ─────────────   │
│  24 pairs  │   15 stocks        │   Claude Sonnet   │
│  Tick @3.5s│   5 indices        │   Live context    │
│  Hist[20]  │   8 sectors        │   Trade signals   │
├────────────┴────────────────────┴───────────────────┤
│              Opportunity Scoring Engine             │
│  Score = momentum(0.4) + volatility(0.35)          │
│        + equity_correlation(0.15) + noise(0.10)   │
├─────────────────────────────────────────────────────┤
│                   Render Layer                      │
│  Dual ticker · FX table · Stock movers · Corr matrix│
│  Top-5 leaderboard · Sparklines · Converter        │
└─────────────────────────────────────────────────────┘
```

---

## 🤝 Contributing

Pull requests welcome. For major changes, open an issue first.

```bash
git checkout -b feature/your-feature
git commit -m 'Add some feature'
git push origin feature/your-feature
```

---

## 📄 License

MIT © 2026 — NEXUS·FX Project

---

## ⚠️ Disclaimer

This application is for **educational and informational purposes only**. Simulated market data is not real. Do not make financial decisions based on this tool. Always consult a licensed financial advisor.
