# Claude Code – Axon Ads API Integration

This project configures Claude Code to use the [Axon Ads API](https://ads.axon.ai) as an MCP (Model Context Protocol) server, giving Claude direct access to Axon Ads tools for campaign management, reporting, and optimization.

## MCP Server

The Axon Ads MCP server is registered in `.claude/settings.json`:

```json
{
  "mcpServers": {
    "axon-ads": {
      "type": "sse",
      "url": "https://ads.axon.ai/api/mcp"
    }
  }
}
```

Claude Code connects to this server automatically when you start a session in this project directory.

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
