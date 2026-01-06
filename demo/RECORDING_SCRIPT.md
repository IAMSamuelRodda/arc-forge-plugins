# Arc Forge Plugins Installation Demo - Claude Code Interface

## Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal

---

## Demo Script (Step by Step)

### Scene 1: Show Clean State (5 sec)

```bash
claude mcp list
```

> Shows no vikunja server installed

---

### Scene 2: Start Claude Code (5 sec)

```bash
claude
```

---

### Scene 3: Add the Marketplace (10 sec)

```
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins
```

> Registers the Arc Forge plugin catalog

---

### Scene 4: Browse Available Plugins (5 sec)

```
/plugin
```

> Navigate to "Discover" tab to see available plugins

---

### Scene 5: Install Vikunja MCP (10 sec)

```
/plugin install vikunja-mcp@arc-forge-plugins
```

> Claude will clone and set up the plugin via HTTPS

---

### Scene 6: Provide Credentials (when prompted)

Edit `config.json` with these demo credentials:

```json
{
  "vikunja_url": "https://try.vikunja.arcforge.au",
  "vikunja_token": "tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
}
```

Then re-run install when Claude prompts.

---

### Scene 7: Verify Installation (5 sec)

```
/plugin
```

> Navigate to "Installed" tab to confirm vikunja-mcp is active

---

### Scene 8: Test the Plugin (10 sec)

```
List my Vikunja projects
```

> Shows actual projects from the demo Vikunja instance

---

## Recording Checklist

- [ ] Terminal font large enough to read
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Timing Target

~60-90 seconds total

## Commands Summary

```bash
# Add marketplace
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins

# List marketplaces
/plugin marketplace list

# Refresh marketplace (if needed)
/plugin marketplace update arc-forge-plugins

# Install a plugin
/plugin install vikunja-mcp@arc-forge-plugins

# Interactive plugin manager
/plugin
```

## Troubleshooting

If you get SSH permission errors, the marketplace may be cached. Run:
```
/plugin marketplace update arc-forge-plugins
```

Or remove and re-add:
```
/plugin marketplace remove arc-forge-plugins
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins
```
