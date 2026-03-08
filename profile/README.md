# Zero Network

**Permissionless stablecoin microtransaction network for users and AI agents.**

1 Z = $0.01 USD | 100-byte transactions | <500ms finality | $0.0001 flat fee

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

### MCP Server

AI agents can connect to the Zero MCP server for instant access to documentation, integration guides, and utility tools.

```json
{
  "mcpServers": {
    "zero": {
      "command": "uvx",
      "args": ["--from", "zero-mcp", "zero-mcp"]
    }
  }
}
```

### Quick Start

```bash
pip install zero-sdk
```

```python
from zero_sdk import Wallet

wallet = Wallet.create()
wallet.send(to="zr_recipient", amount=5)  # 5 Z = $0.05
```

### Key Facts

- **Stablecoin**: 1:1 USDC/USDT backed, not volatile
- **Micro-optimized**: 100-byte transactions, 0.01 Z ($0.0001) flat fee
- **Agent-native**: x402 protocol support, MCP payment integration
- **No smart contracts**: Transfer-only by design
- **Block-lattice**: Each account has its own chain, parallel processing
