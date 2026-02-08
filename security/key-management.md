# Key Management

> Your keys — only yours. We have no access to them.

---

## Non-Custodial Approach

QR Wallet is a **non-custodial** wallet. This means:

- Private keys are stored **only on your device**
- QR Wallet **cannot access** your keys
- QR Wallet **cannot** freeze your funds
- No one but you **can** make a transaction

> **Comparison:** In custodial services (exchanges like Binance, Coinbase), your keys are held by the company. If they block your account — you lose access. In QR Wallet, this cannot happen.

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

> If you lose your device and haven't saved the seed phrase — access to funds is lost forever. QR Wallet cannot recover it.

---

## Wallet Import

You can import an existing wallet:

- **Mnemonic phrase** (12/24 words) — full import
- **Private key** — import a single account

---

## FAQ

**Can QR Wallet see my private key?**

No. The key is stored in the device's Secure Storage and never leaves it.

**What if I lose my phone?**

Restore the wallet on a new device using your seed phrase. All funds intact.

**What if QR Wallet shuts down?**

Your funds are on the blockchain. Use your seed phrase in any other EVM wallet (MetaMask, Rainbow, etc.) to access your EOA.
