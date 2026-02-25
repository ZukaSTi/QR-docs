# Solana Token Accounts (ATA)

> Why you need SOL for swaps — and what makes Solana different from EVM chains.

---

## EVM vs Solana: How Tokens Are Stored

On EVM chains (Ethereum, Base, Polygon), all token balances live inside a single smart contract. Your balance is just a number in a mapping — no extra accounts, no extra cost.

Solana works differently. Every token you hold requires a separate **Associated Token Account (ATA)** — a dedicated on-chain account that stores your balance of that specific token.

```
EVM (Ethereum, Base, Polygon):

  USDC Contract
  ┌──────────────────────────┐
  │  0xAlice  → 100 USDC     │   One contract,
  │  0xBob    → 50 USDC      │   all balances inside
  │  0xCarol  → 200 USDC     │
  └──────────────────────────┘

Solana:

  Alice's Wallet
  ├── SOL balance (native)
  ├── USDC ATA  → 100 USDC      Each token = separate account
  ├── BONK ATA  → 5,000 BONK    Each account = rent deposit
  └── JUP ATA   → 30 JUP
```

---

## What Is an ATA?

**ATA** stands for **Associated Token Account**. It's a unique on-chain account derived deterministically from your wallet address and the token mint address.

```
Your Wallet  +  USDC Mint   →   Your USDC ATA  (unique address)
Your Wallet  +  BONK Mint   →   Your BONK ATA  (unique address)
Your Wallet  +  JUP Mint    →   Your JUP ATA   (unique address)
```

Each ATA:

- Stores your balance for **one specific token**
- Must be **created** before you can receive that token
- Requires a one-time **rent deposit** in SOL

---

## What Is Rent?

Solana charges **rent** for storing data on-chain. Every account that occupies space on the blockchain must hold a minimum SOL balance to remain alive.

For a token account (ATA), the rent-exempt minimum is:

| | |
|---|---|
| **ATA rent** | **~0.00203928 SOL** |
| At SOL = $150 | ~$0.31 |

This is **not a fee** — it's a **refundable deposit**. If you close the token account later, the full rent amount is returned to your wallet.

---

## Why Can't [QR] Wallet Sponsor ATA Rent?

[QR] Wallet sponsors **transaction fees** — the cost of executing operations on the network (signature verification, compute units, priority fees).

ATA rent is fundamentally different from a transaction fee:

| | Transaction Fee | ATA Rent |
|---|---|---|
| **What it is** | Payment for execution | Deposit for storage |
| **Where SOL goes** | To validators | Into the new account |
| **Refundable?** | No | Yes (on account close) |
| **Per-operation?** | Every transaction | Once per token |

```
Sponsored by [QR] Wallet:
├── Transaction signature fee    (~0.000005 SOL)
├── Compute unit cost            (~0.0001 SOL)
└── Priority fee                 (variable)

NOT sponsored — paid by user:
├── ATA rent deposit             (~0.002 SOL per new token)
└── Locked IN the new account    (refundable on close)
```

Sponsoring rent would mean [QR] Wallet permanently locks its own SOL inside every user's token accounts. At scale, this is economically unsustainable — each new token a user receives would lock ~$0.30 of [QR] Wallet's funds indefinitely.

---

## When Do You Need Extra SOL?

ATA creation happens automatically during swaps and token receives. Here's when extra SOL is required:

### Scenario 1: SOL → Token Swap

When you swap SOL for any SPL token and don't yet have an ATA for that token:

```
Your SOL balance must cover:
┌─────────────────────────────────────────────┐
│  Swap amount              e.g. 1.000 SOL    │
│  + wSOL ATA rent              ~0.002 SOL    │  ← wrapping native SOL
│  + Output token ATA rent      ~0.002 SOL    │  ← if first time
│  + Transaction fee            ~0.000005 SOL  │
│  ─────────────────────────────────────────── │
│  Total needed             ≈  1.004 SOL       │
└─────────────────────────────────────────────┘
```

> **What is wSOL?** Solana DEXes like Jupiter work with SPL tokens, not native SOL. Your SOL is automatically **wrapped** into wSOL (an SPL representation) before the swap. This wrapping requires its own temporary ATA.

### Scenario 2: Token → Token Swap

If you swap USDC → BONK and don't have a BONK ATA, the swap will create one. You need SOL for the rent **even though you're swapping USDC, not SOL**.

```
USDC → BONK swap (first time receiving BONK):
┌──────────────────────────────────────────────┐
│  USDC balance             enough for swap    │
│  + SOL for BONK ATA rent      ~0.002 SOL    │  ← needed!
│  + SOL for transaction fee    ~0.000005 SOL  │
└──────────────────────────────────────────────┘
```

### Scenario 3: Receiving Tokens

When someone sends you a token you've never held, the ATA is typically created by the sender's transaction. However, some protocols may require the recipient to have an existing ATA.

---

## How Much SOL Should I Keep?

We recommend keeping **at least 0.01 SOL** as a buffer:

| Purpose | Cost |
|---------|------|
| ATA rent (per new token) | ~0.002 SOL |
| Transaction signature fee | ~0.000005 SOL |
| Priority fee (network congestion) | ~0.0001–0.001 SOL |
| Safety buffer | ~0.005 SOL |

> **Rule of thumb:** 0.01 SOL is enough for ~4 new token accounts and dozens of transactions.

---

## ATA Lifecycle

```
1. First swap or receive of Token X
   └── ATA created automatically → ~0.002 SOL locked as rent

2. Normal usage
   └── Send, receive, swap — ATA persists, no extra rent

3. Token balance reaches 0
   └── ATA still exists, rent still locked
   └── Ready for future receives — no re-creation needed

4. Close ATA (optional, manual)
   └── ~0.002 SOL returned to your wallet
   └── ATA deleted — must re-create to receive again
```

---

## Practical Example

Alice has 2.0 SOL and wants to swap 1.5 SOL → USDC for the first time.

```
Alice's wallet: 2.0 SOL, 0 USDC (no USDC ATA)

Step 1 — Build swap transaction
         Jupiter wraps 1.5 SOL → wSOL for the swap

Step 2 — ATA check
         Alice has no wSOL ATA → create it    (−0.002 SOL)
         Alice has no USDC ATA → create it    (−0.002 SOL)

Step 3 — Execute swap
         1.5 SOL swapped → USDC arrives in new ATA
         Transaction fee                       (−0.000005 SOL)

Step 4 — Cleanup
         wSOL ATA auto-closed                  (+0.002 SOL refund)

Result:  Alice has 0.498 SOL + USDC
         (0.002 SOL locked as USDC ATA rent)
```

---

## FAQ

**Why do I see "Insufficient SOL" when I have enough for the swap amount?**

Your balance must cover the swap amount **plus** ATA rent and transaction fees. Keep at least 0.003 SOL extra beyond the swap amount.

**Is rent a permanent cost? Can I get it back?**

Rent is fully refundable. Closing the token account returns the entire deposit to your wallet.

**Why doesn't this happen on Ethereum or Base?**

EVM chains store all token balances inside the token's smart contract — no extra accounts or deposits needed. Solana's account model requires explicit storage allocation.

**What is wSOL and why does it need an ATA?**

Wrapped SOL (wSOL) is an SPL token that represents native SOL. Solana DEXes operate on SPL tokens, so native SOL must be wrapped before swapping. The wSOL ATA is usually temporary — created for the swap and closed afterward, with rent refunded.

**Do I need SOL for every swap?**

Only if the swap involves a token you've never held before (no existing ATA). Once created, the ATA persists — future swaps of the same token pair require no extra SOL for rent.

**How do I reclaim SOL locked as ATA rent?**

To get your SOL back, you need to close unused token accounts (ATAs with zero balance). There are several public tools and services that help you do this (e.g. [Sol Incinerator](https://sol-incinerator.com), account closers in popular Solana wallets). [QR] Wallet is working on a built-in ATA manager that will let you review and close empty token accounts directly from the app — reclaiming locked SOL in one tap. Stay tuned for updates.

**What if I don't have any SOL at all?**

You won't be able to create new ATAs. If you need to receive a new token on Solana, first acquire a small amount of SOL (~0.01) via a cross-chain bridge or buy crypto feature.
