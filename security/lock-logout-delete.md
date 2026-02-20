# Lock, Logout & Delete

> Three levels of protection — from a quick pause to a full reset.

---

## Overview

QR Wallet provides three distinct security actions, each with a clear purpose:

| Action | When to use | Your wallet data | Login required? |
|--------|------------|-----------------|----------------|
| **Lock** | Stepping away briefly | Everything preserved | Biometric to return |
| **Logout** | Ending your session | Wallet stays on device | Full re-authentication |
| **Delete Wallet** | Permanent reset | Everything erased | New wallet or import |

---

## Lock

**What it does:** Blocks the app screen. Your session stays alive.

**When it happens:**
- Automatically after a period of inactivity (configurable in Settings → Security → Auto-Lock)
- Automatically when the app is in the background longer than the auto-lock threshold
- You can also lock manually

**To unlock:** Use Face ID, Touch ID, fingerprint, or device passcode.

**What stays:**
- All wallet data, balances, tokens, transaction history — loaded and ready
- Backend session — no need to re-authenticate with the server
- All settings, theme, language

**Think of it as:** Locking your phone screen. Everything is exactly where you left it.

---

## Logout

**What it does:** Ends your backend session and clears in-memory data. Your wallet keys remain safely stored on the device.

**Where to find it:** Profile → Security → Log Out

**To get back in:** Authenticate with biometrics on the Login screen. The app restores your wallet from secure on-device storage and re-establishes the backend session.

**What stays:**
- Seed phrase and private keys (in device secure storage)
- All wallet groups (Group 1, 2, 3...)
- App settings (language, theme, auto-lock)

**What is cleared:**
- Backend session (JWT tokens)
- Cached balances, transaction history, token prices
- DApp sessions
- DeFi positions (staking, borrowing, trading)

**After logout you will see** the Login screen with your wallet address. You can:
1. **Authenticate with biometrics** — returns you to the same account with all wallet groups
2. **"Forgot wallet?"** — leads to the Delete option if you need a fresh start

> **Important:** After logout, you cannot create a new wallet. This prevents accidentally creating a second identity. To use a different wallet, delete the current one first.

**Think of it as:** Logging out of your banking app. Your account still exists, you just need to sign in again.

---

## Delete Wallet

**What it does:** Permanently erases all wallet data from the device. This cannot be undone.

**Where to find it:**
- Profile → Security → Delete Wallet
- Login screen → "Forgot wallet?" → Slide to confirm

**What is erased:**
- All seed phrases and private keys
- All wallet groups
- All cached data
- Backend session

**What you keep:**
- Nothing. The device is clean as if the app was just installed.

**After deletion** you will see the Welcome screen where you can:
1. **Create a new wallet** — generates a fresh seed phrase
2. **Import an existing wallet** — enter your seed phrase to restore

> **Critical:** Make sure you have backed up your seed phrase before deleting. Without it, your funds are permanently inaccessible. QR Wallet cannot recover your keys.

**Think of it as:** Factory-resetting your wallet. Start from zero.

---

## Quick Comparison

```
Lock       →  Screen locked  →  Biometric  →  Instant return
Logout     →  Session ended  →  Biometric  →  Wallet restored from device
Delete     →  Everything gone →  Seed phrase →  Full re-import needed
```

---

## FAQ

**Q: I logged out. Will I lose my imported wallets (Groups 2, 3, 4)?**
A: No. All wallet groups are stored in device secure storage. After re-authenticating, all groups are restored.

**Q: Can I create a new wallet after logout?**
A: No. After logout, you can only re-authenticate to your existing wallet or delete it first. This prevents accidental creation of multiple accounts.

**Q: What if my biometrics changed (new fingerprint)?**
A: Currently, you need to use the "Forgot wallet?" option to delete and re-import with your seed phrase. A seed phrase recovery option on the Login screen is planned.

**Q: Does auto-lock count as logout?**
A: No. Auto-lock only blocks the screen. Your session and all data remain intact. Just authenticate to continue.

**Q: What happens if I force-close the app after logout?**
A: When you reopen, you'll see the Login screen. Your wallet is safe — authenticate to restore.
