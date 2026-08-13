# EVM Chains

> EVM-compatible blockchains — one `0x` address format.

---

## What Is EVM?

**EVM (Ethereum Virtual Machine)** is the standard that powers Ethereum and dozens of other blockchains. All EVM networks use the same address format (`0x...`), one token standard (ERC-20), and compatible smart contracts.

On **most** of these networks your **Smart Account address is the same**. Avalanche and Taiko currently use a classic EOA (no Smart Account / sponsored TX).

Non-EVM networks: [Solana](solana.md), [Tron](tron.md), [Bitcoin](bitcoin.md), [Dash](dash.md).

---

## All EVM Networks

### Base
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 8453 |
| **Type** | L2 (Optimism Stack) |
| **Gas** | ~$0.01 |
| **Explorer** | [basescan.org](https://basescan.org) |
| **Sponsored TX** | ✅ |

Fast and cheap L2 by Coinbase. One of the most popular for DeFi and everyday operations.

### Ethereum
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 1 |
| **Type** | L1 (mainnet) |
| **Gas** | $1–10+ |
| **Explorer** | [etherscan.io](https://etherscan.io) |
| **Sponsored TX** | ✅ |

The original blockchain. Most secure and decentralized. Sponsored TX are available when your daily quota allows — Ethereum gas is expensive, so use L2s when you can.

### Arbitrum
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 42161 |
| **Type** | L2 (Rollup) |
| **Gas** | ~$0.02 |
| **Explorer** | [arbiscan.io](https://arbiscan.io) |
| **Sponsored TX** | ✅ |

L2 with optimistic rollups. Large DeFi ecosystem, low fees.

### Polygon
| | |
|---|---|
| **Native Token** | POL |
| **Chain ID** | 137 |
| **Type** | Sidechain / L2 |
| **Gas** | < $0.01 |
| **Explorer** | [polygonscan.com](https://polygonscan.com) |
| **Sponsored TX** | ✅ |

One of the cheapest EVM networks. Widely used for mass transactions and NFTs.

### Optimism
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 10 |
| **Type** | L2 (Optimism Stack) |
| **Gas** | ~$0.01 |
| **Explorer** | [optimistic.etherscan.io](https://optimistic.etherscan.io) |
| **Sponsored TX** | ✅ |

L2 with a mature ecosystem and retroactive public goods funding.

### BNB Chain
| | |
|---|---|
| **Native Token** | BNB |
| **Chain ID** | 56 |
| **Type** | L1 |
| **Gas** | ~$0.03 |
| **Explorer** | [bscscan.com](https://bscscan.com) |
| **Sponsored TX** | ✅ |

Binance's blockchain. Popular in Asia, many DeFi protocols. PancakeSwap is the primary DEX.

### World Chain
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 480 |
| **Type** | L2 (Optimism Stack) |
| **Gas** | ~$0.01 |
| **Explorer** | [worldscan.org](https://worldscan.org) |
| **Sponsored TX** | ✅ |

Network by Worldcoin/World ID. Focus on identity and proof-of-personhood.

### HyperEVM
| | |
|---|---|
| **Native Token** | HYPE |
| **Chain ID** | 999 |
| **Type** | L1 |
| **Gas** | ~$0.01 |
| **Explorer** | [hyperliquid.cloud.blockscout.com](https://hyperliquid.cloud.blockscout.com) |
| **Sponsored TX** | ✅ |

EVM network by Hyperliquid — used for perpetual trading and DeFi on the Hyperliquid platform.

### Plasma
| | |
|---|---|
| **Native Token** | XPL |
| **Chain ID** | 9745 |
| **Type** | L1 |
| **Gas** | ~$0.01 |
| **Explorer** | [plasmascan.to](https://plasmascan.to) |
| **Sponsored TX** | ✅ |

New EVM network focused on speed and scalability.

### Monad
| | |
|---|---|
| **Native Token** | MON |
| **Chain ID** | 143 |
| **Type** | L1 |
| **Gas** | ~$0.01 |
| **Explorer** | [monadvision.com](https://monadvision.com) |
| **Sponsored TX** | ✅ |

Next-gen high-performance EVM blockchain with parallel transaction execution.

### Avalanche C-Chain
| | |
|---|---|
| **Native Token** | AVAX |
| **Chain ID** | 43114 |
| **Type** | L1 |
| **Gas** | ~$0.02 |
| **Explorer** | [snowtrace.io](https://snowtrace.io) |
| **Sponsored TX** | ❌ |
| **Smart Account** | ❌ (EOA) |
| **Smart Pay** | ✅ |
| **Swap** | ✅ |

Avalanche C-Chain. Send, receive, and swap. No Smart Account — you pay native AVAX or use Smart Pay.

### ApeChain
| | |
|---|---|
| **Native Token** | APE |
| **Chain ID** | 33139 |
| **Type** | L3 / app-chain |
| **Gas** | ~$0.01 |
| **Explorer** | [apescan.io](https://apescan.io) |
| **Sponsored TX** | ✅ |
| **Swap** | same-chain only (isolated) |

### Taiko
| | |
|---|---|
| **Native Token** | ETH |
| **Chain ID** | 167000 |
| **Type** | L2 (based rollup) |
| **Gas** | ~$0.01 |
| **Explorer** | [taikoscan.io](https://taikoscan.io) |
| **Sponsored TX** | ❌ |
| **Smart Account** | ❌ (EOA) |
| **Swap** | ✅ |

---

## Comparison Table

| Network | Gas | Sponsored | SA | Speed |
|---------|:---:|:---------:|:--:|:-----:|
| Base | ~$0.01 | ✅ | ✅ | 2s |
| Ethereum | $1–10 | ✅ | ✅ | 15s |
| Arbitrum | ~$0.02 | ✅ | ✅ | 2s |
| Polygon | < $0.01 | ✅ | ✅ | 3s |
| Optimism | ~$0.01 | ✅ | ✅ | 2s |
| BNB Chain | ~$0.03 | ✅ | ✅ | 3s |
| World Chain | ~$0.01 | ✅ | ✅ | 2s |
| HyperEVM | ~$0.01 | ✅ | ✅ | 1s |
| Plasma | ~$0.01 | ✅ | ✅ | 2s |
| Monad | ~$0.01 | ✅ | ✅ | 1s |
| Avalanche | ~$0.02 | ❌ | ❌ | 2s |
| ApeChain | ~$0.01 | ✅ | ✅ | 2s |
| Taiko | ~$0.01 | ❌ | ❌ | 2s |
