# QR Payments

> Scan — pay. Crypto payments in everyday life.

---

## How It Works

[QR] wallet lets you pay real-world bills and merchants by scanning a **local payment QR code** and settling with crypto (typically stablecoins). The merchant receives **local fiat**.

1. Open the in-app scanner (or Pay QR)
2. Scan the merchant's QR code
3. The app detects country, currency, and amount
4. Choose which crypto to pay with
5. Confirm with biometrics
6. Merchant gets paid in local currency

You can also **create a QR code** to receive a crypto payment: pick token and network, optionally set an amount, then show or share the code.

---

## Supported Countries

| Country | Currency | Minimum payment |
|---------|:--------:|:---------------:|
| **Vietnam** | VND | 20,000 VND |
| **Thailand** | THB | 60 THB |
| **Philippines** | PHP | 60 PHP |
| **Indonesia** | IDR | 20,000 IDR |
| **Cambodia** | KHR | 4,500 KHR |
| **Mongolia** | MNT | 4,000 MNT |
| **Brazil** | BRL | 5 BRL |
| **Argentina** | ARS | 1,000 ARS |

Coverage continues to expand. Availability in a country can depend on local rails and verification.

---

## What You Pay With

Payments are settled from your wallet in **stablecoins** — USDC and USDT on the major networks — and in selected other tokens. The payment screen shows which tokens and networks you can pay with for the scanned QR code.

You do not need to hold the local fiat currency.

---

## Payment Limits

If a payment is refused, the app tells you which of these stopped it:

- **Your balance** — not enough of the selected token.
- **Amount limits** — every payment has a minimum and a maximum. Some tokens have a lower maximum per payment; the amount screen shows it.
- **Verification limits** — verification can raise your limits — see [Identity Verification](identity-verification.md).

If the amount is above the current limit, try a smaller amount or pay with a stablecoin.

---

## If a Payment Didn't Go Through

A QR payment has two parts: your crypto transfer on the blockchain, and the local-currency payout to the merchant. **A confirmed blockchain transaction means we received your crypto — it does not yet mean the merchant has been paid.**

Open the payment in **History** to see its status:

| Status | What it means | What to do |
|---|---|---|
| Processing payment | Your crypto is received; the payout to the merchant is in progress | Wait. Most payments finish within a few minutes |
| Completed | The merchant has been paid | Nothing |
| Payment failed | The payout to the merchant did not go through | Your payment will be refunded |
| Needs review | We need to check this payment manually | Wait, or open **Payment issue** in the payment details |
| Refunded | Your crypto has been returned | Check your wallet balance |

{% hint style="danger" %}
**Do not pay a second time** while the first payment is still processing or under review. If the merchant says the money hasn't arrived, show them the payment screen and tap **Payment issue** in the payment details.
{% endhint %}

### Refunds

- Refunds are sent to your wallet in **USDT** for the value of the payment at the time you paid.
- Each refund is checked by our team before it is sent.

### Charged Twice or Cancelled at the Till

Open each payment in History and check its status. Tap **Payment issue** on each one — every payment gets its own ticket. You can also file a **Dispute** from the payment details if goods or services were not received; attach up to 5 photos.

### Who Is Responsible

[QR] wallet receives your crypto, sends the payout order and refunds payments that did not go through. The local payment network delivers the money to the merchant's account. If a payment shows **Completed** but the merchant hasn't received it, report it with **Payment issue** — we will raise it with the payment network.

---

## Cashback

Eligible QR payments can earn **token cashback**. Rate depends on your Premium tier and NFTs. See [Cashback](cashback.md).

---

## Generating a QR Code (Receive)

1. Select token and network
2. Enter amount (optional)
3. Share the QR code — show on screen, save, or send

Works on supported EVM networks and Solana.

---

## FAQ

**Do I need a bank account in that country?**

No. You pay with crypto from [QR] wallet. The merchant is paid in local currency on their side.

**Is identity verification required?**

Some countries ask for a short identity check before the first payment. The app will prompt you if needed. See [Identity Verification](identity-verification.md).

**What if the QR is not recognized?**

Make sure it is a payment QR (not a random image) and that the country is in the list above. You can also paste the payload if the scanner cannot read it.

**My QR code has a fixed amount, but the app refuses it.**

Some merchant codes carry their own amount. Enter exactly the amount printed in the code.
