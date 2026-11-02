# $SMRT Token

> The native token of the [QR] wallet ecosystem — earn it, use it, stake it.

---

## What Is $SMRT?

**$SMRT** (Smart Token) is the native utility token of [QR] wallet. It powers the reward system, enables gas-free transactions, and aligns user incentives with the growth of the ecosystem.

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

During the beta testing phase, [QR] wallet uses a **synthetic token $SMRTS** (Smart Synthetic Token). It is fully equivalent to the future $SMRT in terms of functionality and mechanics:

- Same total supply (10 billion)
- Same distribution logic (Use2Earn, staking, etc.)
- Same smart contract architecture
- Deployed on Base mainnet for real-world testing

> **Important:** $SMRTS is a temporary beta token. It will lose its value at the moment of the official $SMRT launch. The points system will be reset and $SMRT distribution will start from scratch. $SMRTS tokens can be burned after the transition.

**Official launch (TGE):** the exact date is not announced yet.

---

## Claiming $SMRTS (Beta)

$SMRTS is allocated daily at **00:05 UTC**, based on the points you earned. Open **Rewards → SMRTS Claim** to claim it. Claiming is available in the **Android** app.

**Checklist before you claim:**

- [ ] Claims are on the **Base** network
- [ ] You have at least **100 $SMRTS** available
- [ ] Your wallet holds at least **$5** in other assets ($SMRTS excluded) — or you have **Premium**
- [ ] You have a little **ETH on Base** for gas (~$0.001–0.01)
- [ ] You haven't claimed in the last **24 hours**
- [ ] You haven't changed your **default address** in the last 24 hours
- [ ] Your app is updated to the latest version

**Messages and what they mean:**

| Message | What to do |
|---|---|
| Your balance is below $5 | Keep $5+ in other assets, or activate Premium |
| Minimum 100 SMRTs required | Wait until more $SMRTS accrue |
| One claim per 24 hours | Try again later |
| Claim unavailable for 24h after changing default address | Wait 24 hours after the change |
| Previous claim is still being processed | Wait for the previous claim to finish |
| Failed to prepare claim | Try again later |
| Restricted / not eligible | See below |

**Restricted from claiming.** Accounts flagged by our anti-abuse rules can't claim rewards. This affects **only reward claims** — your wallet, funds and all other features work as usual. If you believe it's a mistake, create a [support ticket](../welcome/support.md) and ask for a claim review.

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

1. **Earn points** — complete quests, pay with QR or card, swap, stake, use the app daily
2. **Points determine your share** — the more points you earn, the bigger your slice of the daily pool
3. **$SMRT are distributed** — every day, 2.5 million tokens are split among all active users proportionally
4. **Claim on-chain** — during beta, claim $SMRTS on Base (see [Claiming $SMRTS](#claiming-smrts-beta)). The $SMRT claim contract will be published at TGE

> Distribution runs for **2,000 days** from launch. Total Use2Earn allocation: **5 billion SMRT** (50% of supply).

---

## Utility — What Can You Do with $SMRT?

### 1. Smart Pay — Pay Gas with $SMRT

Instead of paying gas fees in native tokens (ETH, POL, BNB), Premium users can pay with **$SMRTS** (Smart Pay):

- Available on Base, Arbitrum, BNB Chain, Ethereum, Polygon, Optimism, World Chain, ApeChain and Solana
- Fee is auto-calculated at current exchange rate
- Does **not** consume your sponsored TX quota

> No more juggling small amounts of native tokens across those networks. See [Gas & Fees](gas-and-fees.md).

### 2. Staking

**Planned after TGE:** stake $SMRT to earn additional rewards from the staking pool (25% of total supply). Today, staking any supported assets worth $500+ gives a **+500 daily points bonus** — see [Staking](../features/staking.md).

### 3. Points Boost

**Planned after TGE:** higher $SMRT staking balance → higher daily points limit → more $SMRT earned.

### 4. Premium Benefits

$SMRT integrates with the premium tier system — active users who earn more $SMRT naturally get more benefits from higher point earnings.

---

## Distribution Mechanics

### On-Chain Contract (after TGE)

$SMRT distribution after TGE will use an audited smart contract with **Merkle tree-based claiming**:

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

The exact TGE date is not announced yet. From that date, 2.5 million $SMRT are distributed daily.

**How do I claim my $SMRT?**

After TGE, $SMRT accumulates and can be claimed at any time. During beta, $SMRTS is claimed as described in [Claiming $SMRTS](#claiming-smrts-beta).

**Can I trade $SMRT?**

DEX and CEX liquidity is planned for launch. 5% of total supply is allocated for liquidity pools.

**What if I don't claim for a month?**

No problem. Claims are cumulative — your entire unclaimed balance is available whenever you decide to claim.

**Is $SMRT on multiple chains?**

Yes. $SMRT will be deployed across all EVM networks supported by [QR] wallet. Initially on Base, Arbitrum, and BNB Chain — with other networks added over time.

**What determines how much $SMRT I earn?**

Your daily points relative to all other users. More points = larger share of the 2.5M daily pool. See [Points System](../premium-and-rewards/points-system.md) for how to maximize your points.

**What happens to my $SMRTS from beta?**

$SMRTS will lose its value at official launch. You will be able to burn your $SMRTS tokens. The project may organize a special activity for beta participants, but this is not guaranteed.
