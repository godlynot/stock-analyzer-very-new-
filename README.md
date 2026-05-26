# StockMind — Multi-Agent Stock Analyzer

A six-agent AI system that performs institutional-grade stock analysis using live web search (RAG), real-time price data, bull vs bear debate, and dynamic data visualizations — powered by the Claude API.

## Live demo

[godlynot.github.io/stock-analyzer-very-new-](https://godlynot.github.io/stock-analyzer-very-new-)

## How it works

Six specialized AI agents collaborate in sequence to produce a structured investment report:

| Agent | Role |
|-------|------|
| **01 — Web Search** | Retrieves live headlines and analyst opinions using Claude's web search tool. This is the RAG retrieval step — grounding all downstream agents in current facts rather than training knowledge. |
| **02 — Sentiment** | Analyzes investor sentiment based solely on the retrieved news data. Outputs a structured Bullish / Neutral / Bearish score. |
| **03 — Fundamentals** | Evaluates business strength using real-time price data from Yahoo Finance alongside live news context. |
| **04 — Bull Agent** | Constructs the strongest possible case for buying the stock. Argues from the data, not from bias. |
| **05 — Bear Agent** | Counters with the strongest case against. Identifies key risks and challenges the bull agent's assumptions directly. |
| **06 — Synthesis** | Acts as a senior fund manager. Weighs all five preceding agents and produces a final Buy / Hold / Sell verdict with confidence rating. |

After the report is generated, a **follow-up chat interface** lets users ask questions. The system passes the full report context into every turn, demonstrating multi-turn long-chain reasoning.

## Key technical features

- **Retrieval-Augmented Generation (RAG)** — Agent 01 retrieves real web data before any analysis begins, grounding all downstream reasoning in current information
- **Multi-agent collaboration** — Six agents run in sequence, each passing structured JSON context to the next
- **Bull vs Bear debate** — Two agents argue opposite sides before synthesis, mirroring how real investment committees operate
- **Real price data** — Live price, daily change, 30-day momentum, and 52-week range from Yahoo Finance API
- **Data visualizations** — Radar score profile, 30-day price chart, revenue growth bar chart, and 52-week range position (Chart.js)
- **Conversation memory** — Full report context passed into every follow-up chat turn
- **Token tracking** — Exact tokens consumed displayed per session

## Tech stack

| Layer | Technology |
|-------|-----------|
| AI agents | Claude API — `claude-sonnet-4-20250514` |
| RAG / web search | Claude web search tool — `web_search_20250305` |
| Price data | Yahoo Finance API |
| Visualizations | Chart.js 4 |
| Frontend | Vanilla HTML / CSS / JS — no framework, no backend |

## Token usage

Each full six-agent analysis consumes approximately 5,000–9,000 tokens across six API calls. Follow-up chat questions add ~500–1,000 tokens per turn.

## Running it

No installation required. The tool runs entirely in the browser.

1. Get an Anthropic API key from [console.anthropic.com](https://console.anthropic.com)
2. Open the [live demo](https://godlynot.github.io/stock-analyzer-very-new-)
3. Enter your API key and any stock ticker

Your API key stays in your browser only — it is never stored or transmitted anywhere except directly to the Anthropic API.

## Disclaimer

This tool is for educational and demonstration purposes only. Nothing it produces constitutes financial advice.
