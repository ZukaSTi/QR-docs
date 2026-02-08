# Architecture

> How QR Wallet is built inside — for the curious and developers.

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| **Mobile App** | React Native + Expo |
| **State Management** | Zustand |
| **Web3** | viem, permissionless.js |
| **Navigation** | expo-router |
| **Blockchain** | ERC-4337 Account Abstraction |
| **Infrastructure** | Alchemy (RPC, Bundler, Paymaster) |
| **Security** | Biometric + Secure Enclave |

---

## Modular Architecture

QR Wallet is built on a **modular architecture** — each feature is isolated in its own module with clear layers:

```
modules/{feature}/
├── domain/          ← Pure business logic and types
├── infrastructure/  ← API, storage, external services
├── application/     ← State management and facades
└── ui/              ← React components (UI)
```

### Layers

| Layer | Responsibility | Example |
|-------|---------------|---------|
| **Domain** | Types, interfaces, business rules | `Swap.entity.ts`, `StakingPool` |
| **Infrastructure** | API calls and external services | `SwapApi.ts`, `AlchemyPaymaster` |
| **Application** | State, UI logic, facades | `useSwapFacade.ts`, `SponsoredTxStore` |
| **UI** | Visual components | `SwapScreen.tsx`, buttons, cards |

### Import Rule

```
UI → Application → Domain & Infrastructure → Domain
```

UI never talks to Infrastructure directly — only through the Application layer. Domain is pure, with zero dependencies.

---

## Chain Abstraction

Working with different blockchains is unified through an abstraction layer:

```
┌──────────────────────────────────────┐
│            Chain Core                 │
│                                      │
│  ┌──────────┐ ┌──────┐ ┌──────────┐ │
│  │   EVM    │ │Solana│ │   Tron   │ │
│  │ Provider │ │Provid│ │ Provider │ │
│  └──────────┘ └──────┘ └──────────┘ │
│                                      │
│  ChainRegistry → ChainConfigProvider │
│                                      │
│  Unified interface for all operations│
└──────────────────────────────────────┘
```

- **ChainRegistry** — registry of all supported networks
- **ChainConfigProvider** — configuration and capabilities per chain
- **TransactionService** — unified TX sending (EVM, Solana, Tron)

---

## Account Abstraction Stack

```
┌──────────────────────────────────────────────┐
│                User                           │
│          (biometrics → signature)             │
└──────────────────┬───────────────────────────┘
                   ↓
┌──────────────────┴───────────────────────────┐
│          IAccountProvider                     │
│    Build UserOperation                        │
│    (sender, nonce, callData, initCode)        │
└──────────────────┬───────────────────────────┘
                   ↓
┌──────────────────┴───────────────────────────┐
│          IPaymaster                           │
│    Gas sponsorship                            │
│    (paymasterAndData, gas estimates)          │
└──────────────────┬───────────────────────────┘
                   ↓
┌──────────────────┴───────────────────────────┐
│          IBundler                             │
│    Submit to blockchain                       │
│    (sendUserOperation → waitForReceipt)       │
└──────────────────┬───────────────────────────┘
                   ↓
┌──────────────────┴───────────────────────────┐
│          EntryPoint (on-chain)                │
│    Validate → Execute → Pay gas               │
└──────────────────────────────────────────────┘
```

Three interfaces (`IAccountProvider`, `IPaymaster`, `IBundler`) abstract away the specific provider. Currently using Alchemy, but the architecture allows switching to any provider without changing business logic.

---

## Token Registry

A single registry for all tokens in the system:

```typescript
// Each token is described once
{
  symbol: 'USDC',
  name: 'USD Coin',
  addresses: { base: '0x...', arbitrum: '0x...', polygon: '0x...' },
  decimals: { default: 6 },
  flags: { swappable: true, collateral: true, borrowable: true, stakable: true }
}
```

Modules get the tokens they need via **flags**:
- `swappable: true` → Swap tokens
- `collateral: true` → Borrow collateral tokens
- `borrowable: true` → Borrowable tokens
- `stakable: true` → Staking tokens

This eliminates duplication — token data is described **once** and used everywhere.

---

## 18 Languages

The app is localized in 18 languages:

EN, RU, ES, FR, HI, ID, JA, KO, MS, PT, TH, TL, TR, UR, VI, ZH, AR, BN
