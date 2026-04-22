# Base Airdrop Simulator

A speculative tool that scores your Base network on-chain activity against Arbitrum-style airdrop criteria.

🔗 **Live site:** https://YOUR_USERNAME.github.io/base-airdrop-simulator

## Features

- 🔵 Enter any Base mainnet wallet address for instant analysis
- 📊 14-point scoring system modeled after the Arbitrum ARB airdrop
- 💰 USD value calculator with adjustable FDV ($1B–$20B) and airdrop % (5–20%)
- ⛓ Live on-chain data via public Base JSON-RPC (no API key required)
- 📈 Token value chart by point tier
- 🏆 Tier system: Bronze → Silver → Gold → Diamond

## How It Works

The simulator fetches data directly from the Base blockchain using public RPC endpoints:

| Data | Method |
|------|--------|
| ETH balance | `eth_getBalance` |
| Transaction count | `eth_getTransactionCount` (nonce) |
| Active months | Nonce comparison at monthly block checkpoints |
| Stablecoin inflows | `eth_getLogs` for USDC/USDT/DAI/WETH/cbETH transfers |
| Bridge detection | Transfer logs from L2StandardBridge |

## Scoring Criteria (Arbitrum Model Applied to Base)

| Criterion | Points |
|-----------|--------|
| Bridged to Base | 1 |
| Active 2+ / 6+ / 9+ distinct months | 1 each |
| 4+ / 10+ / 25+ / 100+ txs or contracts | 1 each |
| $10K / $50K / $250K+ tx volume | 1 each |
| $10K / $50K / $250K+ stablecoin inflows | 1 each |

**Minimum 3 points required for eligibility. Max 15 points.**

## Deploy to GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch** → `main` → `/ (root)`
4. Your site will be live at `https://YOUR_USERNAME.github.io/base-airdrop-simulator`

## Disclaimer

⚠️ **This is a speculative tool only.** Base has not announced a token or airdrop. This simulator applies Arbitrum's historical scoring model to Base network activity as a hypothetical exercise. Nothing here constitutes financial advice.

Built by [@traderibo123](https://x.com/traderibo123)
