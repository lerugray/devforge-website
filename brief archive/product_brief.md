# DevForge — Product Brief

> Reference document for building the landing page. This is NOT deployed — it's context for the website builder.

---

## What DevForge Is

DevForge is a Windows desktop app (built with Tauri 2) that wraps Claude Code in a structured, game-design-specific UI. It's a command center for AI-assisted game development.

**It is NOT:**
- A game engine (it works *with* your engine — Godot, Unity, Phaser, PICO-8, etc.)
- An idea generator (it doesn't make creative decisions for you)
- A general-purpose AI wrapper (it's specifically built for game design workflows)

**It IS:**
- A context manager that keeps Claude oriented on your project across sessions
- A mode-based workflow tool that keeps Claude focused on one job at a time
- A git safety net that protects non-programmers from losing work
- A design-first tool for people who know what they want to build but need help implementing it

---

## The Core Problem It Solves

Game designers using Claude Code (or similar AI coding tools) hit the same walls:

1. **Context rot** — Claude forgets your project between sessions. You re-explain the same design decisions over and over
2. **No structure** — AI gives you code, but nobody manages the phases, tasks, or design consistency
3. **Git terror** — Non-programmers avoid version control, then lose work when Claude overwrites something
4. **Mode confusion** — Asking Claude to discuss a mechanic and implement it in the same conversation leads to unfocused, sloppy output

DevForge solves all four by making your Game Design Document (GDD) the source of truth, enforcing mode-based discipline, and wrapping git in one-click safety.

---

## Who It's For

- **Game designers with a vision** who need technical help implementing it
- **Solo devs** who've tried Claude Code and got tired of re-explaining their project
- **Board/wargame designers** going digital (DevForge has a full Analog Mode for tabletop)
- **Vibe coders** who want more control over their AI-assisted workflow

**Not for:** People who want AI to generate game ideas from scratch. DevForge assumes you already know what you're building.

---

## Price

**$20 one-time purchase.** No subscriptions. You own it.

(Claude Code subscription is separate — DevForge is the UI layer, not the AI itself.)

---

## The 14 Modes

Each mode has its own color, system prompt, and quick-action buttons. Claude behaves differently depending on the active mode.

| Mode | Color | What It Does |
|------|-------|-------------|
| **FORGE** | White | Generates project scaffolding from your design idea. Asks targeted questions, then creates GDD + task list + project rules |
| **GDD** | Green | Maintains your Game Design Document. Updates sections, adds mechanics, checks consistency. Won't write code |
| **PITCH** | Red | Stress-tests your design. Finds scope creep, mechanical contradictions, feature bloat. Recommends what to cut |
| **DISCUSS** | Amber | Open-ended design conversation. Mechanics, lore, design theory. Not code-focused |
| **IMPLEMENT** | Blue | Writes code. Includes GDD context and current phase. Auto-checkpoint option |
| **DEBUG** | Orange | Root cause analysis with minimal collateral changes. Paste screenshots directly |
| **RESEARCH** | Cyan | Live web search, book downloads, trending topic synthesis. Persistent knowledge bank. SETUP RESEARCH onboards tools, WEB SEARCH pulls live data, TRENDING checks game dev community |
| **QA** | Purple | Systematic testing audit with severity ratings (Blocking/Annoying/Cosmetic). Reports issues, doesn't fix them |
| **FREEFORM** | Gray | No guardrails. Think out loud about anything project-related |
| **MARKETING** | Gold | Store listings, devlogs, social posts. Built-in anti-AI-voice filter makes output sound human |
| **INSTRUCT** | Teal | Step-by-step walkthroughs with exact button names and menu paths |
| **TEST** | Lime | Playtest logging. Tag observations as bug/balance/question/working, then route to other modes |
| **SECURITY** | Crimson | OWASP audits, dependency scanning, threat modeling, code review, auth review, data flow mapping. Analog override for rules integrity |
| **UI/UX** | Pink | WCAG compliance, layout review, contrast checking, user flow analysis, responsive audit, accessibility tree. Analog override for component usability |

---

## Analog Mode (Board/Tabletop Games)

Toggle ANALOG in the footer and all 14 modes adapt:

- Implement writes rules text and component specs instead of code
- Debug finds rules contradictions and edge cases
- QA audits rules clarity and component consistency
- Research focuses on published board games and design theory
- Marketing writes Kickstarter pages and BoardGameGeek listings
- FORGE generates tabletop GDDs with turn structures and victory conditions

Includes 14 tabletop-specific skills: Rules Writing, Component Design, Balance & Probability, Hex Map Design, Solitaire Bot Systems, VASSAL Integration, Print & Play Layout, and more.

Design your full board game with Analog ON, then flip to Analog OFF and Implement mode to build a digital version. Your GDD carries over.

---

## 16 Supported Game Dev Stacks

Godot 4, Unity, Unreal, Phaser 3, HTML5 Canvas, Rust, Python/Pygame, Love2D, GameMaker, RPG Maker, PICO-8, GB Studio, NES (cc65), Game Boy (GBDK), Genesis (SGDK), GBA (devkitPro).

Each stack gets context-aware build commands, documentation links, and coding conventions injected into prompts.

---

## Git Safety System

Built for people who don't know git:

- **Session branches** — START creates an isolated branch. Your main code is untouched until you choose to merge
- **Safety snapshots** — Full project backup before every session
- **Diff viewer** — See exactly what changed before committing (green = added, red = deleted, amber = modified)
- **One-click UNDO** — Reverts entire session to the snapshot
- **One-click MERGE** — Merges session work back to main after you've reviewed it

---

## Session Workflow

1. **START** — Creates session branch, assembles context from your GDD + tasks + last session notes + project rules
2. **Work** — Pick a mode, type what you want, send. Claude streams output in real-time. Diff viewer updates automatically
3. **END** — Claude writes session notes, updates task list, commits everything. Or use AI NOTES (free local AI) to write the summary without spending Claude tokens

You never re-explain your project. DevForge handles context automatically.

---

## Context Management (The Key Feature)

Every prompt DevForge sends to Claude includes:

- Your project rules (CLAUDE.md)
- Last session's notes (what happened, what's next, known issues)
- Current phase and task progress
- Relevant GDD sections (you pick which ones in the sidebar)
- Code structure map
- Active skills and stack-specific patterns

This is what makes DevForge different from raw Claude Code. Claude starts every session fully oriented on your project.

---

## UI Overview

**Three-column layout:**

- **Left sidebar** — Projects list, mode selector, GDD section picker, phase tracker, task list, scope meter, skill library
- **Center** — Terminal with streaming Claude output, prompt input, quick-action buttons, screenshot drop zone. Up to 4 parallel terminal tabs with git worktree isolation
- **Right sidebar** — Diff viewer, build status, session log, scratch notes, session history, code browser with syntax highlighting, test log, knowledge bank, quick links

**Footer:** Project count, git status, token usage, AI provider selector, Ollama status, plus toggles for Analog mode, sprites, sound effects, CRT scanlines, UI scale, and theme (CRT Dark / SNES Light).

---

## Skill Library (47 Skills)

Toggle skills ON in the sidebar; they auto-inject best-practice context into prompts.

- **33 digital skills:** State machines, collision detection, camera systems, pathfinding, dialogue trees, save/load, inventory, UI state, animation, audio, particles, shaders, performance, OWASP security auditing, WCAG accessibility, visual diagrams & charts, plus stack-specific conventions
- **14 analog skills:** Rules writing, component design, balance & probability, hex maps, area/point-to-point movement, solitaire bot systems, VASSAL, Tabletop Simulator, print & play layout

---

## Polish & Personality

- **Oryx 8-bit sprites** — 14 randomized pixel characters (knight, mage, archer, etc.) with idle, running, success, and error animations
- **Retro sound effects** — Boot chime, mode switch clicks, send/success/error sounds (all toggleable)
- **CRT scanline overlay** — Subtle retro screen effect (toggleable)
- **Boot animation** — Pixel character plays on launch
- **Anti-AI-voice filter** — 10-rule system strips AI writing patterns from Marketing mode output

---

## Dynamic Learning System

After each session, Ollama analyzes the transcript and suggests project rules — corrections, conventions, gotchas discovered during the session. You review, edit, accept, or reject each rule before it's written to your project's CLAUDE.md. Claude reads CLAUDE.md every session, so the AI gets smarter about your project over time.

- **SAVE RULE** quick action in every mode for manual rule capture
- **Inline rule bar** below the prompt input for quick rule entry
- **Deduplication engine** prevents duplicate rules
- Works without Ollama for manual rules; auto-extraction requires Ollama

---

## Activity Feed & Thinking Display

- **Real-time activity feed** above the terminal shows what Claude is doing: file reads, edits, bash commands, color-coded
- **Thinking display** — toggle to see Claude's reasoning stream as it works
- **Escape-to-cancel** — press Escape to stop Claude mid-execution
- Per-tab activity feeds for worktree tabs

---

## Session Intelligence

- **ASK bot with live Claude context** — while Claude is working, the ASK bot (Ollama, free) can see the current task, activity feed, and recent output. Ask "what is Claude doing right now?" and get a live answer
- **Transcript browser** — every Claude response is saved as markdown. Browse, view, rename, filter, or delete past transcripts. Load a past transcript as context for your next prompt
- **Diagram generation** — quick actions in 8 modes to generate architecture diagrams, flowcharts, infographics, and comparison charts as PNG. Mention "diagram" or "chart" in any task and the render skill auto-injects
- **Auto-complexity indicator** — scope bar auto-calculates project complexity from lines of code, file count, git commits, GDD size, tasks, and stack. In Forge mode it switches to manual target mode

---

## Ollama Integration (Optional, Free)

When Ollama runs locally, DevForge uses it for utility tasks that don't need Claude:

- Smart context briefings on project load
- Session notes writing (AI NOTES button — free, no Claude tokens)
- Code structure summaries
- Diff explanations
- In-app Q&A bot

If Ollama isn't installed, everything works — these features just skip.

---

## Multi-Provider Support

Works with Claude Code (recommended), Aider, OpenAI Codex CLI, and Google Gemini CLI. Click the provider indicator in the footer to switch. DevForge compensates for non-Claude providers with richer automatic context.

---

## Technical Details

- **Tauri 2** — ~5MB binary (vs ~150MB for Electron), ~28MB RAM (vs ~250MB)
- **Vanilla HTML/CSS/JS** — No framework, no bundler
- **Offline-capable** — Works without internet except for AI API calls
- **No telemetry** — All config stored locally
- **Windows 10/11** (macOS/Linux possible on demand)
- **Requires:** Claude Code (or alternative CLI) installed and authenticated

---

## Roadmap (Active Development)

Upcoming features (no dates committed):

- **MOD Mode** — Build mods for Skyrim, Minecraft, Factorio, Rimworld, and other games
- **Git Personalization Panel** — Connect GitHub, create repos, manage branches from inside DevForge
- **Autonomous Terminal Jobs** — Set a worktree tab to a mode and goal, let it work autonomously with time caps
- **Playtest Asset Generation** — Auto-generate wargame counter sheets, hex maps, placeholder tilesets for prototyping
- **Model Selection & Smart Routing** — Pick Opus/Sonnet/Haiku per task, or let DevForge auto-route
- **LENS Mode** — Editorial and sensitivity review for game content and reception

---

## Competitive Position

There is no other game-design-specific AI wrapper on the market. DevForge sits in an open niche between:

- **Raw Claude Code** — powerful but no context management, no modes, no safety net
- **Game engines** — great for building, but no AI integration or design-first workflow
- **Generic AI coding tools** — not game-aware, no GDD integration, no design discipline

---

## Key Messages for the Landing Page

**What to emphasize:**
- Your GDD becomes the source of truth — not vague prompts
- Never re-explain your project between sessions
- 14 specialized modes keep Claude focused on one job at a time
- Claude learns your project rules over time
- See what Claude is doing in real time (activity feed)
- Browse your full conversation history (transcript browser)
- Generate diagrams and visual aids directly
- One-click undo if Claude goes off the rails
- Works with 16 game dev stacks
- Analog mode for board game / wargame designers

**What NOT to say:**
- Don't call it "AI-powered" or "AI-driven" (everyone says that, it means nothing)
- Don't use "seamlessly", "unleash", "elevate", "empower", "revolutionize"
- Don't promise it replaces programmers (it doesn't — it gives designers structured access to AI coding help)
- Don't oversell (the validation assessment says the product needs more real-world testing — be honest and confident, not hype-y)

**Tone:** Direct, specific, slightly irreverent. Like a tool review from someone who actually uses it, not a marketing department.
