# Arc Forge Plugins

Claude Code plugin marketplace for Arc Forge MCP servers.

## Purpose

- Showcase for portfolio: demonstrates MCP server engineering expertise
- Functional marketplace: others can install plugins via Claude Code CLI

## Structure

```
arc-forge-plugins/
├── .claude-plugin/
│   └── marketplace.json    # Plugin catalog (distributed strategy)
├── demo/
│   └── mcp-proxy-config.json   # Sample aggregated setup
└── README.md               # Installation + showcase
```

## Key Points

- **Distributed marketplace**: Points to GitHub repos, doesn't bundle code
- **mcp-proxy is flagship**: 95% context reduction demo
- **Cherry-picked servers**: vikunja, todoist, youtube-transcript, cloudflare

## Maintenance

When adding new plugins:
1. Ensure the MCP server repo is public on GitHub
2. Add entry to `.claude-plugin/marketplace.json`
3. Update README.md plugin table
4. Optionally add to demo config if relevant

## Version Sync

Keep marketplace versions aligned with source repo releases.
