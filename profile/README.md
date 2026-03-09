# Zero Network

**Permissionless stablecoin microtransaction network for users and AI agents.**

1 Z = $0.01 USD | 136-byte transactions | <500ms finality | $0.0001 flat fee

---

### Sites

| | |
|---|---|
| [zzero.net](https://zzero.net) | Main site |
| [docs.zzero.net](https://docs.zzero.net) | Documentation |
| [explorer.zzero.net](https://explorer.zzero.net) | Network explorer |
| [mcp.zzero.net](https://mcp.zzero.net) | MCP integration |
| [pay.zzero.net](https://pay.zzero.net) | Payment widget SDK |
| [app.zzero.net](https://app.zzero.net) | Bridge, wallet & faucet |
| [install.zzero.net](https://install.zzero.net) | Node installer |

### Core

| | |
|---|---|
| [zero-chain](https://github.com/Zzero-net/zero-chain) | Node implementation (Rust) — 7 crates, 202 tests |
| [zero-contracts](https://github.com/Zzero-net/zero-contracts) | Bridge contracts (Solidity/Foundry) — ZeroVault + ZeroTimelock, 98 tests |

### SDKs

```bash
pip install zero-network          # Python
npm install @zero-network/sdk     # JavaScript/TypeScript
```

```python
from zero_network import Wallet

w = Wallet.create()
w.send("recipient_pubkey", 5)     # 5 Z = $0.05
print(w.balance())
```

```javascript
import { Wallet } from '@zero-network/sdk';

const w = Wallet.create();
await w.send('recipient_pubkey', 5);  // 5 Z = $0.05
console.log(await w.balance());
```

### MCP Server

AI agents can connect to the Zero MCP server for instant access to documentation, integration guides, and utility tools.

```json
{
  "mcpServers": {
    "zero": {
      "command": "uvx",
      "args": ["--from", "zero-network-mcp", "zero-mcp"]
    }
  }
}
```

### Install a Validator

```bash
curl -sSf https://install.zzero.net/install.sh | sh
zero-node init --validator
zero-node run
```

### Network Fees

| Fee | Amount | USD |
|-----|--------|-----|
| Transfer | 0.01 Z | $0.0001 |
| Account creation | 5 Z (one-time) | $0.05 |
| Bridge out | 0.50 Z | $0.005 |
| Bridge in | Free | $0.00 |

Fee distribution: 70% validators, 15% bridge reserve, 15% protocol reserve.

### Key Facts

- **Stablecoin**: 1:1 USDC/USDT backed on Base + Arbitrum
- **Micro-optimized**: 136-byte transactions, 0.01 Z ($0.0001) flat fee, 25 Z ($0.25) max per tx
- **Agent-native**: x402 protocol support, MCP payment integration
- **No smart contracts**: Transfer-only by design — one operation: move Z from A to B
- **Block-lattice**: Each account has its own chain, parallel processing, no global ordering bottleneck
- **Bridge**: Trinity Validators (2-of-3 multisig), EIP-712 signatures, tiered circuit breaker (20%/50%)
- **Timelock admin**: 24h delay on all vault admin operations, 2-of-3 guardian threshold
