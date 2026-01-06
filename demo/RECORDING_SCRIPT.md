# Arc Forge Plugins Installation Demo - Claude Code Interface

## Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal
4. **Ensure uv is installed**: `curl -LsSf https://astral.sh/uv/install.sh | sh`
5. **Set credentials** (for demo, export before starting):
   ```bash
   export VIKUNJA_URL="https://try.vikunja.arcforge.au"
   export VIKUNJA_TOKEN="tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
   ```
   > Or add directly to `~/.claude.json` after install - see README.md

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

### Scene 4: Install Vikunja MCP (15 sec)

```
/plugin install vikunja-mcp@arc-forge-plugins
```

> Installs plugin (uvx handles dependencies automatically)

---

### Scene 5: Restart Claude Code (10 sec)

```
/exit
```

Then restart:
```bash
claude
```

> MCP server activates on restart (uvx downloads & runs automatically)

---

### Scene 6: Test the Plugin (10 sec)

```
List my Vikunja projects
```

> Shows actual projects from the demo Vikunja instance

---

## Recording Checklist

- [ ] uv installed (`which uvx` should return path)
- [ ] Credentials set (export or ~/.claude.json)
- [ ] Terminal font large enough to read
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Demo Credentials

For the demo, set these before recording:
```bash
export VIKUNJA_URL="https://try.vikunja.arcforge.au"
export VIKUNJA_TOKEN="tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
```

## Timing Target

~60 seconds total

## How It Works (uvx Pattern)

The plugin uses the official Anthropic pattern:
- `uvx` automatically creates isolated environment
- Downloads package from git
- Installs dependencies
- Runs the server

**No manual venv, no pip install, no setup commands.**

## Commands Summary

```bash
# Add marketplace
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins

# Install plugin (uvx handles everything)
/plugin install vikunja-mcp@arc-forge-plugins

# Restart for MCP activation
/exit && claude
```

## Troubleshooting

**If uvx not found:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.bashrc  # or restart terminal
```

**If credentials not set:**
Add to `~/.claude.json` under the vikunja server's `env` section, or export before starting Claude Code.
