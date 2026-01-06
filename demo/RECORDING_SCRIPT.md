# Arc Forge Plugins Demo

## Demo Videos

| Video | Description |
|-------|-------------|
| `vikunja-mcp-demo.mp4` | MCP server in action: create task, add reminder via Claude |
| `marketplace-install-part1.mp4` | Plugin marketplace installation flow |

---

## Vikunja MCP Demo (vikunja-mcp-demo.mp4)

Shows the MCP server working end-to-end:

### Scene 1: Create Task in Vikunja (Browser)
- Open Vikunja web interface
- Create a new task

### Scene 2: Show Installed MCP Server (Claude Code)
- Show `claude mcp list` or MCP status
- Confirms vikunja-mcp is installed and connected

### Scene 3: Add Reminder via Claude
- Prompt Claude to add a reminder to the task
- Example: "Add a reminder to task #123 for tomorrow at 9am"

### Scene 4: Confirm Success in Vikunja (Browser)
- Return to Vikunja web interface
- Show the reminder was added to the task

---

## Installation Demo (marketplace-install-part1.mp4)

### Pre-Recording Setup

1. **Clean terminal** - `clear`
2. **Increase font** - `Ctrl++` (3-4x)
3. **OBS ready** - Window capture on terminal
4. **Ensure uv is installed**: `curl -LsSf https://astral.sh/uv/install.sh | sh`

### Scene 1: Show Clean State (5 sec)

```bash
claude mcp list
```

> Shows no vikunja server installed

### Scene 2: Start Claude Code (5 sec)

```bash
claude
```

### Scene 3: Add the Marketplace (10 sec)

```
/plugin marketplace add IAMSamuelRodda/arc-forge-plugins
```

> Registers the Arc Forge plugin catalog

### Scene 4: Install Vikunja MCP (15 sec)

```
/plugin install vikunja-mcp@arc-forge-plugins
```

> Installs plugin (uvx handles dependencies automatically)

### Scene 5: Configure Credentials (15 sec)

Run the setup script:

```bash
curl -sSL https://raw.githubusercontent.com/IAMSamuelRodda/vikunja-mcp/main/setup-credentials.sh | bash
```

Or manually create `~/.config/vikunja-mcp/config.json`:

```json
{
  "url": "https://your-vikunja-instance.com",
  "token": "your-api-token"
}
```

### Scene 6: Restart & Test (10 sec)

```bash
claude
```

Then test:
```
List my Vikunja projects
```

> Shows actual projects from the Vikunja instance

---

## Recording Checklist

- [ ] uv installed (`which uvx` should return path)
- [ ] Terminal font large enough to read
- [ ] OBS recording to MP4
- [ ] Clear terminal before starting

## Timing Target

~60 seconds per demo

## Troubleshooting

**If uvx not found:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.bashrc  # or restart terminal
```

**If plugin not working:**
Run `setup-credentials.sh` or check `~/.config/vikunja-mcp/config.json` exists.
