# Smart Accounts

> Programmable wallets on the blockchain that make crypto simple.

---

## What Is a Smart Account?

A **Smart Account (SA)** is your personal smart contract on the blockchain. Unlike a regular wallet, it can:

- **Skip gas payments** — QR Wallet or stablecoins can cover the fee
- **Execute multiple actions at once** — e.g., approve + transfer in a single transaction
- **Work identically across all networks** — same address on Base, Arbitrum, Polygon, and others

> **Simple analogy:** A regular wallet is a key to your door. A Smart Account is a smart lock that can unlock with your fingerprint, let the delivery person in on schedule, and pay utilities automatically.

---

## How It Works

When you create a wallet in QR Wallet, **two** wallets are actually created:

```
┌─────────────────────────────────────┐
│  EOA (regular wallet)               │
│  Holds the private key              │
│  Signs operations                   │
│  → Owner of the Smart Account       │
└──────────────┬──────────────────────┘
               │ controls
┌──────────────▼──────────────────────┐
│  Smart Account (programmable wallet)│
│  Holds your funds                   │
│  Executes transactions              │
│  Can operate gaslessly              │
└─────────────────────────────────────┘
```

**EOA** (Externally Owned Account) is the "remote control." It signs operations but doesn't hold funds.

**Smart Account** is the "executor." It receives, holds, and sends funds. All your tokens live here.

---

## One Address — All Networks

Your Smart Account has the **exact same address** across all EVM networks:

| Network | Address |
|---------|---------|
| Base | `0xAbc...123` |
| Arbitrum | `0xAbc...123` |
| Polygon | `0xAbc...123` |
| Optimism | `0xAbc...123` |
| ... | `0xAbc...123` |

This is possible thanks to **CREATE2** technology — the address is mathematically derived from the owner's address, independent of any specific network.

> Anyone can send you tokens on any supported network — the address is always the same.

---

## Activating a Smart Account

Before sending transactions via SA, you need to **activate** it on each network where you want to use it. This is a one-time action — activate once, it works forever.

### Three Activation Methods

| Method | Who Pays | Where |
|--------|----------|-------|
| **Sponsored** | QR Wallet (free) | All L2 networks |
| **Self-pay** | User (native token) | Ethereum |
| **Gasless** | User (USDC/USDT) | When sponsored is unavailable |

### Activation Cost

| Network | Method | Approx. Cost |
|---------|--------|:------------:|
| Base | Sponsored | ~$0.02 (free for you) |
| Polygon | Sponsored | ~$0.01 (free for you) |
| Arbitrum | Sponsored | ~$0.03 (free for you) |
| BNB Chain | Sponsored | ~$0.05 (free for you) |
| Ethereum | Self-pay | ~$3.00 (you pay) |

> On L2 networks, activation costs pennies and QR Wallet covers it. On Ethereum, it's expensive due to high gas, so the user pays.

### Auto-Activation

You don't even need to activate SA manually! When someone **sends funds** to your SA address:

1. The app detects the incoming transfer
2. If the amount is ≥ $5 (≥ $1 on Polygon) — SA activates automatically
3. Everything happens in the background, no action required
4. Works on all L2 networks with sponsored activation support

---

## Activation Limits

The number of networks where you can activate SA depends on your tier:

| Tier | Activations |
|------|:-----------:|
| Free | 0 |
| Day | 1 network |
| Month | 2 networks |
| Year | 10 networks |
| Lifetime | 25 networks |

More on tiers: [Premium Tiers](../premium-and-rewards/premium-tiers.md)

---

## Technology

Smart Account in QR Wallet is built on the **ERC-4337 (Account Abstraction)** standard — an open Ethereum standard for programmable wallets.

We use audited **Alchemy LightAccount** contracts — a proven and secure solution deployed across all supported networks.

Deep dive: [ERC-4337 Deep Dive](../under-the-hood/erc-4337.md)

---

## FAQ

**Do I need to activate SA on every network?**
Only on those where you want to send transactions. You can receive funds without activation.

**Can I lose funds if SA isn't activated?**
No. Funds on the SA address are safe — activation is only needed for outgoing transactions.

**If SA is already activated, do I need to do anything again?**
No. Activation is a one-time action. Once deployed — it works forever.
