# Gas & Fees

> Four payment modes — from free to classic.

---

## What Is Gas?

**Gas** is the fee for executing an operation on the blockchain. Every action (transfer, swap, staking) requires network computational resources, and gas is the payment for them.

In traditional wallets, users **always** pay gas in the network's native token: ETH on Ethereum, POL on Polygon, BNB on BNB Chain, etc.

In [QR] wallet — **four modes**.

---

## Mode 1: Sponsored (Free)

```
User → Transaction → Paymaster pays gas → Done
                      ([QR] wallet)
```

- Gas is **fully paid by [QR] wallet**
- User spends nothing — no tokens, no native currency
- Available within your daily limit (depends on Premium tier)
- Works on Smart Account networks

**When used:** Always, when sponsored TX are available. The app automatically selects this as the priority mode.

More: [Sponsored Transactions](sponsored-transactions.md)

---

## Mode 2: Smart Pay

```
User → Transaction → Fee paid in $SMRT (or supported tokens) → Done
```

- Cover network fees **without holding the native gas token**
- Live today on **BNB Chain, Avalanche, and Dash**
- The list of networks **keeps growing**
- Uses a **separate quota** from sponsored TX — Smart Pay does not consume your free TX

**When used:** When you want to pay fees in $SMRT (or another supported token) instead of ETH/BNB/DASH.

---

## Mode 3: Gasless (Pay with Stablecoins)

```
User → Transaction → Paymaster pays gas → Deducts USDC/USDT from balance
```

- Gas is paid in **USDC or USDT** instead of native tokens
- Amount is automatically deducted from Smart Account balance
- Convenient when you don't have ETH/POL/BNB but have stablecoins

**When used:** If sponsored TX are exhausted and you have stablecoins on a Smart Account network.

---

## Mode 4: Self-pay (Classic)

```
User → Transaction → User pays gas in the native token
```

- Classic method: gas paid in **ETH, POL, BNB, AVAX, SOL, TRX, BTC, DASH**, depending on the network
- Gas cost shown before confirmation
- Always available as a fallback
- The only mode on networks without Smart Account sponsorship (Bitcoin, Dash, Avalanche, Taiko, Tron energy)

**When used:** If no sponsored TX and Smart Pay / gasless is unavailable.

---

## Selection Priority

The app automatically selects the **optimal** payment mode:

```
1. Sponsored  →  free TX available?       → YES → use it
                                          → NO  ↓
2. Smart Pay  →  supported on this network
                 and you choose it?       → YES → use it
                                          → NO  ↓
3. Gasless    →  stablecoins available?   → YES → use it
                                          → NO  ↓
4. Self-pay   →  native token available?  → YES → use it
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
| Avalanche | ~$0.02 |
| World Chain | ~$0.01 |
| Solana | ~$0.001 |
| Dash | low (native fee) |
| Bitcoin | varies with network congestion |
| Tron | ~$1–3 (energy) |
| Ethereum | $1–10+ |

> On L2 networks, gas costs fractions of a cent — even in self-pay mode it's practically free.

---

## FAQ

**Can I always use free TX?**

If your Premium tier provides a daily limit. On Ultra — up to 10 free TX per day (+ NFT bonuses).

**Does Smart Pay work everywhere?**

Not yet. It currently works on **BNB Chain, Avalanche, and Dash**. More networks are added over time.

**Why does gasless take USDC and not any token?**

Paymaster only accepts stablecoins (USDC, USDT) as payment — they have a stable exchange rate, which simplifies fee calculation.

**Does gas on Tron work differently?**

Yes. Tron uses an "energy" and "bandwidth" system instead of classic gas. USDT transfers on Tron require energy, which can be obtained by staking TRX.

**Do Bitcoin and Dash use Smart Accounts?**

No. They use classic addresses. You pay the native network fee (or Smart Pay on Dash).
