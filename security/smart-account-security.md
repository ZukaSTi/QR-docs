# Smart Account Security

> Audited contracts, open standards, transparent architecture.

---

## Contract Audits

QR Wallet uses **Alchemy LightAccount** — a wallet smart contract that has undergone multiple audits:

- Open source
- Deployed on all supported EVM networks
- Used by thousands of applications

> We do **not** use custom smart contracts for the wallet. LightAccount is a proven and audited solution from Alchemy.

---

## ERC-4337 Standard

Smart Account operates on the **open ERC-4337 standard**, which:

- Is accepted by the Ethereum community
- Is implemented by multiple independent teams
- Does not depend on any specific provider

Key contracts of the standard:

| Contract | Role |
|----------|------|
| **EntryPoint** | Router — accepts and executes UserOperations |
| **LightAccount** | Wallet — holds funds and executes calls |
| **Paymaster** | Sponsor — pays gas on behalf of the user |

All contracts are **public and verified** on blockchain explorers.

---

## Ownership Model

```
┌─────────────────┐
│  Your EOA key    │ ← Sole owner
│  (Secure Storage)│
└────────┬────────┘
         │ signs
┌────────▼────────┐
│  Smart Account   │ ← Verifies EOA signature
│  (on-chain)      │    before executing any action
└─────────────────┘
```

- **Only your EOA** can sign Smart Account transactions
- Smart Account verifies the signature at the smart contract level
- Without a valid signature — the transaction is rejected by the blockchain

---

## Attack Protection

| Threat | Protection |
|--------|-----------|
| Device theft | Biometrics + Secure Storage |
| Fake transaction | Signature verified on-chain |
| Server compromise | Keys only on device |
| Malicious DApp | Explicit confirmation for every TX |
| Replay attack | Nonce and chainId in UserOperation |

---

## What We Do NOT Store

- ❌ User private keys
- ❌ Mnemonic phrases
- ❌ Biometric data
- ❌ Passwords

We only store **public** information: wallet addresses, transaction history, profile settings.

---

## Transparency

- ERC-4337 standard is open and documented
- LightAccount contracts are open source
- EntryPoint is verified on Etherscan
- Anyone can inspect the contract code on block explorers
