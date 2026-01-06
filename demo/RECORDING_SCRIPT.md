# Arc Forge Plugins Installation Demo

## Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal
4. **Ensure uv is installed**: `curl -LsSf https://astral.sh/uv/install.sh | sh`

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

### Scene 5: Add Credentials (15 sec)

```
/exit
```

Open `~/.claude.json` and add credentials to the vikunja server:

```json
{
  "mcpServers": {
    "vikunja": {
      "env": {
        "VIKUNJA_URL": "https://try.vikunja.arcforge.au",
        "VIKUNJA_TOKEN": "tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206"
      }
    }
  }
}
```

---

### Scene 6: Restart & Test (10 sec)

```bash
claude
```

Then test:
```
List my Vikunja projects
```

> Shows actual projects from the demo Vikunja instance

---

## Recording Checklist

- [ ] uv installed (`which uvx` should return path)
- [ ] Terminal font large enough to read
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Demo Credentials

```
VIKUNJA_URL: https://try.vikunja.arcforge.au
VIKUNJA_TOKEN: tk_581fe5bcf3ac77e96bfed84e0b2791adff50c206
```

## Timing Target

~60 seconds total

## Troubleshooting

**If uvx not found:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.bashrc  # or restart terminal
```

**If plugin not working:**
Check `~/.claude.json` has credentials in the vikunja server's `env` section.
