# Sponsored Transactions

> QR Wallet pays network fees for you. Free transactions are real.

---

## How It Works

Every blockchain transaction requires "gas" — a network fee. In most wallets, users pay gas themselves in native tokens (ETH, POL, BNB).

QR Wallet does it differently. When you send a transaction:

1. The app checks: do you have remaining sponsored TX?
2. If **yes** → QR Wallet pays the gas via **Paymaster**
3. If **no** → you're offered Smart Pay, stablecoin (gasless), or native token payment

> **Paymaster** is a smart contract that signs permission to pay gas on behalf of the user. The blockchain charges the Paymaster, not your wallet.

---

## Transaction Flow — Step by Step

Here's what happens under the hood when you tap "Send":

```
Step 1   Confirm action
          ↓
Step 2   Biometric authentication (Face ID / fingerprint)
          ↓
Step 3   Build UserOperation
          Description: to whom, how much, which network
          ↓
Step 4   Request Paymaster
          Sponsored → Paymaster signs that it will pay
          Smart Pay → fee paid in $SMRT (or supported tokens)
          Gasless   → fee calculated in USDC/USDT
          Self-pay  → gas calculated in native token
          ↓
Step 5   Sign UserOperation with your key
          Proof that you approved the operation
          ↓
Step 6   Send to Bundler
          Service that packages the operation into a transaction
          ↓
Step 7   Bundler submits transaction to blockchain
          ↓
Step 8   EntryPoint contract verifies and executes
          ↓
Step 9   Paymaster pays the gas (if sponsored)
          ↓
Step 10  Done! Funds delivered.
```

### Speed

| Network | Time |
|---------|------|
| Base, Optimism, Arbitrum | 2–5 seconds |
| Polygon, BNB Chain, Avalanche | 3–7 seconds |
| Ethereum | 15–30 seconds |

Bitcoin and Dash confirm on their own networks (typically minutes, depending on fees).

---

## What Consumes a Sponsored TX?

| Action | Consumes TX? |
|--------|:------------:|
| Send tokens | ✅ |
| Swap | ✅ |
| Bridge (cross-chain) | ✅ |
| Staking | ✅ |
| Borrow | ✅ |
| Buy Premium (crypto) | ✅ |
| Receive tokens | ❌ |
| SA Activation | ❌ (separate limit) |
| Smart Pay | ❌ (separate quota) |

---

## Daily Limit & Reset

- Counter resets **every day at 00:00 UTC**
- Unused TX **do not accumulate** — they expire at end of day
- Limit depends on Premium tier and NFT bonuses

### Limits by Tier

| Tier | Sponsored TX/day |
|------|:----------------:|
| Free | 0 |
| Premium 1 / 3 / 6 Months | 1 |
| Premium Black Month | 2 |
| Premium Black Year | 5 |
| Premium Ultra | 10 |

Free users also receive **1 welcome static TX** (does not reset daily).

### NFT Bonuses to Daily Limit

| NFT | Extra TX/day |
|-----|:------------:|
| Hunter NFT | +1 |
| OG NFT | +2 |

**Example:** Black Year + Hunter NFT + OG NFT = 5 + 1 + 2 = **8 TX/day**

---

## Static TX

In addition to daily limits, you may have **static sponsored TX** — they **don't reset** daily. These are bonus TX earned through promotions, referral programs, and other activities. The welcome TX for new users is static.

**Spending priority:** daily TX are consumed first, then static.

---

## Supported Networks

Sponsored transactions work on Smart Account networks (most EVM L2s, plus Ethereum and Solana via a separate fee sponsorship path).

They are **not** used on Bitcoin, Dash, Avalanche, or Taiko — those networks use native fees (or Smart Pay where available).

| Network | Sponsored TX |
|---------|:-----------:|
| Base | ✅ |
| Arbitrum | ✅ |
| Polygon | ✅ |
| Optimism | ✅ |
| BNB Chain | ✅ |
| World Chain | ✅ |
| HyperEVM | ✅ |
| Monad | ✅ |
| Plasma | ✅ |
| ApeChain | ✅ |
| Ethereum | ✅ |
| Solana | ✅ (separate mechanism) |
| Avalanche | ❌ (EOA / native fees) |
| Taiko | ❌ (EOA / native fees) |
| Bitcoin | ❌ |
| Dash | ❌ |
| Tron | ❌ (energy / bandwidth) |

---

## What If TX Run Out?

You're **not locked out**. Options:

1. **Smart Pay** — pay the fee in $SMRT (BNB Chain, Avalanche, Dash — more networks over time)
2. **Gasless** — pay gas in USDC/USDT (stablecoins)
3. **Self-pay** — pay gas in native token (ETH, POL, BNB, AVAX, DASH, BTC, …)
4. **Wait** — daily limit resets at 00:00 UTC

---

## FAQ

**Do failed transactions count?**

No. If a transaction fails, the sponsored TX is not consumed.

**Can I check my remaining balance?**

Yes — the Premium card in the app shows usage, for example `3/5 TX`.

**Does Smart Pay use my sponsored TX?**

No. Smart Pay has its own quota and does not consume sponsored TX.
