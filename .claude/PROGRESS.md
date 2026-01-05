# Arc Forge Plugins - Progress

## Current Status: Demo Recording Phase

### Completed
- [x] Created marketplace structure (`.claude-plugin/marketplace.json`)
- [x] Published to GitHub (IAMSamuelRodda/arc-forge-plugins)
- [x] Security audit on all 5 plugin repos (secrets in git history)
- [x] Cleaned vikunja-mcp history (leaked token removed, token rotated)
- [x] Standardized all repos with install.sh + config.json.example
- [x] Simplified READMEs (removed OpenBao complexity)
- [x] Made all 4 private repos public:
  - vikunja-mcp
  - todoist-mcp
  - cloudflare-mcp
  - youtube-transcript-mcp
- [x] Gitignore cleanup (removed tracked __pycache__, openbao_secrets.py)
- [x] Created `publishing-repos` skill from lessons learned
- [x] Added to portfolio (master_samuel.yaml)

### In Progress
- [ ] Record installation demo video
  - Tool: OBS Studio (configured for MP4 output)
  - Script: Clone marketplace → install vikunja-mcp → verify
  - Target: Clean machine demonstration

### Pending
- [ ] Upload demo video to repo or YouTube
- [ ] Update README with demo video embed
- [ ] Test installation on additional clean machines
- [ ] Consider adding more plugins to marketplace

## Plugin Repos (All Public)

| Plugin | Status | GitHub |
|--------|--------|--------|
| mcp-proxy | Public (flagship) | IAMSamuelRodda/mcp-proxy |
| vikunja-mcp | Public | IAMSamuelRodda/vikunja-mcp |
| todoist-mcp | Public | IAMSamuelRodda/todoist-mcp |
| cloudflare-mcp | Public | IAMSamuelRodda/cloudflare-mcp |
| youtube-transcript-mcp | Public | IAMSamuelRodda/youtube-transcript-mcp |

## Demo Recording Notes

### OBS Setup
- Output: MP4
- Source: Window Capture (terminal)
- Save to: ~/Videos/

### Demo Script
```bash
clear
claude mcp list
git clone https://github.com/IAMSamuelRodda/arc-forge-plugins.git
cd arc-forge-plugins
cat .claude-plugin/marketplace.json | jq '.plugins[].name'
git clone https://github.com/IAMSamuelRodda/vikunja-mcp.git
cd vikunja-mcp
./install.sh
nano config.json  # add credentials
./install.sh
claude mcp list
```

### Pre-Recording Checklist
- [ ] Increase terminal font (Ctrl++ x3)
- [ ] Clear terminal
- [ ] Have Vikunja credentials ready
- [ ] Close unnecessary windows
