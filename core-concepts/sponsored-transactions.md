# Sponsored Transactions

> QR Wallet pays network fees for you. Free transactions are real.

---

## How It Works

Every blockchain transaction requires "gas" — a network fee. In most wallets, users pay gas themselves in native tokens (ETH, MATIC, BNB).

QR Wallet does it differently. When you send a transaction:

1. The app checks: do you have remaining sponsored TX?
2. If **yes** → QR Wallet pays the gas via **Paymaster**
3. If **no** → you're offered stablecoin or native token payment

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
| Polygon, BNB Chain | 3–7 seconds |
| Ethereum | 15–30 seconds |

---

## What Consumes a Sponsored TX?

| Action | Consumes TX? |
|--------|:------------:|
| Send tokens | ✅ |
| Swap | ✅ |
| Bridge (cross-chain) | ✅ |
| Staking | ✅ |
| Borrow | ✅ |
| Buy Premium | ✅ |
| Receive tokens | ❌ |
| SA Activation | ❌ (separate limit) |

---

## Daily Limit & Reset

- Counter resets **every day at 00:00 UTC**
- Unused TX **do not accumulate** — they expire at end of day
- Limit depends on Premium tier and NFT bonuses

### Limits by Tier

| Tier | Sponsored TX/day |
|------|:----------------:|
| Free | 0 |
| Day | 0 |
| Month | 3 |
| Year | 5 |
| Lifetime | 10 |

### NFT Bonuses to Daily Limit

| NFT | Extra TX/day |
|-----|:------------:|
| Hunter NFT | +1 |
| OG NFT | +2 |

**Example:** Year + Hunter NFT + OG NFT = 5 + 1 + 2 = **8 TX/day**

---

## Static TX

In addition to daily limits, you may have **static sponsored TX** — they **don't reset** daily. These are bonus TX earned through promotions, referral programs, and other activities.

**Spending priority:** daily TX are consumed first, then static.

---

## Supported Networks

| Network | Sponsored TX | Cost for QR Wallet |
|---------|:-----------:|:------------------:|
| Base | ✅ | ~$0.02 |
| Arbitrum | ✅ | ~$0.03 |
| Polygon | ✅ | ~$0.01 |
| Optimism | ✅ | ~$0.02 |
| BNB Chain | ✅ | ~$0.05 |
| World Chain | ✅ | ~$0.02 |
| HyperEVM | ✅ | ~$0.02 |
| Monad | ✅ | ~$0.02 |
| Plasma | ✅ | ~$0.02 |
| Ethereum | ✅ (temporary) | ~$3–10 |

> **Ethereum:** Sponsored transactions on Ethereum are available **temporarily until March 2026** as part of an early adopter promotion. After that, Ethereum will switch to self-pay/gasless mode due to high gas costs.

---

## What If TX Run Out?

You're **not locked out**. Three options:

1. **Gasless** — pay gas in USDC/USDT (stablecoins)
2. **Self-pay** — pay gas in native token (ETH, POL, BNB)
3. **Wait** — limit resets at 00:00 UTC

---

## FAQ

**Do failed transactions count?**

No. If a transaction fails, the sponsored TX is not consumed.

**Can I check my remaining balance?**

Yes — the Premium card in the app shows usage: `3/5 TX`.

**Does it work on Solana?**

Yes, Solana uses a separate fee sponsorship mechanism.
