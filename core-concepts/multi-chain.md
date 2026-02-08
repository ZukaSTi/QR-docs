# Multi-Chain

> 12 blockchains. One wallet. One balance.

---

## The Idea

Cryptocurrencies exist on different blockchains — and usually each one requires its own wallet, its own gas token, its own interface. QR Wallet **unifies everything** into a single app.

Your assets on Base, Ethereum, Solana, and Tron — all displayed as a **single USD balance**.

---

## Supported Networks

### EVM Networks (10)

One family, one standard, one Smart Account address:

| Network | Native Token | Chain ID |
|---------|:------------:|:--------:|
| **Base** | ETH | 8453 |
| **Ethereum** | ETH | 1 |
| **Arbitrum** | ETH | 42161 |
| **Polygon** | POL | 137 |
| **Optimism** | ETH | 10 |
| **BNB Chain** | BNB | 56 |
| **World Chain** | ETH | 480 |
| **HyperEVM** | HYPE | 999 |
| **Plasma** | XPL | 9745 |
| **Monad** | MON | 143 |

### Non-EVM Networks (2)

Separate blockchains with their own addressing and mechanics:

| Network | Native Token | Highlights |
|---------|:------------:|-----------|
| **Solana** | SOL | High speed, low fees, SPL tokens |
| **Tron** | TRX | Popular for USDT transfers, energy model instead of gas |

---

## How Unified Balance Works

```
┌─────────────────────────────────────────┐
│          Your total balance: $1,234.56  │
├─────────────────────────────────────────┤
│  Base       $500.00  (USDC, ETH)        │
│  Arbitrum   $300.00  (USDC, ARB)        │
│  Solana     $250.00  (SOL, USDC)        │
│  Polygon    $100.00  (POL, USDT)        │
│  Tron        $84.56  (TRX, USDT)        │
└─────────────────────────────────────────┘
```

The app automatically:
- Fetches balances from all networks in parallel
- Gets current token prices
- Sums everything into a single USD balance
- Updates on pull-to-refresh and periodically in the background

---

## Cross-Chain Operations

### Sending
Choose a token → choose a network → enter address → send. The app determines which network the token is on.

### Bridge
Need to move tokens between networks? The built-in bridge lets you transfer USDC from Ethereum to Base — right from the swap interface.

### Swap
Token exchange works both within a single network and across networks. More: [Swap & Bridge](../features/swap-and-bridge.md)

---

## One Address for All EVM Networks

Thanks to Smart Account and CREATE2, your address is **identical** across all 10 EVM networks. This means:

- One QR code for receiving on any EVM network
- Sender can choose the network without knowing details
- No need to share different addresses for different networks

> For Solana and Tron — separate addresses, as these blockchains use a different format.

---

## FAQ

**Do I need to switch networks manually?**
For viewing balance — no, everything is visible at once. For sending — you choose the network when creating a transaction.

**Can I receive tokens on a network where SA isn't activated?**
Yes. Funds will arrive at your address. SA activates automatically upon receiving ≥ $5.

**Which tokens are supported?**
All standard ERC-20 tokens on EVM networks, SPL tokens on Solana, TRC-20 on Tron. You can also add custom tokens by contract address.
