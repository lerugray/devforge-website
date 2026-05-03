# Website Update Brief — v0.2.6

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.5 -> v0.2.6

The "What's Live" header updated to v0.2.6. This is a polish patch fixing three issues reported by the external tester (night__day).

## What Changed

**Bug #1 — Activity feed not clearing on project switch:**
Switching between projects left the previous project's activity entries (tool calls, file edits, thinking blocks) visible in the feed. Now clears automatically when you switch projects.

**Bug #2 — CLEAR button in activity feed broken:**
The CLEAR button in the activity panel header did nothing when clicked. Root cause: an internal array reference was broken by how the data was being reset. Fixed so the button works reliably.

**Bug #3 — Node.js deprecation warning showing in terminal:**
A red warning about "DEP0190 DeprecationWarning" appeared in the terminal on every prompt send, looking like an error. This is harmless CLI noise from Node.js internals. Now suppressed from display.

## What to Update on the Site

One line updated under activity feed:

**Before:**
- Activity feed showing what Claude is doing in real time

**After:**
- Activity feed showing what Claude is doing in real time (clears properly between projects, CLEAR button works)

One line added:
- Clean terminal output: Node.js deprecation warnings and other CLI noise suppressed

## Why This Matters

All three bugs affect the basic "does this feel broken?" first impression. A red warning on every send, stale data from another project, and a button that does nothing all erode trust. These are the kind of fixes that make the difference between "this tool is rough" and "this tool works."

## Source

Changes already made to ROADMAP_PUBLIC.md — sync to site.
