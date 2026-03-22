# GeoSignal — Geopolitical Market Intelligence System

A local ML/NLP pipeline that converts global news into actionable market signals — no external AI APIs.

**[▶ Live Demo](https://YOUR-USERNAME.github.io/geosignal)**

---

## What it does

GeoSignal ingests financial news headlines and runs them through a multi-step NLP pipeline to generate a **Geopolitical Tension Index (GTI)**, which feeds a **LightGBM model** predicting market direction, volatility spikes, and sector-level impact.

### Three modules

| Module | What it shows |
|--------|--------------|
| 🌍 Macro Map | Click any continent to see active geopolitical events and their bullish/bearish market bias |
| 📈 Stock Screener | Filter Indian equities by sector and NLP signal; geo-correlated momentum scoring per stock |
| 🤖 NLP Pipeline | Live simulation of the 4-step prompt chain with configurable prompt engineering techniques |

---

## ML / NLP Architecture

```
News Headlines (Reuters / Bloomberg style)
        │
        ▼
┌─────────────────────────────┐
│   NLP Pipeline (local)      │
│  ① Event Classification     │  ← Transformer-based
│  ② Sentiment Scoring        │  ← Few-shot prompted
│  ③ Narrative Clustering     │  ← Macro theme detection
│  ④ Structured JSON Output   │  ← LightGBM feature input
└─────────────────────────────┘
        │
        ▼
  Geopolitical Tension Index (GTI)
        │
        ▼
┌─────────────────────────────┐
│   LightGBM Model            │
│  • Volatility spike prob.   │
│  • Bullish / Bearish bias   │
│  • Macro risk shift score   │
└─────────────────────────────┘
        │
        ▼
  Interactive Dashboard
```

## Prompt Engineering Techniques Used

- **Zero-shot** — role-based instruction with no examples
- **Few-shot** — 3–5 labeled examples injected into context
- **Chain-of-Thought** — step-by-step reasoning for risk classification
- **Structured Output** — JSON schema enforcement for LightGBM feature extraction

---

## Running locally

No dependencies. No build step. No API keys.

```bash
# Clone the repo
git clone https://github.com/YOUR-USERNAME/geosignal.git
cd geosignal

# Option 1: just open in browser
open index.html

# Option 2: run a local server
python -m http.server 8000
# then visit localhost:8000
```

---

## Built by

**Kunal Kandpal** — MBA (Operations), VIT Chennai  
Previously: Project Management Executive at Mars Wrigley | Supply Chain Intern at Blackberry  
[LinkedIn](https://www.linkedin.com/in/kunal-kandpal-302302197)
