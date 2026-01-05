# Arc Forge Plugins

Claude Code plugin marketplace featuring production-grade MCP servers with context-optimized architectures.

## Featured: mcp-proxy

The flagship of this collection - an aggregating proxy that reduces context window usage by **95%** while maintaining full tool access.

**The Problem**: 10 MCP servers × 15 tools each = 150 tool definitions = ~15,000+ tokens consumed before any work begins.

**The Solution**: mcp-proxy exposes just 2 meta-tools (~800 tokens):
- `get_tools_in_category` - Navigate the tool hierarchy
- `execute_tool` - Run any tool by path

```
Before: 150 tools → 15,000 tokens
After:  2 tools  → 800 tokens (95% reduction)
```

## Available Plugins

| Plugin | Description | Tools |
|--------|-------------|-------|
| **mcp-proxy** | Context-optimized aggregating proxy | 2 meta-tools |
| **vikunja-mcp** | Self-hosted task management (GTD-ready) | 27 tools |
| **todoist-mcp** | Todoist with natural language dates | 12 tools |
| **youtube-transcript-mcp** | Transcript extraction (no API key) | 3 tools |
| **cloudflare-mcp** | DNS zone and record management | 5 tools |

## Installation

### Add Marketplace

```bash
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins
```

### Install Individual Plugins

```bash
# Install specific plugin
/plugin install mcp-proxy@arc-forge-plugins
/plugin install vikunja-mcp@arc-forge-plugins

# Or install all
/plugin install mcp-proxy vikunja-mcp todoist-mcp youtube-transcript-mcp cloudflare-mcp
```

## Demo: Aggregated Setup

For maximum context efficiency, use mcp-proxy to aggregate all servers:

1. Clone mcp-proxy and copy the demo config:
   ```bash
   git clone https://github.com/IAMSamuelRodda/mcp-proxy
   cp demo/mcp-proxy-config.json mcp-proxy/config/config.local.json
   ```

2. Configure environment files for each server (API keys, etc.)

3. Run bootstrap:
   ```bash
   cd mcp-proxy
   ./scripts/bootstrap.sh
   ```

4. Restart Claude Code - you now have all servers accessible through 2 meta-tools.

See [`demo/mcp-proxy-config.json`](demo/mcp-proxy-config.json) for a working configuration.

## Architecture Highlights

### Token Optimization

All servers in this collection follow context-efficient patterns:

- **Cursor-based pagination** - Large result sets paginated to prevent context overflow
- **Filtered responses** - Only relevant fields returned, not full API payloads
- **Lazy loading** - Tools discovered on-demand, not all at once

### Production-Ready

- Comprehensive error handling with actionable messages
- Environment-based configuration (no hardcoded secrets)
- Evaluation suites for each server

## Contributing

Found a bug or want to improve a server? Each plugin links to its source repository.

## License

MIT License - See individual repositories for details.

---

*Built by [Samuel Rodda](https://github.com/IAMSamuelRodda) - Engineering tools for the AI era*
