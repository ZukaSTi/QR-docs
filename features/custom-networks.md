# Custom Networks

> Add any EVM network — and its tokens — yourself.

---

## Custom EVM Networks

[QR] wallet includes a curated list of networks. If you need another EVM chain (a new L2, an app-chain, a private consortium chain), you can **add it by RPC**.

1. Open network settings → **Add network**
2. Enter **RPC URL**, **chain ID**, **name**, and **native token** symbol/decimals
3. The app checks that the RPC responds and that the chain ID matches
4. The network appears in your wallet: balances, receive, and send (as supported)

Custom networks use your **EOA** on that chain. They do not use sponsored Smart Account transactions.

---

## Custom Tokens

On any EVM network (built-in or custom):

1. Tap **Add token**
2. Paste the token **contract address**
3. The app reads name, symbol, and decimals
4. The token appears in your list

Same-symbol tokens on different networks (for example USDT on Ethereum and USDT on your custom chain) are grouped in one row with per-network balances.

---

## Safety

- Only add RPCs and contracts you trust
- A wrong chain ID or a malicious RPC can show fake balances — double-check explorers
- Custom tokens are **not** automatically available in Swap until they exist on a supported aggregator

---

## FAQ

**Can I add Solana / Bitcoin / Tron this way?**

No. Custom networks are **EVM-only**.

**Will custom networks sync to a new phone?**

They are stored on the device. After you restore the wallet from seed, add the network and tokens again (or wait if cloud restore of the list is offered in your build).
