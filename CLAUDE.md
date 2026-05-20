# Claude Code – Axon Ads API Integration

This project configures Claude Code to use the [Axon Ads API](https://ads.axon.ai) as an MCP (Model Context Protocol) server, giving Claude direct access to Axon Ads tools for campaign management, reporting, and optimization.

## MCP Server

The Axon Ads MCP server is registered in `.claude/settings.json` for project-level access:

```json
{
  "mcpServers": {
    "ads-manager-reports": {
      "type": "http",
      "url": "https://ads.axon.ai/api/mcp"
    }
  }
}
```

To register it at the user level instead (available across all your projects), run:

```bash
claude mcp add --transport http "ads-manager-reports" "https://ads.axon.ai/api/mcp" --scope user
```

## Authentication

The Axon Ads API requires authentication. Set your API key as an environment variable before starting Claude Code:

```bash
export AXON_ADS_API_KEY="your-api-key-here"
```

Or add it to your shell profile for persistence.

## Usage

Once configured, Claude can use Axon Ads tools directly in conversation. Example prompts:

- "Show me campaign performance for the last 7 days"
- "Create a new campaign targeting iOS users in the US"
- "Adjust the bid for campaign ID 12345 to $2.50"
- "Generate a report of top-performing creatives this month"

## Setup

1. Clone this repository
2. `cd claude-code-applovin`
3. Set your `AXON_ADS_API_KEY` environment variable
4. Run `claude` — the MCP server will be available automatically
