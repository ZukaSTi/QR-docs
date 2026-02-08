# API Overview

> Public QR Wallet APIs for integrations and partners.

---

## Basic Info

| Parameter | Value |
|-----------|-------|
| **Base URL** | `https://api.qr.xyz` |
| **Format** | JSON |
| **Authentication** | API Key (for partners) |
| **Rate Limit** | Depends on API tier |

---

## Available APIs

### 1. QR Payments

Create and process QR codes for crypto payments. Ideal for integration into retail, e-commerce, and services.

[Learn more →](qr-payments-api.md)

### 2. Webhooks

Receive real-time event notifications — incoming payments, transaction confirmations, status changes.

[Learn more →](webhooks.md)

---

## Authentication

Use an API key in the header:

```bash
curl https://api.qr.xyz/v1/payments \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

Keys are issued after partner application approval: [Partnership Request](../for-partners/partnership-request.md)

---

## Status

> The API is in **Early Access**. We're actively expanding functionality. To get access, contact us via [partnership request](../for-partners/partnership-request.md).
