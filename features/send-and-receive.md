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
2. Pick the **network** if needed (EVM vs Bitcoin vs Dash vs Solana)
3. Show the sender your **QR code** or copy your **address**

Networks that support [QR Payments](qr-payments.md) may show a QR Pay badge.

> **Tron:** deposits to Tron are temporarily unavailable. Don't send TRX or TRC-20 tokens to a [QR] wallet Tron address.

### Addresses by Network Type

| Type | Address | Format |
|------|---------|--------|
| EVM (Smart Account) | SA address | `0x...` (same across SA networks) |
| Avalanche / Taiko | EOA | `0x...` |
| Solana | Solana wallet | Base58 |
| Tron | Tron wallet (deposits temporarily unavailable) | `T...` |
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

---

## My Transfer Didn't Arrive

{% hint style="danger" %}
Do **not** delete the wallet, reinstall the app, or share your seed phrase as a first step. Your funds are on the blockchain, not in the app — and anyone asking for your seed phrase is a scammer.
{% endhint %}

Check in this order:

1. **Network.** The sender must use the same network you copied the address from. For example, USDT sent on BNB Chain to your address arrives on BNB Chain — not on Base. Switch the network in the wallet to see it.
2. **Address.** In Pro mode you can have a Smart Account and a regular (EOA) address. Make sure you are looking at the address the funds were sent to. See [Smart Accounts](../core-concepts/smart-accounts.md#which-address-is-which).
3. **Token.** If you received a token that isn't shown, add it by its contract address.
4. **Explorer.** Open the transaction hash in the network explorer. If it shows **Success** and the recipient is your address, the funds are yours — pull down to refresh the balance.
5. **Not in the explorer?** The transfer was never sent. Ask the sender or the exchange for the transaction hash.

**Sending to an exchange:** check the exchange's **minimum deposit** and whether it requires a **memo / tag**. A deposit below the minimum or without the required memo can only be recovered by the exchange's support.

**Still missing?** Create a [support ticket](../welcome/support.md) and attach the transaction hash.
