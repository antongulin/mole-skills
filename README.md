<div align="center">

# mole-skills

AI agent skills for [Mole](https://github.com/tw93/Mole) — macOS system maintenance CLI

[![skills.sh](https://skills.sh/b/antongulin/mole-skills)](https://skills.sh/antongulin/mole-skills)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

</div>

Skills package providing AI coding assistants with structured instructions for helping users manage macOS disk space, system health, and applications through the Mole CLI.

> **Author**: [Anton Gulin](https://github.com/antongulin)

## Skills

### [mole-analyze](./skills/mole-analyze)

Explore macOS disk usage with an interactive TUI or JSON output. Covers overview mode, directory scanning, file navigation, large file detection, deleting files, JSON output, and custom path analysis.

```bash
mo analyze                          # Overview mode
mo analyze /path/to/dir             # Analyze a specific directory
mo analyze --json                   # JSON output
```

### [mole-clean](./skills/mole-clean)

Clean macOS disk space by removing caches, logs, temporary files, app data, browser data, system files, and project artifacts across 16 cleanup categories.

```bash
mo clean --dry-run                  # Preview what would be cleaned
mo clean                            # Run interactive cleanup
mo clean --whitelist                # Manage protected paths
```

### [mole-optimize](./skills/mole-optimize)

Optimize macOS system performance by refreshing caches, repairing configurations, and running maintenance tasks. Includes system health checks, diagnostics, database optimization, and service tuning.

```bash
mo optimize --dry-run               # Preview optimization actions
mo optimize                         # Run full optimization
```

### [mole-status](./skills/mole-status)

Monitor macOS system health with live metrics including RAM usage, disk usage, uptime, and overall system status in an interactive TUI dashboard.

```bash
mo status                           # Launch live system health dashboard
```

### [mole-uninstall](./skills/mole-uninstall)

Completely remove macOS applications including their support files, caches, and preferences. Supports Homebrew cask detection, batch removal, and Trash/permanent modes.

```bash
mo uninstall --list                 # List all uninstallable apps
mo uninstall AppName                # Uninstall by name
mo uninstall --dry-run AppName      # Preview before uninstalling
```

## Installation

### Using the Skills CLI (recommended)

**Project scope** (default) — installs locally in the current project:

```bash
npx skills add antongulin/mole-skills
```

**Global scope** (`-g`) — available across all projects:

```bash
npx skills add antongulin/mole-skills -g
```

The CLI automatically detects your installed coding agents. See [skills.sh](https://skills.sh) for more options.

### Manual

Clone and symlink the skills directory to your agent's skills path:

```bash
git clone https://github.com/antongulin/mole-skills.git
ln -s $(pwd)/mole-skills/skills/* <agent-skills-path>/
```

Replace `<agent-skills-path>` with your agent's skills directory. Most agents support the universal path `~/.agents/skills/`. Common agent-specific paths:

| Agent | Path |
|-------|------|
| Universal | `~/.agents/skills/` |
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` |
| GitHub Copilot | `~/.copilot/skills/` |
| OpenCode | `~/.config/opencode/skills/` |
| Antigravity | `~/.gemini/antigravity/skills/` |
| Cursor | `~/.cursor/skills/` |
| Cline | `~/.agents/skills/` |
| Gemini CLI | `~/.gemini/skills/` |

## Supported Agents

Skills are compatible with all agents that support the [skills.sh](https://skills.sh) specification:

| Agent | `--agent` | Project Path | Global Path |
|-------|-----------|-------------|-------------|
| AiderDesk | `aider-desk` | `.aider-desk/skills/` | `~/.aider-desk/skills/` |
| Amp, Kimi Code CLI, Replit, Universal | `amp`, `kimi-cli`, `replit`, `universal` | `.agents/skills/` | `~/.config/agents/skills/` |
| Antigravity | `antigravity` | `.agents/skills/` | `~/.gemini/antigravity/skills/` |
| Augment | `augment` | `.augment/skills/` | `~/.augment/skills/` |
| IBM Bob | `bob` | `.bob/skills/` | `~/.bob/skills/` |
| Claude Code | `claude-code` | `.claude/skills/` | `~/.claude/skills/` |
| OpenClaw | `openclaw` | `skills/` | `~/.openclaw/skills/` |
| Cline, Dexto, Warp | `cline`, `dexto`, `warp` | `.agents/skills/` | `~/.agents/skills/` |
| CodeBuddy | `codebuddy` | `.codebuddy/skills/` | `~/.codebuddy/skills/` |
| Codex | `codex` | `.agents/skills/` | `~/.codex/skills/` |
| Cursor | `cursor` | `.agents/skills/` | `~/.cursor/skills/` |
| Gemini CLI | `gemini-cli` | `.agents/skills/` | `~/.gemini/skills/` |
| GitHub Copilot | `github-copilot` | `.agents/skills/` | `~/.copilot/skills/` |
| Goose | `goose` | `.goose/skills/` | `~/.config/goose/skills/` |
| OpenCode | `opencode` | `.agents/skills/` | `~/.config/opencode/skills/` |
| OpenHands | `openhands` | `.openhands/skills/` | `~/.openhands/skills/` |
| Pi | `pi` | `.pi/skills/` | `~/.pi/agent/skills/` |
| Roo Code | `roo` | `.roo/skills/` | `~/.roo/skills/` |
| Windsurf | `windsurf` | `.windsurf/skills/` | `~/.codeium/windsurf/skills/` |
| Zencoder | `zencoder` | `.zencoder/skills/` | `~/.zencoder/skills/` |

See the [full list](https://github.com/vercel-labs/skills?tab=readme-ov-file#supported-agents) for all 50+ supported agents.

## Usage

These SKILL.md files are automatically loaded by AI coding assistants (OpenCode, Claude Code, Copilot CLI, etc.) when a user's request matches a skill's description. Each skill provides:

- **Command reference** — All flags, options, and environment variables
- **Workflow patterns** — Recommended usage patterns for common tasks
- **Safety guidance** — Important precautions and best practices
- **Exit codes** — Expected return values

> [!TIP]
> For a full list of Mole commands, run `mo --help` in your terminal.

## Compatibility

Skills are compatible with AI coding assistants that support the [skills.sh](https://www.skills.sh/docs) skill format, including OpenCode, Claude Code, Copilot CLI, Cursor, Codex, Cline, Gemini CLI, and 50+ others.

## Related

- [Mole](https://github.com/tw93/Mole) — The macOS CLI tool these skills support
- [opencode-skill-creator](https://github.com/antongulin/opencode-skill-creator) — Tool used to generate these skills
