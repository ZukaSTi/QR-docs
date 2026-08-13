# Send & Receive

> Send crypto in seconds — as easy as a text message.

---

## Sending

### How to Send Tokens

1. **Select token** — from your token list or via search
2. **Select network** — which chain to send on (Base, Bitcoin, Dash, etc.)
3. **Enter address** — manually, paste from clipboard, address book, or scan a QR code
4. **Enter amount** — in tokens or USD
5. **Choose gas payment** — sponsored, Smart Pay, gasless, or self-pay (where available)
6. **Confirm** — via biometrics (Face ID / fingerprint)

On Smart Account networks, confirmation is typically 2–7 seconds on L2. Bitcoin and Dash follow their own confirmation times.

### Smart Features

- **Address book** — save frequently used addresses with names
- **Recent addresses** — last recipients always at hand
- **QR scanner** — built-in scanner for reading addresses and QR payments
- **Address validation** — warning when sending to a contract or unknown address

> **Never change letter case** on Solana, Tron, Bitcoin, or Dash addresses. They are case-sensitive. Only EVM addresses (`0x…`) are case-insensitive.

---

## Receiving

### How to Receive Tokens

1. Open the **Receive** screen
2. Pick the **network** if needed (EVM vs Bitcoin vs Dash vs Solana vs Tron)
3. Show the sender your **QR code** or copy your **address**

Networks that support [QR Payments](qr-payments.md) may show a QR Pay badge.

### Addresses by Network Type

| Type | Address | Format |
|------|---------|--------|
| EVM (Smart Account) | SA address | `0x...` (same across SA networks) |
| Avalanche / Taiko | EOA | `0x...` |
| Solana | Solana wallet | Base58 |
| Tron | Tron wallet | `T...` |
| Bitcoin | Bitcoin wallet | Native BTC address |
| Dash | Dash wallet | Starts with `X` |

---

## Supported Tokens

- **Native tokens**: ETH, POL, BNB, SOL, TRX, BTC, DASH, AVAX, HYPE, XPL, MON, APE, etc.
- **Stablecoins**: USDC, USDT, DAI on supported networks
- **ERC-20 / SPL / TRC-20**: any standard tokens
- **Custom tokens**: add by contract address on EVM

---

## Transaction History

All transactions are saved in history:

- **Status** — pending, confirmed, failed
- **Details** — amount, recipient, network, transaction hash
- **Explorer link** — open block explorer for each transaction
- **Filtering** — by network, operation type, date
