# QR Payments API

> Integrate crypto payments into your service via QR codes.

---

## Capabilities

- Create payment QR codes with specified amount and token
- Check payment status
- Receive incoming payment notifications (Webhooks)
- Support for all EVM networks, Solana, and Tron

---

## Create Payment

```bash
POST /v1/payments

{
  "amount": "10.00",
  "currency": "USDC",
  "network": "base",
  "merchant_id": "your-merchant-id",
  "order_id": "order-12345",
  "callback_url": "https://your-site.com/webhook"
}
```

**Response:**

```json
{
  "payment_id": "pay_abc123",
  "qr_code_url": "https://api.qr.xyz/qr/pay_abc123.png",
  "payment_address": "0x...",
  "amount": "10.00",
  "currency": "USDC",
  "network": "base",
  "status": "pending",
  "expires_at": "2026-02-08T12:00:00Z"
}
```

---

## Check Status

```bash
GET /v1/payments/{payment_id}
```

**Statuses:**

| Status | Description |
|--------|------------|
| `pending` | Awaiting payment |
| `confirming` | Transaction on blockchain, waiting for confirmations |
| `completed` | Payment confirmed |
| `expired` | Payment window expired |
| `cancelled` | Cancelled |

---

## Multi-Network Acceptance

A single payment can accept payment on **multiple networks** simultaneously:

```bash
POST /v1/payments

{
  "amount": "10.00",
  "currency": "USDC",
  "networks": ["base", "arbitrum", "polygon"],
  "merchant_id": "your-merchant-id"
}
```

The QR code shows the payer a network selection — they pay on whichever network they have funds.

---

## API Status

> QR Payments API is in **Early Access**. Functionality and response formats may change. To get access, submit a [partnership request](../for-partners/partnership-request.md).
