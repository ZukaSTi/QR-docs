# Swap & Bridge

> Token exchange and cross-chain transfers — all in one interface.

---

## Swap

Exchange one token for another right in the wallet, without external sites.

### How It Works

1. Select **network** (Base, Arbitrum, Solana, etc.)
2. Select **FROM** token (what you give) and **TO** token (what you get)
3. Enter amount
4. Review quote: rate, slippage, fee
5. Confirm with biometrics

The app automatically finds the best route through multiple DEX aggregators.

### Supported DEXes

| Provider | Networks |
|----------|---------|
| **Uniswap V3** | Base, Ethereum, Arbitrum, Polygon, Optimism, World Chain |
| **PancakeSwap V3** | BNB Chain |
| **Jupiter** | Solana |
| **SunSwap** | Tron |
| **LI.FI** | Cross-chain (all EVM) |
| **Rango** | Cross-chain (all EVM + Solana + Tron) |

### Supported Swap Networks

Base, Ethereum, Arbitrum, Polygon, Optimism, BNB Chain, World Chain, Solana, Tron

---

## Bridge

Transfer tokens **between networks** — e.g., USDC from Ethereum to Base.

### How It Works

Bridge is integrated directly into the Swap interface:

1. Select **FROM** network — e.g., Ethereum
2. Select **TO** network — e.g., Base
3. Select token and amount
4. Aggregator finds the best route through available bridges
5. Confirm — funds arrive on the destination network

### Cross-Chain Aggregators

- **Rango** — aggregates 70+ bridges and DEXes, supports EVM + Solana + Tron
- **LI.FI** — bridge and DEX aggregator for EVM networks

### Minimum Amount

For cross-chain swaps, minimum amount is **$0.10**, as bridge fees can consume very small amounts.

---

## Fees

| Type | Fee |
|------|-----|
| **Swap (same-chain)** | 0.3% of amount |
| **Bridge (cross-chain)** | 0.3% + bridge fee |
| **Gas** | Sponsored / Gasless / Self-pay |

> Swap fee is the DEX liquidity fee. Gas is a separate network fee that can be covered by sponsored TX.

---

## Settings

- **Slippage** — default 0.5%, configurable
- **Deadline** — order lifetime
- **Price impact** — warning on high impact

---

## FAQ

**What if the rate changes during the transaction?**
Slippage protection — if price moves more than the allowed %, the transaction is rejected and you don't lose funds.

**Can I swap ETH for SOL?**
Yes. Cross-chain swap via Rango enables exchange between any supported networks.

**How long does a bridge take?**
Depends on the route — from 30 seconds (L2 → L2) to 15 minutes (Ethereum → L2).
