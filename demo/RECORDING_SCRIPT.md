# Arc Forge Plugins Installation Demo - Claude Code Interface

## Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal
4. **Have credentials ready** - Vikunja URL + API token in clipboard/notepad

---

## Demo Script (Step by Step)

### Scene 1: Show Clean State (5 sec)

```bash
claude mcp list
```

> Shows no vikunja server installed

---

### Scene 2: Clone Marketplace (10 sec)

```bash
git clone https://github.com/IAMSamuelRodda/arc-forge-plugins.git
cd arc-forge-plugins
```

---

### Scene 3: Browse Available Plugins (5 sec)

```bash
cat .claude-plugin/marketplace.json | jq '.plugins[] | {name, description}'
```

---

### Scene 4: Start Claude Code (5 sec)

```bash
claude
```

---

### Scene 5: Ask Claude to Install (type this in Claude Code)

```
Install the vikunja-mcp plugin from this marketplace
```

> Claude will read the marketplace.json, clone vikunja-mcp, and run install.sh

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

### Scene 7: Verify Installation

```
Show my registered MCP servers
```

> Or exit and run: `claude mcp list`

---

### Scene 8: Test the Plugin

```
List my Vikunja projects
```

> Shows actual projects from your Vikunja instance

---

## Recording Checklist

- [ ] Terminal font large enough to read
- [ ] Vikunja credentials ready (URL + token)
- [ ] Demo Vikunja instance has sample projects
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Timing Target

~60-90 seconds total
