# Key Management

> Your keys — only yours. We have no access to them.

---

## Self-Custody (Non-Custodial) Approach

[QR] wallet is a **self-custody (non-custodial)** wallet. This means:

- Private keys are stored **only on your device**
- [QR] wallet **cannot access** your keys
- [QR] wallet **cannot** freeze your funds
- No one but you **can** make a transaction

> **Comparison:** In custodial services (exchanges like Binance, Coinbase), your keys are held by the company. If they block your account — you lose access. In [QR] wallet, this cannot happen.

---

## How Keys Are Stored

```
┌──────────────────────────────────┐
│   Your Device                    │
│                                  │
│   ┌────────────────────────┐     │
│   │  Secure Storage        │     │
│   │  (Keychain / Keystore) │     │
│   │                        │     │
│   │  🔑 Private key        │     │
│   │  🔑 Mnemonic phrase    │     │
│   └────────────────────────┘     │
│                                  │
│   Protected by biometrics        │
└──────────────────────────────────┘
```

- **iOS:** Keychain with Secure Enclave protection
- **Android:** Android Keystore

Keys are **encrypted** and accessible only upon successful biometric authentication.

---

## Wallet Creation

When creating a wallet, a **mnemonic phrase** (seed phrase) of 12 or 24 words is generated. From it, the following are mathematically derived:

1. **EOA private key** — for signing transactions
2. **EOA public address** — for receiving funds
3. **Smart Account address** — computed from the EOA address

---

## Backup

The mnemonic phrase is the **only way to recover** your wallet. Store it:

- On paper in a secure location
- In a password manager (1Password, Bitwarden)
- **Never** in notes, messengers, or cloud storage

> If you lose your device and haven't saved the seed phrase — access to funds is lost forever. [QR] wallet cannot recover it.

---

## Wallet Import

You can import an existing wallet:

- **Mnemonic phrase** (12/24 words) — full import
- **Private key** — import a single account

---

## FAQ

**Can [QR] wallet see my private key?**

No. The key is stored in the device's Secure Storage and never leaves it.

**What if I lose my phone?**

Restore the wallet on a new device using your seed phrase. All funds intact.

**What if [QR] wallet shuts down?**

Your funds are on the blockchain — nobody can take them away. Recovery depends on where your funds are:

**The easiest way:** install [QR] wallet on any device, choose *Import wallet* and enter your seed phrase. Your EOA and Smart Account addresses come back exactly as before.

**EOA funds** — import your seed phrase into any EVM wallet (MetaMask, Rainbow, etc.). Use the same account index you used in [QR] wallet — the first account is index 0 (derivation path `m/44'/60'/0'/0/<index>`).

**Smart Account funds** (including staked positions in Aave and Compound) — your EOA key is the **sole owner** of the Smart Account. The SA address is computed deterministically from your EOA (CREATE2) with these parameters:

| Parameter | Value |
|---|---|
| Account type | Alchemy LightAccount v1.1.0 |
| Factory | `0x00004EC70002a32400f8ae005A26081065620D20` |
| EntryPoint | v0.6 — `0x5FF137D4b0FDCD49DcA30c7CF57E578a026d2789` |
| Salt | `0` |
| Owner | Your EOA address |

A tool or wallet that supports Alchemy LightAccount with these parameters computes the same Smart Account address and can operate it with your EOA key.

> **Why can't I see SA funds in MetaMask?** MetaMask shows EOA balances only. Your funds are not lost — the Smart Account is a separate address owned by your EOA.

> **Important:** "ERC-4337 support" alone is not enough — a Smart Account address depends on the account type, factory and salt. Use the parameters above. Your Smart Account is an on-chain contract — it exists as long as the blockchain exists.

**Solana funds** — import your seed phrase into any Solana wallet (Phantom, Solflare, etc.).

**Tron funds** — import your seed phrase into any Tron wallet (TronLink, etc.).

---

## What Self-Custody Does and Doesn't Mean

[QR] wallet never holds your keys. That protects you from us — but some things are outside any wallet's control:

| Layer | Who controls it |
|---|---|
| **Keys** | Only you — stored on your device |
| **Smart Account** | A contract that only your key can operate |
| **Tokens** | The token issuer. Some stablecoins (for example USDT and USDC) can be frozen by their issuer |
| **QR payments, cards, buying crypto** | Payment partners, who may delay or decline a payment under their rules |
| **App data on the device** | A cache. Logout removes it; everything is restored from the blockchain |

**Be careful with signatures:**
- Approving a token for a DApp lets that DApp spend the token. Only sign on sites you trust.
- Unknown tokens that suddenly appear in your wallet are often scams. Don't interact with them or visit links in their names.
