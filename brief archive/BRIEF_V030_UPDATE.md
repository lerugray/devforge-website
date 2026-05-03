# Website Update Brief — v0.3.0

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.9 -> v0.3.0

This is a major feature release, not a patch. The "What's Live" header should update to v0.3.0. This is the first non-bugfix release since v0.2 and represents the completion of the v0.3 roadmap milestone.

## What Changed

### Provider Hardening (the tester's bugs are fixed)

The v0.2.2 through v0.2.9 patches were all attempts to fix Gemini CLI spawning on Windows. v0.3.0 addresses the remaining issues and adds structural protections:

- **Gemini `-p` argument fix:** The shell fallback passed an empty string that Windows cmd.exe silently ate, causing every Gemini send to fail with "Not enough arguments following: p." Fixed with a shell-safe placeholder.
- **Native installer support:** Provider CLIs installed as native `.exe` binaries (not npm `.cmd` wrappers) are now detected and spawned correctly. This covers Gemini and Codex users who installed via native installers rather than npm.
- **Gemini session resume:** The `--resume` flag was only passed on one of two code paths. Since Windows always uses the other path, session continuity was silently broken. Fixed.
- **243 automated tests** (was 139). Includes 66 new reliability tests specifically designed to catch every category of bug from the v0.2.x patches: empty args, inconsistent code paths, missing flags, unhandled events.

### Provider UX (new users can actually get started)

- **Auto-detect all providers at startup.** The provider settings modal now shows green/red status dots showing which CLIs are installed. Missing providers show a NOT INSTALLED badge with install instructions. Gemini shows a FREE badge.
- **PROVIDERS help tab.** New tab in the ? HELP modal with step-by-step setup for all 4 providers: install commands, authentication, costs, model recommendations, and troubleshooting.
- **Connection test on switch.** Switching providers shows a toast confirming the CLI works or warning if it's missing, with terminal install instructions.
- **Alternative suggestion.** If the active provider isn't installed, the terminal names a provider that IS installed.

### Auto-Model Routing (new feature)

- Devforge can now auto-select the best Claude model per prompt based on mode and task complexity.
- Forge, Debug, and Security mode prompts route to Opus. Short simple tasks route to Haiku (saves subscription time). Everything else routes to Sonnet.
- Toggleable in provider settings. Off by default. Claude only.
- The model picker shows a SUGGESTED badge next to the recommended model for the current mode.

## What to Update on the Site

### Hero/feature section
Add a new feature bullet or card:
- **Smart model routing** — auto-picks Opus, Sonnet, or Haiku based on your mode and task complexity. Saves subscription time on simple tasks, uses full power for architecture and debugging.

### Provider section
Update to emphasize the improved multi-provider experience:
- 4 providers supported: Claude Code ($20-100/mo), Gemini CLI (free), Aider (bring your own key), Codex CLI (OpenAI credits)
- Auto-detection shows which CLIs are installed at a glance
- In-app setup guide with install commands, auth steps, and troubleshooting

### Reliability section
- 243 automated tests covering provider spawning, argument safety, dual-path consistency, and security encoding
- 9 patches driven by external tester feedback (v0.2.2 through v0.3.0)

### Version number
- Update any version references from v0.2.x to v0.3.0

## Why This Matters

v0.2.2 through v0.2.9 were reactive patches fixing one tester's Gemini issues. v0.3.0 is proactive — it fixes the remaining bugs, adds structural tests to prevent regressions, and makes the multi-provider experience actually usable for someone who isn't using Claude Code. The PROVIDERS help tab and auto-detection mean a new user with only Gemini installed can get started without reading external docs.

The auto-model routing is the first v0.3 roadmap feature (Advanced Model Selection). Cross-provider routing (Claude for code, Gemini for research) is deferred to v0.4.0 as an opt-in feature.

## Source

Changes pushed to main. ROADMAP_PUBLIC.md may need updating to reflect v0.3.0 completion and v0.4.0 plans.
