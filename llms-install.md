# Installing Scamchecker.nl in Cline

This is a hosted remote MCP server. There is nothing to clone, build or install.

Add this entry to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "scamchecker": {
      "type": "streamableHttp",
      "url": "https://scamchecker.nl/mcp",
      "disabled": false
    }
  }
}
```

Authentication: No account needed for the hosted endpoint. For automations, request a free API key (`Authorization: Bearer sc_...`, 20 checks per 10 minutes and 100 per day per key) at https://scamchecker.nl/api/sleutel/.

No credentials are needed.

Check the connection by asking: "Is this SMS from PostNL real? "Your parcel is on hold, pay 1.99 EUR at postnl-pakket-hulp.com""
