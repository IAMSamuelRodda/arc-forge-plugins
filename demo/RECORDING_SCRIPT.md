# Arc Forge Plugins Installation Demo - Claude Code Interface

## Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal
4. **Set env vars first** (before recording):
   ```bash
   export VIKUNJA_URL="https://try.vikunja.arcforge.au"
   export VIKUNJA_TOKEN="tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
   ```

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

### Scene 4: Install Vikunja MCP (10 sec)

```
/plugin install vikunja-mcp@arc-forge-plugins
```

> Clones the plugin

---

### Scene 5: Run Setup Command (15 sec)

```
/vikunja-mcp:setup
```

> This creates the Python venv and installs dependencies

---

### Scene 6: Exit and Restart (10 sec)

```
/exit
```

Then restart:
```bash
claude
```

> MCP server activates on restart

---

### Scene 7: Test the Plugin (10 sec)

```
List my Vikunja projects
```

> Shows actual projects from the demo Vikunja instance

---

## Recording Checklist

- [ ] Environment variables set BEFORE starting Claude Code
- [ ] Terminal font large enough to read
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Environment Variables

Set these before recording:
```bash
export VIKUNJA_URL="https://try.vikunja.arcforge.au"
export VIKUNJA_TOKEN="tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
```

## Timing Target

~60-90 seconds total

## Commands Summary

```bash
# Add marketplace
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins

# Install plugin
/plugin install vikunja-mcp@arc-forge-plugins

# Run setup (creates venv, installs deps)
/vikunja-mcp:setup

# Restart Claude Code for MCP to activate
/exit
claude
```
