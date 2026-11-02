# Smart Accounts

> Programmable wallets on the blockchain that make crypto simple.

---

## What Is a Smart Account?

A **Smart Account (SA)** is your personal smart contract on the blockchain. Unlike a regular wallet, it can:

- **Skip gas payments** — [QR] wallet or stablecoins can cover the fee
- **Execute multiple actions at once** — e.g., approve + transfer in a single transaction
- **Work identically across all networks** — same address on Base, Arbitrum, Polygon, and others

> **Simple analogy:** A regular wallet is a key to your door. A Smart Account is a smart lock that can unlock with your fingerprint, let the delivery person in on schedule, and pay utilities automatically.

---

## How It Works

When you create a wallet in [QR] wallet, **two** wallets are actually created:

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

> Anyone can send you tokens on any **Smart Account** EVM network — the address is always the same. Solana, Tron, Bitcoin, and Dash use different addresses. Avalanche and Taiko use the EOA.

---

## Which Address Is Which

| Term | What it is |
|---|---|
| **Wallet group** | Everything created from one secret phrase |
| **EOA (regular address)** | An address derived from your secret phrase. Pays its own gas |
| **Smart Account (SA)** | A contract wallet owned by your EOA. Can use sponsored gas, gasless and Smart Pay |

**Lite mode** (the default for new users) uses your Smart Account only — one address, nothing to choose. **Pro mode** (switch it in Profile → Lite / Pro) shows both addresses, lets you switch between them and hold several wallet groups.

| Action | Paid from | Gas |
|---|---|---|
| Send / swap from the Smart Account | Smart Account | Sponsored, gasless, Smart Pay or self-pay |
| Send / swap from the EOA | EOA | Self-pay in the native token |

{% hint style="warning" %}
Moving funds between your EOA and your Smart Account is a **real blockchain transfer**, not a display switch. Both addresses are yours — but funds sent to one don't appear on the other.
{% endhint %}

---

## Activating a Smart Account

Before sending transactions via SA, you need to **activate** it on each network where you want to use it. This is a one-time action — activate once, it works forever.

### Activation by Network

Activation is paid by [QR] wallet (sponsored). You never need a separate transfer to activate.

| Network | Activation | Auto-activates after a deposit of |
|---------|-----------|:---------------------------------:|
| Base, Arbitrum, Optimism, BNB Chain, World Chain, HyperEVM, Monad, Plasma, ApeChain, Stable | Sponsored | $5 or more |
| Polygon | Sponsored | $1 or more |
| Ethereum | Sponsored | $10 or more |
| Avalanche, Taiko, custom networks | No Smart Account — classic EOA | — |
| Solana, Bitcoin, Dash, Tron | Separate non-EVM addresses | — |

### Auto-Activation

You don't need to activate SA manually. When someone **sends funds** to your SA address:

1. The app detects the incoming transfer
2. If the amount reaches the threshold in the table above — SA activates automatically
3. Everything happens in the background, no action required

Free users activate through a deposit. Premium tiers also include activations that don't need a deposit (see below).

---

## Activation Limits

Premium tiers include activations that don't need a deposit:

| Tier | Activations |
|------|:-----------:|
| Free | 0 (activation after a deposit) |
| Premium 1 Month | 1 network |
| Premium 3 Months | 1 network |
| Premium 6 Months | 2 networks |
| Premium Black Month | 2 networks |
| Premium Black Year | 10 networks |
| Premium Ultra | 25 networks |

More on tiers: [Premium Tiers](../premium-and-rewards/premium-tiers.md)

---

## Technology

Smart Account in [QR] wallet is built on the **ERC-4337 (Account Abstraction)** standard — an open Ethereum standard for programmable wallets.

We use audited **Alchemy LightAccount v1.1.0** contracts with EntryPoint v0.6 — a proven and secure solution on Smart Account EVM networks (not Bitcoin, Dash, Avalanche, or Taiko). Recovery details: [Key Management](../security/key-management.md).

Deep dive: [ERC-4337 Deep Dive](../under-the-hood/erc-4337.md)

---

## FAQ

**Do I need to activate SA on every network?**

Only on those where you want to send transactions. You can receive funds without activation.

**Can I lose funds if SA isn't activated?**

No. Funds on the SA address are safe — activation is only needed for outgoing transactions.

**If SA is already activated, do I need to do anything again?**

No. Activation is a one-time action. Once deployed — it works forever.
