# Dash

> Fast UTXO payments — live in [QR] wallet.

---

## Overview

| | |
|---|---|
| **Native Token** | DASH |
| **Address** | Native Dash address (starts with `X`) |
| **Explorer** | [explorer.dash.org](https://explorer.dash.org/insight) |
| **Smart Account** | ❌ |
| **Sponsored TX** | ❌ |
| **Swap / Bridge** | ❌ |
| **QR payments** | ✅ |

Dash is a UTXO network with InstantSend-style confirmations. It does **not** use EVM Smart Accounts.

---

## What Works

- **Balance** — in the unified portfolio
- **Receive** — Dash address / QR
- **Send** — to another Dash address
- **QR payments** — pay merchant QR codes with DASH, up to $200 per payment (see [QR Payments](../features/qr-payments.md))

---

## What Does Not Work

- **Swap** — no in-app DASH swap
- **Smart Account / sponsored TX** — classic send only

---

## Safety

Dash addresses are **case-sensitive** and start with **X**. Do not send DASH to an EVM, Bitcoin, or Solana address.
