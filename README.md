# PULSE — X Layer AI Intelligence Hub

> AI-powered DeFi trading intelligence platform built natively on X Layer

**Live Demo:** https://sammy-xxiv.github.io/pulse

**Agentic Wallet:** 0x6d08320ee7f76eaa2ce41c86f2aa3cfb7056ace9

---

## Overview

PULSE is a full-stack AI trading intelligence hub for the X Layer ecosystem. It combines real-time on-chain market data from OKX OnchainOS with Claude AI to deliver actionable trading intelligence, risk analysis, and seamless swap execution — all in one interface.

## Features

### Market Intelligence
Live token prices, 24h price changes, and volume data for X Layer tokens via OKX OnchainOS DEX API. Claude AI generates a real-time market brief with ecosystem-level analysis.

### AI Trading Signals
Claude analyzes live X Layer market data and generates BUY/SELL/HOLD signals for each token with specific reasoning. Signals update on every refresh.

### Token Scanner
Paste any X Layer token contract address to receive an instant AI risk report. Claude evaluates the token and returns a SAFE/CAUTION/DANGER verdict with a risk score out of 100.

### Portfolio Analyzer
Connect your OKX Wallet to view your X Layer holdings alongside live prices and 24h changes. Claude provides personalized portfolio analysis and rebalancing recommendations.

### Transaction Lens
Paste any X Layer transaction hash to get a plain-English explanation of what happened. Claude decodes the transaction and explains it to any user regardless of technical background.

### Swap — OnchainOS DEX
Execute real token swaps on X Layer with zero gas fees via the OKX DEX aggregator. Supports all major X Layer tokens with best-price routing across available liquidity sources.

---

## Technical Stack

| Layer | Technology |
|---|---|
| Frontend | Single-file HTML/CSS/JS — deployed on GitHub Pages |
| Backend | Cloudflare Worker — secure API proxy with HMAC-SHA256 signing |
| Market Data | OKX OnchainOS DEX API v6 |
| AI Analysis | Anthropic Claude Sonnet |
| Wallet | OKX Wallet — native EVM injection + X Layer chain switching |
| Chain | X Layer Mainnet (Chain ID: 196) |

## OnchainOS Integration

PULSE uses the following OnchainOS API endpoints:

- `/api/v6/dex/market/price-info` — Real-time token prices
- `/api/v6/dex/aggregator/quote` — Best-price swap quotes
- `/api/v6/dex/aggregator/swap` — Swap transaction construction
- `/api/v6/wallet/asset/all-token-balances-by-address` — Wallet balances
- `/api/v6/wallet/post-transaction/transaction-detail-by-txhash` — Transaction data
- `/api/v6/wallet/token/token-detail` — Token metadata for Scanner

All API keys are stored as Cloudflare Worker environment variables. No credentials are exposed in the frontend.

## Security

- All OKX API requests are signed server-side using HMAC-SHA256
- API keys stored as encrypted Cloudflare environment variables
- Frontend contains zero credentials
- Wallet signing happens client-side in the user's OKX Wallet — private keys never leave the device

## X Layer Ecosystem Fit

PULSE is built exclusively for X Layer mainnet. Every feature — prices, swaps, scanner, portfolio, lens — queries X Layer chain data. The swap module uses zero-gas execution native to X Layer. The platform fills a clear gap in the X Layer ecosystem: intelligent, AI-powered tooling that helps users understand and act on on-chain data.

---

Built by **SAMMY** for the OKX Build X Hackathon Season 2
