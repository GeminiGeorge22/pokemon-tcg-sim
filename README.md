# Pokémon TCG Sim

[![pokemon-tcg-sim MCP connector](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/pokemon-tcg-sim/badges/score.svg)](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/pokemon-tcg-sim)

Pokémon TCG Sim is a **Pokémon Trading Card Game simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Paste a 60-card list and ask: Is this legal in Standard? How often is this card in prizes? Goldfish this list.

Operated by **FMF Tools**.

- Live site: https://pokemon-tcg-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp
- Install page: https://pokemon-tcg-sim.fmf-x402.workers.dev/install
- Tools and prices: https://pokemon-tcg-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, deck check, and opening-hand odds are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "pokemon-tcg-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http pokemon-tcg-sim https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "pokemon-tcg-sim": {
      "url": "https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"pokemon-tcg-sim","type":"http","url":"https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: Pokémon TCG Sim. MCP server URL: `https://pokemon-tcg-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| ptcg_deck_check | free |
| ptcg_opening_hand_odds | free |
| ptcg_draw_odds | $0.001 |
| ptcg_prize_odds | $0.001 |
| ptcg_goldfish | $0.003 |

## Licence and fan notice

This repository is MIT licensed. Pokémon TCG Sim is an unofficial fan tool, not affiliated with or endorsed by Nintendo, Game Freak, or The Pokémon Company. Pokémon and card names are trademarks of their owners. Card data comes from TCGdex (MIT). Card data tools are free. Paid tools sell only our own computation and return no card data.

Contact: fmf-tools@agentmail.to
