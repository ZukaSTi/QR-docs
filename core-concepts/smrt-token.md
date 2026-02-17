# $SMRT Token

> The native token of the QR Wallet ecosystem — earn it, use it, stake it.

---

## What Is $SMRT?

**$SMRT** (Smart Token) is the native utility token of QR Wallet. It powers the reward system, enables gas-free transactions, and aligns user incentives with the growth of the ecosystem.

| Parameter | Value |
|-----------|-------|
| **Name** | Smart Token |
| **Symbol** | SMRT |
| **Total Supply** | 10,000,000,000 (10 billion) |
| **Decimals** | 18 |
| **Standard** | ERC-20 |
| **Networks** | Base, Arbitrum, BNB Chain |

> The same contract address on all supported networks (deployed via CREATE2). Contract address will be published at official launch.

---

## Current Status: Beta ($SMRTS)

During the beta testing phase, QR Wallet uses a **synthetic token $SMRTS** (Smart Synthetic Token). It is fully equivalent to the future $SMRT in terms of functionality and mechanics:

- Same total supply (10 billion)
- Same distribution logic (Use2Earn, staking, etc.)
- Same smart contract architecture
- Deployed on Base mainnet for real-world testing

> **Important:** $SMRTS is a temporary beta token. It will lose its value at the moment of the official $SMRT launch. All earned $SMRTS balances will be converted to $SMRT at a 1:1 ratio.

**Estimated official launch: March 1, 2026** (preliminary date, subject to change).

---

## How to Earn $SMRT

$SMRT is distributed daily to active users through the **Use2Earn** model:

```
┌─────────────────────────────────────────┐
│          Daily Distribution Pool        │
│          2,500,000 SMRT / day           │
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
3. **$SMRT are distributed** — every day, 2.5 million tokens are split among all active users proportionally
4. **Claim on-chain** — tokens are available for claiming via a Merkle-proof smart contract

> Distribution runs for **2,000 days** from launch. Total Use2Earn allocation: **5 billion SMRT** (50% of supply).

---

## Utility — What Can You Do with $SMRT?

### 1. Smart Pay — Pay Gas with $SMRT

Instead of paying gas fees in native tokens (ETH, POL, BNB), you can pay with **$SMRT**:

- Works on all supported EVM networks
- Fee is auto-calculated at current exchange rate
- Supports same-chain and cross-chain payments

> No more juggling small amounts of native tokens across networks. One token for all fees.

### 2. Staking

Stake $SMRT to earn additional rewards from the staking pool (25% of total supply). Staking $500+ in USD value also gives a **+500 daily points bonus**.

### 3. Points Boost

Higher $SMRT staking balance → higher daily points limit → more $SMRT earned. A self-reinforcing cycle for active users.

### 4. Premium Benefits

$SMRT integrates with the premium tier system — active users who earn more $SMRT naturally get more benefits from higher point earnings.

---

## Distribution Mechanics

### On-Chain Contract

$SMRT distribution uses an audited smart contract with **Merkle tree-based claiming**:

```
┌──────────────┐     ┌──────────────────┐     ┌──────────────┐
│  Backend      │────▶│  Distribution    │────▶│  User Wallet │
│  calculates   │     │  Contract        │     │  receives    │
│  daily shares │     │  (Merkle proofs) │     │  $SMRT       │
└──────────────┘     └──────────────────┘     └──────────────┘
```

- **Cumulative claims** — you don't need to claim every day. Unclaimed tokens accumulate and can be collected at any time
- **Batch transfers** — the system can also send tokens directly to wallets (up to 300 recipients per batch)
- **Grace period** — 30 days after distribution ends to claim remaining tokens
- **Security** — pausable, access-controlled, reentrancy-protected (OpenZeppelin)

### Key Parameters

| Parameter | Value |
|-----------|:-----:|
| Daily distribution | 2,500,000 SMRT |
| Distribution period | 2,000 days |
| Claim grace period | 30 days |
| Max batch size | 300 recipients |
| Daily cap (on-chain) | 2,500,000 SMRT |

---

## FAQ

**When does distribution start?**

Estimated launch: **March 1, 2026** (preliminary, subject to change). From that date, 2.5 million $SMRT are distributed daily.

**How do I claim my $SMRT?**

Tokens appear in the app as "pending" balance. You can claim them on-chain at any time — no rush, they accumulate.

**Can I trade $SMRT?**

DEX and CEX liquidity is planned for launch. 5% of total supply is allocated for liquidity pools.

**What if I don't claim for a month?**

No problem. Claims are cumulative — your entire unclaimed balance is available whenever you decide to claim.

**Is $SMRT on multiple chains?**

Yes. The token will be deployed on Base, Arbitrum, and BNB Chain with the same contract address.

**What determines how much $SMRT I earn?**

Your daily points relative to all other users. More points = larger share of the 2.5M daily pool. See [Points System](../premium-and-rewards/points-system.md) for how to maximize your points.

**What happens to my $SMRTS from beta?**

All earned $SMRTS will be converted to $SMRT at a 1:1 ratio at official launch.
