# Codex Pulse

Codex plugin and terminal command for usage, live rate limits, and
`/status`-style session information. It works as a bundled Codex plugin skill
and as an optional shell command when linked into `PATH`.

## Commands

```bash
node scripts/codex-pulse
node scripts/codex-pulse status
node scripts/codex-pulse statusline
node scripts/codex-pulse watch -i 10
node scripts/codex-pulse json
```

If the command is installed or symlinked into `PATH`, these aliases are also
available:

```bash
codex-pulse
codex-pulse status
codex-pulse statusline
codex-pulse watch -i 10
codex-pulse json
```

## Data Sources

- `codex app-server` JSON-RPC method `account/rateLimits/read`
- `~/.codex/state_5.sqlite` latest thread metadata
- latest `token_count` event under `~/.codex/sessions/**/*.jsonl`

The command falls back to cached session data if live rate-limit reads fail.

## Local Install

```bash
ln -sf "$PWD/scripts/codex-pulse" ~/.local/bin/codex-pulse
```
