# Token Status

Codex plugin and terminal command for token usage, live rate limits, and
`/status`-style session information. It works as a bundled Codex plugin skill
and as an optional shell command when linked into `PATH`.

## Commands

```bash
node scripts/codex-token-status
node scripts/codex-token-status status
node scripts/codex-token-status statusline
node scripts/codex-token-status watch -i 10
node scripts/codex-token-status json
```

If the command is installed or symlinked into `PATH`, these aliases are also
available:

```bash
codex-token-status
codex-token-status status
codex-token-status statusline
codex-token-status watch -i 10
codex-token-status json
```

## Data Sources

- `codex app-server` JSON-RPC method `account/rateLimits/read`
- `~/.codex/state_5.sqlite` latest thread metadata
- latest `token_count` event under `~/.codex/sessions/**/*.jsonl`

The command falls back to cached session data if live rate-limit reads fail.

## Local Install

```bash
ln -sf "$PWD/scripts/codex-token-status" ~/.local/bin/codex-token-status
```
