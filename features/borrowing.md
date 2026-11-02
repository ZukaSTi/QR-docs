# Borrowing

> Get liquidity without selling your tokens.

{% hint style="info" %}
Borrowing is available in the **Android** app, in Pro mode.
{% endhint %}

---

## What Is DeFi Borrowing?

**Borrowing** is getting tokens against your assets as collateral. You deposit collateral and receive a loan in stablecoins or other tokens.

Why? Say you have ETH and believe in its growth. But you need USDC now. Instead of selling ETH, you deposit it as collateral and get USDC — while **keeping your position** in ETH.

---

## How to Borrow

1. Go to the **Borrow** section
2. Select **network** and **market**
3. **Supply collateral** — e.g., ETH or WBTC
4. Select **token to borrow** — e.g., USDC
5. Enter amount — the system shows Health Factor
6. Confirm with biometrics

---

## Key Metrics

| Metric | Description |
|--------|------------|
| **Health Factor** | Position health. > 1 = safe, < 1 = liquidation |
| **LTV** (Loan-to-Value) | Loan-to-collateral ratio. E.g., 75% = borrowed $75 against $100 collateral |
| **Liquidation Threshold** | Threshold at which collateral can be liquidated |
| **Borrow APY** | Annual interest rate on the loan (you pay this) |

### Health Factor — Detailed

```
Health Factor = (Collateral × Liquidation Threshold) / Loan Amount

Example: ($1000 × 0.85) / $600 = 1.42 — safe ✅
```

| Value | Status | Color |
|-------|--------|-------|
| > 1.3 | Safe | 🟢 Green |
| 1.1 – 1.3 | Caution | 🟡 Yellow |
| 1.0 – 1.1 | Danger | 🔴 Red |
| < 1.0 | Liquidation | 🔴 Critical |

---

## Supported Protocols

| Protocol | Description |
|----------|------------|
| **AAVE** | Largest lending protocol, operates on 5 networks |
| **Compound** | One of the first DeFi protocols, stable and reliable |

---

## Supported Networks

Base, Ethereum, Arbitrum, Optimism, Polygon

---

## Token Types

**Collateral:** ETH, WBTC, USDC, USDT, DAI and other major tokens

**Borrowable:** Primarily stablecoins — USDC, USDT, DAI

---

## Position Management

After opening a loan you can:

- **Add collateral** — increase Health Factor
- **Withdraw some collateral** — if Health Factor allows
- **Repay partially** — reduce debt
- **Fully repay** — close the position

---

## FAQ

**What is liquidation?**

If collateral price drops significantly and Health Factor falls below 1, the protocol automatically sells part of your collateral to cover the debt. This protects lenders.

**What's the max LTV?**

Depends on the token. ETH is usually 80%, stablecoins up to 85%. We recommend not exceeding 60–70% for safety.

**How much does borrowing cost?**

Borrow APY is a variable rate, usually 2–8% annually for stablecoins. Depends on market demand.
