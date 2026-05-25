# Multi-Agent Stock Analyzer

A multi-agent AI system that performs deep stock analysis using live web search (RAG), real-time price data, and long-chain reasoning — powered by the Claude API.

## What it does

Enter any stock ticker and four specialized AI agents collaborate to produce a structured investment report:

| Agent | Role |
|-------|------|
| **Web Search Agent** | Retrieves live news and headlines using Claude's web search tool (RAG) |
| **Sentiment Agent** | Analyzes investor sentiment grounded in the retrieved news |
| **Fundamentals Agent** | Evaluates business strength using real price data from Yahoo Finance |
| **Synthesis Agent** | Combines all agent outputs into a final Buy / Hold / Sell verdict |

After the report is generated, a **follow-up chat interface** lets users ask questions about the analysis. The system maintains full conversation memory across turns, demonstrating multi-turn long-chain reasoning.

## Key technical features

- **Retrieval-Augmented Generation (RAG)** — Agent 1 retrieves real web data before any analysis begins, grounding downstream agents in current facts rather than training knowledge
- **Multi-agent collaboration** — Four agents run in sequence, each passing context to the next
- **Real price data** — Live price and daily change pulled from Yahoo Finance API
- **Conversation memory** — Full report context passed into every follow-up chat turn
- **Token tracking** — Displays tokens consumed per analysis session

## Tech stack

- Claude API (`claude-sonnet-4-20250514`)
- Claude web search tool (`web_search_20250305`)
- Yahoo Finance API (price data)
- Vanilla HTML/CSS/JS — runs entirely in the browser, no backend required

## Token usage

Each full analysis consumes approximately 3,000–6,000 tokens (4 agent calls + web search). Follow-up questions add ~500–1,000 tokens per turn.
 
## Disclaimer

This tool is for educational and demonstration purposes only. Nothing it produces constitutes financial advice.
