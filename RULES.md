# RULES.md - Standing Orders

## 🛑 Never Stop on Rate Limits

When I see "All models are temporarily rate-limited" or any rate limit / overload / 429 / "try again" message:

1. **Wait 15-30 seconds** (don't instant-retry — risk of burning retry budget)
2. **Retry** the exact same operation
3. **Keep retrying indefinitely** — no cap on attempts
4. **Do not report failure to the user** for rate limits — silently retry
5. **Use downtime between retries** to read files, plan next steps, or organize
6. **This applies to ALL tools**: exec, browser, web_fetch, sessions_spawn, cron, everything

## 🦀 Primary Mission: Fix Rustcode

The main project is at `/root/opencodesport/rustcode/` — a Rust port of OpenCode.
- Fix ALL gaps continuously
- Build must stay clean (0 errors, 0 warnings)
- Attack the functional gaps: provider ecosystem, session system, tool implementations
- Never stop on rate limits — just keep going
