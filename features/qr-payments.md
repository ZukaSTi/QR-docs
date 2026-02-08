# QR Payments

> Scan — pay. Crypto payments faster than Apple Pay.

---

## How It Works

QR Wallet supports multiple QR payment formats:

### 1. QR Wallet Pay

Our own QR code format for instant crypto payments:

1. **Merchant** generates a QR code with amount and address
2. **Buyer** scans the code via the in-app camera
3. App automatically detects network, token, and amount
4. Buyer confirms with biometrics — payment goes through in seconds

### 2. Gaian Pay

Integration with the Gaian Pay system for point-of-sale payments:

- Scan merchant's QR code
- Automatic payment parameter detection
- Real-time confirmation and processing

### 3. Thai QR (PromptPay)

Support for the Thai EMVCo QR standard for PromptPay payments:

- QR code parsing per EMVCo standard
- Merchant info extraction
- CRC validation
- Payment processing via cryptocurrency

---

## Generating a QR Code

You can also **create a QR code** to receive payment:

1. Select token and network
2. Enter amount (optional)
3. Share the QR code — show on screen, save, or send

---

## Supported Networks

QR payments work on all supported networks:
- All EVM networks (Base, Arbitrum, Polygon, etc.)
- Solana
- Tron

The app automatically detects the network from the QR code and suggests the optimal payment route.
