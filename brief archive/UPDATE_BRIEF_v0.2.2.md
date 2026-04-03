# Website Update Brief — v0.2.2

## What Changed

### v0.2.2 is a patch release (bug fixes + stability)
This is a targeted fix release based on continued tester feedback. No new features — all fixes improve reliability for existing users, especially those using non-Claude providers on Windows.

### Fixes
- **GDD file detection** now works regardless of filename capitalization. Users who name their file `gdd.md` instead of `GDD.md` no longer get "not found." Devforge searches the directory for a case-insensitive match.
- **Gemini and Codex CLI** no longer crash with "command line too long" on Windows. Long prompts are written to a temp file instead of passed as command-line arguments.
- **Failed prompts are easier to recover.** If a send fails, the terminal now tells you to press Alt+Up to get your prompt back.
- **Textarea resize grip** no longer shows a non-functional browser resize handle.

### Under the hood
- First automated test suite: 11 Rust unit tests (security allowlist, timeout capping) and 70-point JS smoke test covering HTML structure, all 16 modes, 4 providers, security patterns, and accessibility.
- `.claude/rules/` directory with project map, architecture decisions, and model routing guide — improves AI session efficiency for development.

## Files Updated
- `ROADMAP_PUBLIC.md` — version bumped to v0.2.2, added multi-provider and test suite lines

## What the Website Needs
1. Bump the version number from v0.2.1 to v0.2.2 wherever it appears
2. No new feature sections needed — this is a stability patch
3. If there's a "reliability" or "stability" angle on the site, this release strengthens it: automated tests, better error messages, multi-provider robustness
4. The multi-provider angle (Claude, Aider, Codex, Gemini all working on Windows) is worth keeping visible — it's a differentiator

## Correct URLs
- Website: www.usedevforge.com
- itch.io: (existing listing)
- GitHub: github.com/lerugray/devforge
