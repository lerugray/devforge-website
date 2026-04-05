# Website Update Brief — v0.2.8

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.7 -> v0.2.8

The "What's Live" header updated to v0.2.8. This is a reliability patch fixing a Gemini CLI spawn failure reported by the external tester (night__day).

## What Changed

**Gemini "Cannot find module" on send:**
v0.2.7 assumed the Gemini CLI script lived at a path constructed from `npm root -g`. On machines with different Node version managers (nvm, volta, fnm) or non-standard npm layouts, the constructed path was wrong and Node threw a MODULE_NOT_FOUND error on every send.

Fixed by finding the real path instead of guessing. At startup, Devforge runs `where gemini` to find the actual CLI wrapper on PATH, reads it, and extracts the real script location. This is the same path the operating system uses — it works regardless of how Node or Gemini was installed.

**Wrapper .js files replace inline one-liners:**
The Gemini and Codex spawn logic was previously crammed into `node -e "..."` one-liner strings that were hard to debug when they broke. Now written as proper .js wrapper files. Same behavior, but readable and testable.

**Test suite expanded:**
92 automated checks -> 133. New tests cover the CLI wrapper generation, path resolution, and the full new-user send flow.

## What to Update on the Site

One line added under the provider reliability section:

- Reliable CLI path resolution across all Node.js setups (nvm, volta, standard npm)

## Why This Matters

This is the 7th patch driven by external tester feedback. The tester uses Gemini CLI as their provider and hits every edge case in the spawn path. This fix addresses the root cause: instead of constructing a path and hoping it's right, we now find the path the OS already knows about. This should be the last spawn-related issue for Gemini users regardless of their Node.js setup.

## Source

Changes already made to ROADMAP_PUBLIC.md — sync to site.
