# Multi-Chain

> Many blockchains. One wallet. One balance.

---

## The Idea

Cryptocurrencies exist on different blockchains — and usually each one requires its own wallet, its own gas token, its own interface. [QR] wallet **unifies everything** into a single app.

Your assets on Base, Ethereum, Solana, Bitcoin, Dash, and Tron — all displayed as a **single USD balance**.

New networks are added over time. You can also [add a custom EVM network](../features/custom-networks.md).

---

## Supported Networks

### EVM Networks

One family, one address format (`0x…`). On most EVM chains your **Smart Account address is the same**. Avalanche and Taiko currently use the classic EOA address (no Smart Account).

| Network | Native Token | Chain ID | Smart Account |
|---------|:------------:|:--------:|:-------------:|
| **Base** | ETH | 8453 | ✅ |
| **Ethereum** | ETH | 1 | ✅ |
| **Arbitrum** | ETH | 42161 | ✅ |
| **Polygon** | POL | 137 | ✅ |
| **Optimism** | ETH | 10 | ✅ |
| **BNB Chain** | BNB | 56 | ✅ |
| **World Chain** | ETH | 480 | ✅ |
| **HyperEVM** | HYPE | 999 | ✅ |
| **Plasma** | XPL | 9745 | ✅ |
| **Monad** | MON | 143 | ✅ |
| **Avalanche** | AVAX | 43114 | ❌ (EOA) |
| **ApeChain** | APE | 33139 | ✅ |
| **Taiko** | ETH | 167000 | ❌ (EOA) |

Details: [EVM Chains](../supported-networks/evm-chains.md)

### Other Networks

| Network | Native Token | Highlights |
|---------|:------------:|-----------|
| **Solana** | SOL | High speed, low fees, SPL tokens |
| **Tron** | TRX | Popular for USDT transfers, energy model instead of gas |
| **Bitcoin** | BTC | Balance, receive, and send. No swap |
| **Dash** | DASH | Instant-friendly UTXO network. Balance, receive, and send. Smart Pay supported |

---

## How Unified Balance Works

```
┌─────────────────────────────────────────┐
│          Your total balance: $1,234.56  │
├─────────────────────────────────────────┤
│  Base       $500.00  (USDC, ETH)        │
│  Bitcoin    $300.00  (BTC)              │
│  Solana     $250.00  (SOL, USDC)        │
│  Polygon    $100.00  (POL, USDT)        │
│  Dash        $50.00  (DASH)             │
│  Tron        $34.56  (TRX, USDT)        │
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
Choose a token → choose a network → enter address → send. The app determines which network the token is on. Bitcoin and Dash use their own address formats.

### Bridge
Need to move tokens between EVM / Solana / Tron? The built-in bridge lives in the swap interface. Bitcoin and Dash are **not** available for swap/bridge.

### Swap
Token exchange works both within a single network and across supported networks. More: [Swap & Bridge](../features/swap-and-bridge.md)

---

## Addresses

- **Most EVM networks** — one Smart Account address (`0x…`)
- **Avalanche & Taiko** — EOA address (`0x…`, same format, no Smart Account)
- **Solana** — separate Base58 address
- **Tron** — separate `T…` address
- **Bitcoin** — native BTC address
- **Dash** — native Dash address (starts with `X`)

> Addresses on Solana, Tron, Bitcoin, and Dash are **case-sensitive**. Copy them exactly as shown in the app.

More: [Send & Receive](../features/send-and-receive.md)
