# Website Update Brief — v0.2.5

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.4 -> v0.2.5

The "What's Live" header updated to v0.2.5. This is a reliability patch that fixes the two most-reported bugs from early testers.

## What Changed

**Bug #1 — GDD files not detected (persistent since v0.2.1):**
Root cause found and fixed. Tauri's filesystem permissions were silently blocking access to user project folders. Every user who created a project pointing to a folder in Documents (or anywhere outside the app's own directory) hit this. GDD files, task files, session notes — all unreadable. Now works on any folder.

**Bug #2 — Gemini CLI hanging on send:**
Root cause found and fixed. The Gemini integration now streams output in real time instead of freezing. Users on Google's free Gemini tier get the same responsive experience as Claude Code users.

**Also fixed:** Version number now shows the full patch version so users can verify their build. Terminal auto-scrolls to latest output.

## What to Update on the Site

One line updated under multi-provider support:

**Before:**
- Multi-provider support (Claude Code, Aider, Codex CLI, Gemini CLI) with reliable Windows delivery and real-time streaming output

**After:**
- Multi-provider support (Claude Code, Aider, Codex CLI, Gemini CLI) with reliable file detection and real-time streaming on all providers

## Why This Matters

These were the two bugs that blocked the first external tester from using Devforge at all. The GDD fix in particular means project setup actually works now — the single most important first-run experience. Every prior patch (v0.2.1 through v0.2.4) was treating symptoms of the same underlying permission issue.

## Source

Changes already made to ROADMAP_PUBLIC.md — sync to site.
