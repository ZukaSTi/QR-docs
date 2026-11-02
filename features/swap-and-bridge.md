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
| **Uniswap V3** | Base, Ethereum, Arbitrum, Polygon, Optimism, World Chain, Monad, BNB Chain |
| **Jupiter** | Solana |
| **PancakeSwap V3** | BNB Chain (Android) |
| **LI.FI** | Cross-chain, EVM (Android) |
| **Rango** | Cross-chain, EVM + Solana + Avalanche (Android) |

### Supported Swap Networks

Base, Ethereum, Arbitrum, Polygon, Optimism, BNB Chain, World Chain, Monad, Solana. Avalanche — on Android.

**Not available for swap:** HyperEVM, Plasma, Stable, ApeChain, Taiko, Bitcoin, Dash, Tron.

Full list by network: [Network Feature Matrix](../supported-networks/feature-matrix.md).

---

## Bridge

Transfer tokens **between networks** — e.g., USDC from Ethereum to Base.

{% hint style="info" %}
Cross-chain swaps and bridges are available in the **Android** app.
{% endhint %}

### How It Works

Bridge is integrated directly into the Swap interface:

1. Select **FROM** network — e.g., Ethereum
2. Select **TO** network — e.g., Base
3. Select token and amount
4. Aggregator finds the best route through available bridges
5. Confirm — funds arrive on the destination network

### Cross-Chain Aggregators

- **Rango** — aggregates bridges and DEXes across EVM networks, Solana and Avalanche
- **LI.FI** — bridge and DEX aggregator for EVM networks

### Minimum Amount

For cross-chain swaps, amounts below **$1** may be inefficient — bridge fees can consume a large share. The app shows a warning; it is not a hard block.

---

## Fees

| Type | Fee |
|------|-----|
| **Swap (same-chain)** | DEX liquidity fee (varies by pool, often ~0.3%) |
| **Bridge (cross-chain)** | DEX/bridge fee + provider fee |
| **Gas** | Sponsored / Smart Pay (Premium) / Gasless / Self-pay |

> Gas is a separate network fee that can be covered by sponsored TX or Smart Pay.

---

## If a Swap or Bridge Is Stuck

A cross-chain swap has up to four steps. The transaction details show each step and its hash:

1. **Quote** — price and route. Nothing is sent yet.
2. **Source transaction** — your tokens leave the source network.
3. **Bridge** — the route provider moves the value between networks.
4. **Destination transaction** — the tokens arrive on the destination network.

**What to check:**

- Open the source transaction in the explorer. If it **failed**, nothing left your wallet except possibly gas.
- If it **succeeded**, the route is in progress. Bridges usually take a few minutes, sometimes longer.
- If the route can't complete, funds are returned on the **source** network — sometimes as an intermediate token (for example USDC instead of the token you started with). Check your balance on the source network before contacting support.
- Still nothing after an hour? Create a [support ticket](../welcome/support.md) with the source transaction hash.

**"Route unavailable"** — no provider can execute this pair or amount right now. Try a different amount, a different token, or a two-step route through USDC.

Routes are executed by the aggregators listed above. [QR] wallet does not hold your tokens during a route.

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
