# Website Update Brief — v0.2.3 + Roadmap

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.2 → v0.2.3

The "What's Live" section header changed from v0.2.2 to v0.2.3. This is a bugfix release focused on Aider provider reliability and diagnostic improvements. No new user-facing features — just making existing features work better for real users.

Key fixes for the site's feature claims:
- Multi-provider support line changed from "long prompt handling" to "reliable prompt delivery" (more accurate)
- Aider users can now actually send prompts without hanging (was broken for all Aider users on Windows)
- GDD detection is more robust with diagnostic logging

## New v0.3 Roadmap Item: Stack-Aware Test Automation

Added to ROADMAP_PUBLIC.md under v0.3. This is a TEST mode upgrade:

- Devforge generates test suites using the right framework for your stack (cargo test for Rust, pytest for Python, GUT for Godot, Playwright for web games, etc.)
- One-button test runner with results in the activity feed
- Failed tests auto-route to Debug mode with context
- Config validation for non-executable stacks (Ikemen GO character files, mod structures, ROM headers)
- Covers all 20 platforms

## How to Present

- **Headline angle:** "Automated testing that knows your game engine" — this is a differentiator. No other game dev tool picks the test framework for you based on your stack.
- The test automation story pairs well with the existing autonomous tabs pitch: "Let Claude write code in one tab, run tests in another."
- Config validation for Ikemen GO and modding is a niche but compelling detail for those communities.
- Don't oversell the visual/gameplay testing (computer use) — that's deferred to v0.4+ and not in the public roadmap yet.

## Source

Changes already made to ROADMAP_PUBLIC.md — sync to site.
