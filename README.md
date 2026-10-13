<img src="logo-400.png" alt="Scamchecker.nl logo" width="96" height="96">

# Scamchecker.nl MCP server

**Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium).**

Remote MCP server: `https://scamchecker.nl/mcp` (Streamable HTTP) · Website: [scamchecker.nl](https://scamchecker.nl/)

## What it does

Scamchecker.nl checks a message that looks off: a phishing email, a fake parcel SMS, a WhatsApp message from "your son" with a new number, or a link that imitates a bank. You paste the text or link, the server returns a verdict, the red flags it found, which brand is being impersonated and what to do next. It is built for messages aimed at people in the Netherlands and Belgium.

A result without red flags never means a message is safe. The server says so in every answer.

## Connect

- **Server URL:** `https://scamchecker.nl/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** No account needed for the hosted endpoint. For automations, request a free API key (`Authorization: Bearer sc_...`, 20 checks per 10 minutes and 100 per day per key) at https://scamchecker.nl/api/sleutel/.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http scamchecker https://scamchecker.nl/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "scamchecker": {
      "type": "http",
      "url": "https://scamchecker.nl/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `check_message` | Check text, a link or a screenshot description for scam signals; returns verdict, summary, signals, impersonated brand and advice. |

## Example prompts

- Is this SMS from PostNL real? "Your parcel is on hold, pay 1.99 EUR at postnl-pakket-hulp.com"
- My mother got a WhatsApp from an unknown number saying it is me with a new phone. Scam?
- Check this link before I click it: ing-veilig-check.nl

## Links

- Website: https://scamchecker.nl/
- Documentation: https://scamchecker.nl/hoe-het-werkt
- Privacy policy: https://scamchecker.nl/privacy/
- Terms: https://scamchecker.nl/voorwaarden/
- Free API key: https://scamchecker.nl/api/sleutel/
- n8n node: https://www.npmjs.com/package/n8n-nodes-scamchecker
- Support: mailto:contact@scamchecker.nl

## Keywords

scam checker, phishing detection, fraud check, fake SMS, smishing, WhatsApp scam, fake parcel message, bank phishing, link checker, Netherlands, Belgium.

Nederlands: nepbericht controleren, phishing herkennen, oplichting, nep sms, WhatsApp fraude, vriend-in-nood fraude, pakketje sms nep, phishing mail ING Rabobank, link controleren, is dit nep.

## More MCP servers by Samautomation

- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/smrht/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/smrht/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/smrht/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))
- [SamDesk Support](https://samdesk.nl/support/plugin/): Read your SamDesk support inbox, find customer agreements and draft replies. Read-only. ([listing](https://github.com/smrht/samdesk-support-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
