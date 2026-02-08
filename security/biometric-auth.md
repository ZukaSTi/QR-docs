# Biometric Auth

> Every transaction is protected by your fingerprint or face.

---

## How It Works

Every critical action in QR Wallet requires **biometric authentication**:

- **Face ID** (iPhone)
- **Touch ID** (iPhone, iPad)
- **Fingerprint** (Android)
- **Face Recognition** (Android)

---

## What's Protected

| Action | Requires biometrics? |
|--------|:--------------------:|
| Send tokens | ✅ |
| Swap / Bridge | ✅ |
| Staking / Borrow | ✅ |
| Sign transaction in DApp | ✅ |
| Buy Premium | ✅ |
| View seed phrase | ✅ |
| Export private key | ✅ |
| Open app | Configurable |

---

## Why Biometrics?

A PIN or password can be observed, written down, or brute-forced. Biometrics offers:

- **Uniqueness** — your fingerprint / face can't be copied
- **Speed** — instant authentication
- **Convenience** — no passwords to remember
- **Hardware security** — data stored in Secure Enclave / TEE

---

## Important: Signing Order

In QR Wallet, biometrics is requested **before** transaction preparation, not after. This is intentional — to prevent Paymaster signature expiry.

```
1. User enters transaction details
2. → Biometrics ← (confirm first)
3. Prepare UserOperation
4. Request Paymaster
5. Sign
6. Send
```

---

## FAQ

**What if biometrics doesn't work?**

On devices without biometrics, the device PIN is used as fallback.

**Are my biometric data stored?**

No. QR Wallet does not store biometric data. Authentication is handled by the OS (iOS/Android) through a secure hardware module.
