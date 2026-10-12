# Buildability™ MCP Server (`readypermit-mcp`)

> AI-powered property zoning, buildability, and ADU eligibility analysis for any U.S. address.

This MCP server connects AI assistants (Claude, ChatGPT, Cursor, VS Code, Windsurf) to [Buildability™](https://buildability.us) — instant property intelligence powered by 20+ government data sources.

## Pricing

Pay-as-you-go: **$5 per successful analysis** (prepaid credits).

Get an API key at https://buildability.us/api

The Buildability™ Score is still available at no cost on https://buildability.us

No open free tier on the MCP endpoint. A valid API key is required for production volume.

## Tools

| Tool | Description |
|------|-------------|
| `analyze_property` | Full zoning & buildability analysis for any U.S. address |
| `check_adu_eligibility` | ADU (accessory dwelling unit) eligibility check |
| `check_flood_risk` | FEMA flood zone & environmental risk assessment |
| `compare_parcels` | Side-by-side comparison of 2-5 properties |
| `what_can_i_build` | Answer "what can I build here?" for any property |

## Quick Setup

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "readypermit": {
      "command": "npx",
      "args": ["-y", "readypermit-mcp"],
      "env": {
        "READYPERMIT_API_KEY": "your-buildability-api-key",
        "MAPBOX_TOKEN": "your-mapbox-token"
      }
    }
  }
}
```

### Cursor

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "readypermit": {
      "command": "npx",
      "args": ["-y", "readypermit-mcp"],
      "env": {
        "READYPERMIT_API_KEY": "your-buildability-api-key",
        "MAPBOX_TOKEN": "your-mapbox-token"
      }
    }
  }
}
```

### ChatGPT Desktop

Settings > MCP Servers > Add Server > enter `npx -y readypermit-mcp`

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `READYPERMIT_API_KEY` | Required for production | API key for full analysis volume. Get one at https://buildability.us/api |
| `MAPBOX_TOKEN` | Recommended | Mapbox API token for geocoding |

## What It Does

When an AI assistant user asks about property zoning, ADUs, flood risk, or buildability, the MCP tools:

1. Geocode the address via Mapbox
2. Return a structured property preview with key data points
3. Generate a deep link to the full Buildability™ Report

## Example Prompts

- "Can I build an ADU at 742 Evergreen Terrace, Springfield, IL?"
- "What's the zoning for 123 Main St, Austin, TX?"
- "Is my property in a flood zone? 456 Oak Ave, Miami, FL"
- "Compare these 3 investment properties for buildability"
- "What can I build on my lot at 789 Pine St, Denver, CO?"

## About Buildability™

Buildability™ replaces $2,000-$4,500 in zoning consultant fees with an instant Buildability™ Report:

- Buildability™ Score (0-100, letter-graded)
- Zoning analysis (FAR, setbacks, height limits, permitted uses)
- ADU eligibility and permit pathway
- Environmental risk (FEMA, EPA, wildfire, seismic)
- Comparable sales and market position

Covers all 50 U.S. states, 3,100+ counties. Data from 20+ government sources.

Buildability™ is a product of ReadyPermit.AI, Inc.

## License

MIT

## Links

- [Buildability™](https://buildability.us)
- [Report an Issue](https://github.com/Galax-ai/readypermit-mcp/issues)
- Built by [Galax Studios](https://galaxstudios.com)
