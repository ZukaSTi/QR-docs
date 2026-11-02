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
- Pay with **$SMRTS, AVAX or APE**
- Available with **Premium** on Base, Arbitrum, BNB Chain, Ethereum, Polygon, Optimism, World Chain, ApeChain and Solana
- Uses a **separate quota** from sponsored TX — Smart Pay does not consume your free TX

**When used:** When you choose to pay fees in $SMRTS (or another supported token) instead of the native token.

---

## Mode 3: Gasless (Pay with Tokens)

```
User → Transaction → Paymaster pays gas → Deducts a token from balance
```

- Gas is paid in a **supported token** (such as USDC or USDT) instead of the native token
- Amount is automatically deducted from Smart Account balance
- Available on Ethereum, Base, Arbitrum, Polygon, Optimism, BNB Chain and World Chain
- Works for supported tokens from the token list — not for native tokens or custom tokens you added yourself

**When used:** If sponsored TX are exhausted and you hold a supported token on one of these networks.

---

## Mode 4: Self-pay (Classic)

```
User → Transaction → User pays gas in the native token
```

- Classic method: gas paid in **ETH, POL, BNB, AVAX, SOL, TRX, BTC, DASH**, depending on the network
- Gas cost shown before confirmation
- Always available as a fallback
- The only mode on networks without Smart Account sponsorship (Bitcoin, Dash, Avalanche, Taiko, Tron)

**When used:** If no sponsored TX and Smart Pay / gasless is unavailable.

---

## Selection Priority

The app automatically selects the **optimal** payment mode:

```
1. Sponsored  →  free TX available?       → YES → use it
                                          → NO  ↓
2. Smart Pay  →  Premium, supported network
                 and you choose it?       → YES → use it
                                          → NO  ↓
3. Gasless    →  supported token?         → YES → use it
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
| Tron | paid in TRX (energy) |
| Ethereum | $1–10+ |

> On L2 networks, gas costs fractions of a cent — even in self-pay mode it's practically free.

---

## Four Different Costs

When you see a cost in the app, it is one of these:

| Cost | Paid to | When |
|---|---|---|
| **Network gas** | The blockchain | Every on-chain transaction |
| **Service fee** | Payment or card partner | QR payments, card top-ups, buying crypto — shown before you confirm |
| **Slippage** | Nobody — price movement | Swaps (default tolerance 0.5%) |
| **Exchange rate** | Built into the quote | Crypto → local currency |

## Same Name, Different Token

- **ETH on Base and ETH on Arbitrum are separate balances.** Moving between them is a bridge, not a transfer.
- **ETH ≠ WETH, SOL ≠ wrapped SOL.** Wrapped tokens can't pay gas.
- To pay gas yourself you need the **native token of that exact network**.

---

## FAQ

**Can I always use free TX?**

If your Premium tier provides a daily limit. On Ultra — up to 10 free TX per day (+ NFT bonuses).

**Does Smart Pay work everywhere?**

No. It works with Premium only on Base, Arbitrum, BNB Chain, Ethereum, Polygon, Optimism, World Chain, ApeChain and Solana.

**Why does gasless not take every token?**

The paymaster accepts only tokens from its supported list — they have reliable prices, which makes the fee calculation safe.

**Does gas on Tron work differently?**

Yes. Tron uses an "energy" and "bandwidth" system instead of classic gas. USDT transfers on Tron require energy, which can be obtained by staking TRX. Deposits to Tron are temporarily unavailable — see [Tron](../supported-networks/tron.md).

**Do Bitcoin and Dash use Smart Accounts?**

No. They use classic addresses. You pay the native network fee.
