# Webhooks

> Receive payment notifications in real time.

---

## How They Work

When an event occurs (payment, confirmation, cancellation), QR Wallet sends an **HTTP POST** request to your `callback_url` with event details.

---

## Notification Format

```json
POST https://your-site.com/webhook

{
  "event": "payment.completed",
  "payment_id": "pay_abc123",
  "merchant_id": "your-merchant-id",
  "order_id": "order-12345",
  "amount": "10.00",
  "currency": "USDC",
  "network": "base",
  "tx_hash": "0xabc...",
  "status": "completed",
  "timestamp": "2026-02-08T11:30:00Z"
}
```

---

## Event Types

| Event | Description |
|-------|------------|
| `payment.pending` | Payment created, awaiting payment |
| `payment.confirming` | Transaction detected, awaiting confirmations |
| `payment.completed` | Payment confirmed and completed |
| `payment.expired` | Payment window expired |
| `payment.cancelled` | Payment cancelled |

---

## Verification

Every webhook is signed with a secret key. Verify the signature to protect against spoofing:

```bash
X-Webhook-Signature: sha256=HMAC_SIGNATURE
```

Compute HMAC-SHA256 of the request body with your webhook secret and compare with the header.

---

## Retry Policy

If your server doesn't respond `200 OK`, QR Wallet retries:

| Attempt | Delay |
|---------|-------|
| 1 | Immediately |
| 2 | 30 seconds |
| 3 | 5 minutes |
| 4 | 30 minutes |
| 5 | 2 hours |

After 5 failed attempts, the webhook is marked as `failed`.

---

## API Status

> Webhooks API is in **Early Access**. To get access, submit a [partnership request](../for-partners/partnership-request.md).
