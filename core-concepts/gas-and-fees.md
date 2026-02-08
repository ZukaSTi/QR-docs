# Gas & Fees

> Three payment modes — from free to classic.

---

## What Is Gas?

**Gas** is the fee for executing an operation on the blockchain. Every action (transfer, swap, staking) requires network computational resources, and gas is the payment for them.

In traditional wallets, users **always** pay gas in the network's native token: ETH on Ethereum, POL on Polygon, BNB on BNB Chain, etc.

In QR Wallet — **three modes**.

---

## Mode 1: Sponsored (Free)

```
User → Transaction → Paymaster pays gas → Done
                      (QR Wallet)
```

- Gas is **fully paid by QR Wallet**
- User spends nothing — no tokens, no native currency
- Available within your daily limit (depends on Premium tier)
- Works on all L2 networks

**When used:** Always, when sponsored TX are available. The app automatically selects this as the priority mode.

---

## Mode 2: Gasless (Pay with Stablecoins)

```
User → Transaction → Paymaster pays gas → Deducts USDC/USDT from balance
```

- Gas is paid in **USDC or USDT** instead of native tokens
- Amount is automatically deducted from Smart Account balance
- Convenient when you don't have ETH/POL/BNB but have stablecoins

**When used:** If sponsored TX are exhausted and user has stablecoins.

---

## Mode 3: Self-pay (Classic)

```
User → Transaction → User pays gas in ETH/POL/BNB
```

- Classic method: gas paid in **native token**
- Gas cost shown before confirmation
- Always available as a fallback

**When used:** If no sponsored TX and gasless is unavailable.

---

## Selection Priority

The app automatically selects the **optimal** payment mode:

```
1. Sponsored  →  free TX available?       → YES → use it
                                          → NO  ↓
2. Gasless    →  stablecoins available?   → YES → use it
                                          → NO  ↓
3. Self-pay   →  native token available?  → YES → use it
                                          → NO  → insufficient funds
```

Users can always switch modes manually in the send interface.

---

## Gas Cost Comparison by Network

| Network | Typical Transfer Cost |
|---------|:--------------------:|
| Polygon | < $0.01 |
| Base | ~$0.01 |
| Optimism | ~$0.01 |
| Arbitrum | ~$0.02 |
| BNB Chain | ~$0.03 |
| World Chain | ~$0.01 |
| Solana | ~$0.001 |
| Tron | ~$1–3 (energy) |
| Ethereum | $1–10+ |

> On L2 networks, gas costs fractions of a cent — even in self-pay mode it's practically free. On Ethereum — significantly more expensive.

---

## FAQ

**Can I always use free TX?**
Yes, if your Premium tier provides sufficient daily limit. On Lifetime — up to 10 free TX per day (+ NFT bonuses).

**Why does gasless take USDC and not any token?**
Paymaster only accepts stablecoins (USDC, USDT) as payment — they have a stable exchange rate, which simplifies fee calculation.

**Does gas on Tron work differently?**
Yes. Tron uses an "energy" and "bandwidth" system instead of classic gas. USDT transfers on Tron require energy, which can be obtained by staking TRX.
