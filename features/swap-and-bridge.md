# Swap & Bridge

> Token exchange and cross-chain transfers — all in one interface.

---

## Swap

Exchange one token for another right in the wallet, without external sites.

### How It Works

1. Select **network** (Base, Arbitrum, Solana, Avalanche, etc.)
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
| **LI.FI** | Cross-chain (EVM) |
| **Rango** | Cross-chain (EVM + Solana + Tron) |

### Supported Swap Networks

Base, Ethereum, Arbitrum, Polygon, Optimism, BNB Chain, World Chain, Avalanche, Taiko, ApeChain, Solana, Tron

**Not available for swap:** Bitcoin, Dash.

### Isolated Networks

Same-chain swaps work; **cross-chain** routes are limited or unavailable:

Tron, Monad, Plasma, ApeChain

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

For cross-chain swaps, amounts below **$1** may be inefficient — bridge fees can consume a large share. The app shows a warning; it is not a hard block.

---

## Fees

| Type | Fee |
|------|-----|
| **Swap (same-chain)** | DEX liquidity fee (varies by pool, often ~0.3%) |
| **Bridge (cross-chain)** | DEX/bridge fee + provider fee |
| **Gas** | Sponsored / Smart Pay / Gasless / Self-pay |

> Gas is a separate network fee that can be covered by sponsored TX or Smart Pay.

---

## Settings

- **Slippage** — default 0.5%, configurable (including auto)
- **Deadline** — order lifetime
- **Price impact** — warning on high impact

---

## FAQ

**What if the rate changes during the transaction?**

Slippage protection — if price moves more than the allowed %, the transaction is rejected and you don't lose funds.

**Can I swap ETH for SOL?**

Yes, via a cross-chain route on supported pairs. You cannot swap to or from Bitcoin or Dash.

**How long does a bridge take?**

Depends on the route — from 30 seconds (L2 → L2) to 15 minutes (Ethereum → L2).
