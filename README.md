# PAYGRID

**Pay-per-request AI data APIs — no accounts, no API keys. Just USDC on Base.**

PAYGRID is a live x402-powered API server offering three AI data services. Agents and developers pay per request using USDC on Base mainnet via the [x402 protocol](https://x402.org).

## Live Endpoint

```
https://api.autopilotpr.com
```

## Endpoints

| Method | Path | Price | Description |
|--------|------|-------|-------------|
| `POST` | `/score/hotel` | $0.05 | Hotel readiness scoring — scrapes a property URL and returns structured signals |
| `POST` | `/critic/content` | $0.03 | Content QA — pass/fail with specific failure reasons |
| `POST` | `/intel/deal-flow` | $0.25 | M&A deal flow scan — criteria in, ranked matches out |

## Health Check

```bash
curl https://api.autopilotpr.com/health
```

## How It Works

1. Client sends HTTP request to an endpoint
2. Server responds with `402 Payment Required` + payment details
3. Client pays USDC on Base mainnet via x402
4. Server verifies payment and returns the data

No API keys. No accounts. No subscriptions.

## Stack

- Node.js + Express + `@x402/express`
- Coinbase Developer Platform (CDP) JWT auth
- Cloudflare Tunnel (permanent domain)
- Base mainnet USDC payments

## Built By

[AutoPilot PR](https://autopilotpr.com) — AI-powered growth systems for SMBs.
