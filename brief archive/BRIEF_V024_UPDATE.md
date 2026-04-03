# Website Update Brief — v0.2.4

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.2.3 → v0.2.4

The "What's Live" header updated to v0.2.4. This is a reliability patch focused on Gemini CLI — a provider with a free tier (Google AI Studio API key, no credit card), which makes it the easiest on-ramp for new users who don't have Claude or OpenAI subscriptions.

## What Changed in the What's Live Section

Two lines updated under multi-provider support:

**Before:**
- Multi-provider support (Claude Code, Aider, Codex CLI, Gemini CLI) with reliable prompt delivery on Windows

**After:**
- Multi-provider support (Claude Code, Aider, Codex CLI, Gemini CLI) with reliable Windows delivery and real-time streaming output
- Gemini CLI runs with full activity feed, session resume, and auto-approval — same experience as Claude Code

## Why This Matters for the Site

Gemini CLI is the free entry point for Devforge. Users without a Claude subscription can use Google AI Studio's free tier to get the full Devforge experience. This is worth calling out on the site — it lowers the barrier to try the product.

The "same experience as Claude Code" line is accurate now: Gemini outputs stream-json (activity feed shows tool calls in real time), supports session resume, and auto-approves edits without interrupting the workflow.

## How to Present

- The free provider angle ("works with Gemini CLI's free tier") is a headline-worthy selling point on the landing page
- Don't go into technical details about the fix — just emphasize that Gemini now works reliably and provides the same real-time feedback as Claude Code
- Could be worth a callout box or feature highlight: "Free to start — use Google's Gemini CLI with a free AI Studio key"

## Source

Changes already made to ROADMAP_PUBLIC.md — sync to site.
