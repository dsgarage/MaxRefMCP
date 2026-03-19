# MaxRefMCP

[日本語](README.md) | English

**Max/MSP & Max4Live Reference MCP Server**

An [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) server that lets you search and browse Max/MSP object references from any AI client.

> **Works with any MCP-compatible AI client.**
> Connect from Claude Code, Claude Desktop, or any client that supports the Streamable HTTP transport.

## Features

| Tool | Description |
|---|---|
| `maxref.search_object` | Search objects by name or keyword |
| `maxref.get_object` | Get detailed object reference |
| `maxref.compare_objects` | Compare 2-5 objects side by side |
| `maxref.explain_connection` | Explain connection between two objects |
| `maxref.rnbo_compatibility` | Check RNBO compatibility + suggest alternatives |
| `maxref.glossary` | Japanese-English Max/MSP glossary |
| `maxref.search_pattern` | Search design patterns by intent |
| `maxref.search_package` | Search external packages & libraries |
| `maxref.suggest_approach` | Suggest implementation approaches |
| `maxref.official_news` | Fetch latest news from Cycling '74 |
| `maxref.rnbo_news` | Fetch latest RNBO / Move Takeover info |
| `maxref.read_article` | Read official article details |
| `maxref.report_bug` | Report bugs via auto-created GitHub Issues |
| `maxref.request_feature` | Request features via auto-created GitHub Issues |
| `maxref.analytics` | Get API usage summary |

See [Wiki — Tool Reference](https://github.com/dsgarage/MaxRefMCP/wiki/Tools-en) for detailed parameter specs.

## Quick Start

### Claude Code (CLI)

```bash
claude mcp add --transport http --scope project max-ref "https://maxrefmcp-production.up.railway.app/mcp"
```

### Claude Desktop

Add to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "max-ref": {
      "type": "streamable-http",
      "url": "https://maxrefmcp-production.up.railway.app/mcp"
    }
  }
}
```

### Other MCP-Compatible Clients

Connect using the following:

| Item | Value |
|---|---|
| Endpoint URL | `https://maxrefmcp-production.up.railway.app/mcp` |
| Transport | Streamable HTTP |
| Authentication | Not required |

See [Wiki — Setup Guide](https://github.com/dsgarage/MaxRefMCP/wiki/Setup-en) for detailed instructions.

## Usage

Once connected, simply ask your AI about Max/MSP and the tools will be invoked automatically.

```
"What's the difference between cycle~ and phasor~?"
"I want to design an FM synthesis patch"
"Search for gen~ compatible objects"
"Is groove~ compatible with RNBO?"
```

See [Wiki — Usage & Examples](https://github.com/dsgarage/MaxRefMCP/wiki/Usage-en) for more.

## Documentation

| Page | Content |
|---|---|
| [Setup Guide](https://github.com/dsgarage/MaxRefMCP/wiki/Setup-en) | How to connect from various AI clients |
| [Tool Reference](https://github.com/dsgarage/MaxRefMCP/wiki/Tools-en) | All 15 tools with parameter specs |
| [Usage & Examples](https://github.com/dsgarage/MaxRefMCP/wiki/Usage-en) | Real-world usage and example queries |
| [FAQ](https://github.com/dsgarage/MaxRefMCP/wiki/FAQ-en) | Frequently asked questions |

## Feedback

- **Bug reports**: [Create an Issue](https://github.com/dsgarage/MaxRefMCP/issues/new?template=bug_report.md)
- **Feature requests**: [Create an Issue](https://github.com/dsgarage/MaxRefMCP/issues/new?template=feature_request.md)
- You can also report directly from within the MCP tools using `maxref.report_bug` / `maxref.request_feature`

## Release Notes

See [Releases](https://github.com/dsgarage/MaxRefMCP/releases).

## Related Projects

- **[MaxMCP](https://github.com/dsgarage/MaxMCP)** — MCP server for actual Max/MSP patch operations (create, connect, control)

Connect both MaxRefMCP (research & design) and MaxMCP (patch operations) for an end-to-end AI-assisted Max/MSP workflow.

## Author

**dsgarage** — [@dsgarage](https://x.com/dsgarage)

## License

MIT
