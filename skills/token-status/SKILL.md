---
name: token-status
description: Show Codex token usage, live rate limits, and /status-style session information from the command line.
---

# Token Status

Use this skill when the user asks for Codex token usage, live CLI usage display,
rate-limit status, or `/status`-style information.

Prefer the bundled script from this plugin:

```bash
node ../../scripts/codex-token-status
node ../../scripts/codex-token-status statusline
node ../../scripts/codex-token-status watch -i 10
node ../../scripts/codex-token-status json
```

If the command is installed or symlinked into `PATH`, these aliases are also
available:

```bash
codex-token-status
codex-token-status statusline
codex-token-status watch -i 10
codex-token-status json
```

The command reads:

- live rate limits from `codex app-server` with `account/rateLimits/read`
- latest session metadata from `~/.codex/state_5.sqlite`
- token usage from the latest `token_count` event in `~/.codex/sessions/**/*.jsonl`

If live rate limits are unavailable, it falls back to cached session data and
prints a warning.
