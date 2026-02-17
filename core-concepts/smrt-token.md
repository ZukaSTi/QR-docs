# $SMRTS Token

> The native token of QR Wallet ecosystem — earn it, use it, stake it.

---

## What Is $SMRTS?

**$SMRTS** (Smart Synthetic Token) is the native utility token of QR Wallet. It powers the reward system, enables gas-free transactions, and aligns user incentives with the growth of the ecosystem.

| Parameter | Value |
|-----------|-------|
| **Name** | Smart Synthetic Token |
| **Symbol** | SMRTS |
| **Total Supply** | 10,000,000,000 (10 billion) |
| **Decimals** | 18 |
| **Standard** | ERC-20 |
| **Networks** | Base, Arbitrum, BNB Chain |
| **Contract** | `0x5afEc355Ab5ADCAF69434ed851BD28479D52ebBA` |

> The same contract address on all supported networks (deployed via CREATE2).

---

## How to Earn $SMRTS

$SMRTS is distributed daily to active users through the **Use2Earn** model:

```
┌─────────────────────────────────────────┐
│          Daily Distribution Pool        │
│          2,500,000 SMRTS / day          │
├─────────────────────────────────────────┤
│                                         │
│   Your daily share =                    │
│                                         │
│       Your Points Today                 │
│    ─────────────────────── × 2.5M       │
│     Total Points (all users)            │
│                                         │
└─────────────────────────────────────────┘
```

**Step by step:**

1. **Earn points** — complete quests, swap, send, stake, use the app daily
2. **Points determine your share** — the more points you earn, the bigger your slice of the daily pool
3. **$SMRTS are distributed** — every day, 2.5 million tokens are split among all active users proportionally
4. **Claim on-chain** — tokens are available for claiming via a Merkle-proof smart contract

> Distribution runs for **2,000 days** from launch. Total Use2Earn allocation: **5 billion SMRTS** (50% of supply).

---

## Utility — What Can You Do with $SMRTS?

### 1. Smart Pay — Pay Gas with $SMRTS

Instead of paying gas fees in native tokens (ETH, POL, BNB), you can pay with **$SMRTS**:

- Works on all supported EVM networks
- Fee is auto-calculated at current exchange rate
- Supports same-chain and cross-chain payments

> No more juggling small amounts of native tokens across networks. One token for all fees.

### 2. Staking

Stake $SMRTS to earn additional rewards from the staking pool (25% of total supply). Staking $500+ in USD value also gives a **+500 daily points bonus**.

### 3. Points Boost

Higher $SMRTS staking balance → higher daily points limit → more $SMRTS earned. A self-reinforcing cycle for active users.

### 4. Premium Benefits

$SMRTS integrates with the premium tier system — active users who earn more $SMRTS naturally get more benefits from higher point earnings.

---

## Distribution Mechanics

### On-Chain Contract

$SMRTS distribution uses an audited smart contract with **Merkle tree-based claiming**:

```
┌──────────────┐     ┌──────────────────┐     ┌──────────────┐
│  Backend      │────▶│  Distribution    │────▶│  User Wallet │
│  calculates   │     │  Contract        │     │  receives    │
│  daily shares │     │  (Merkle proofs) │     │  $SMRTS      │
└──────────────┘     └──────────────────┘     └──────────────┘
```

- **Cumulative claims** — you don't need to claim every day. Unclaimed tokens accumulate and can be collected at any time
- **Batch transfers** — the system can also send tokens directly to wallets (up to 300 recipients per batch)
- **Grace period** — 30 days after distribution ends to claim remaining tokens
- **Security** — pausable, access-controlled, reentrancy-protected (OpenZeppelin)

### Key Parameters

| Parameter | Value |
|-----------|:-----:|
| Daily distribution | 2,500,000 SMRTS |
| Distribution period | 2,000 days |
| Claim grace period | 30 days |
| Max batch size | 300 recipients |
| Daily cap (on-chain) | 2,500,000 SMRTS |

---

## FAQ

**When does distribution start?**

Official launch: **March 1, 2026**. From that date, 2.5 million $SMRTS are distributed daily.

**How do I claim my $SMRTS?**

Tokens appear in the app as "pending" balance. You can claim them on-chain at any time — no rush, they accumulate.

**Can I trade $SMRTS?**

DEX and CEX liquidity is planned for launch. 5% of total supply is allocated for liquidity pools.

**What if I don't claim for a month?**

No problem. Claims are cumulative — your entire unclaimed balance is available whenever you decide to claim.

**Is $SMRTS on multiple chains?**

Yes. The same token is deployed on Base, Arbitrum, and BNB Chain with the same contract address.

**What determines how much $SMRTS I earn?**

Your daily points relative to all other users. More points = larger share of the 2.5M daily pool. See [Points System](../premium-and-rewards/points-system.md) for how to maximize your points.
