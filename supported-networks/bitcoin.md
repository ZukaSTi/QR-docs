# Bitcoin

> Native Bitcoin in [QR] wallet — balance, receive, and send.

---

## Overview

| | |
|---|---|
| **Native Token** | BTC |
| **Address** | Native Bitcoin address (separate from EVM) |
| **Explorer** | [mempool.space](https://mempool.space) |
| **Smart Account** | ❌ |
| **Sponsored TX** | ❌ |
| **Swap / Bridge** | ❌ |

Bitcoin is a UTXO network. It does **not** use ERC-4337 Smart Accounts. Fees are paid in **BTC**.

---

## What Works

- **Balance** — shown in the unified portfolio
- **Receive** — show your Bitcoin address / QR from the Receive screen
- **Send** — send BTC to another Bitcoin address

---

## What Does Not Work (Yet)

- **Swap** — you cannot swap BTC inside [QR] wallet
- **Bridge** — no in-app BTC ↔ EVM bridge
- **QR fiat payments** from the Bitcoin balance (use supported QR Pay networks instead)

To get BTC into other chains, send BTC out to an exchange or a dedicated bridge, then back to [QR] wallet on an EVM/Solana/Tron address.

---

## Fees

Network fee depends on Bitcoin congestion and the fee rate you confirm in the app. There is no sponsored / gasless path.

---

## Safety

Bitcoin addresses are **case-sensitive**. Copy them exactly from the app. Sending BTC to an EVM `0x…` address will lose funds.
