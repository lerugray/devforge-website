# Devforge Roadmap

> v0.1 shipped 2026-03-28. This is the plan for what comes next.

## v0.2 Features

### 1. MOD Mode (15th mode)
For developing mods for established games (Skyrim, Minecraft, Factorio, Rimworld, etc.)
- Quick actions: SETUP MOD PROJECT, ADD CONTENT, HOOK EVENT, TEST MOD, PACKAGE FOR WORKSHOP
- Game-specific modding skills in skill library (Unity mod patterns, Bethesda plugins, Source engine)
- Expands audience from "making games from scratch" to "modifying existing games"
- Modding is how many developers start — this is a gateway to full game dev with Devforge

### 2. Git Personalization Panel
First-class git UI inside Devforge — connect GitHub account, create repos, manage branches, push/pull.
- Currently SETUP GIT in Implement mode is a one-shot Claude prompt, not a built-in flow
- Removes another technical barrier for non-programmers who don't know terminal git
- Scope question: full GitHub OAuth/API integration vs git CLI wrappers with nice UI

### 3. Autonomous Terminal Jobs
Set a worktree tab to a mode + goal, let it work autonomously through a task sequence.
- Mode constrains scope: Debug tab only fixes bugs, Implement tab only writes code
- Ollama orchestrates the sequence, Claude Code executes each step
- Usage time cap per run (e.g., "run for 30 min max") — CC subscriptions are time-based (5hr/day), not cost-based
- Target: power users on $100/mo who want parallel development or stress testing
- 4 worktree tabs could each work on a different phase simultaneously

### 4. Playtest Asset Generation
Generate functional playtest graphics via Python rendering (matplotlib/pillow).

**Analog (high feasibility):**
- Wargame counter sheets from order-of-battle data in GDD
- Hex maps with terrain types
- Player aids and reference cards
- Card layouts for prototyping
- Wargame designers redo counter sheets by hand every playtest cycle — this saves hours

**Digital (moderate feasibility):**
- Placeholder tilesets (colored squares with labels: WALL, FLOOR, DOOR, WATER)
- Simple sprite sheets for prototyping
- UI wireframe images
- Not final art — functional enough to playtest with, replaced later

Could tie into FORGE: after generating GDD, offer to generate starter playtest materials.

### 5. Model Selection & Smart Routing
Model picker dropdown next to the provider selector.

**Simple (v0.2):**
- Dropdown showing available models per provider (Opus/Sonnet/Haiku for Claude Code)
- One-line descriptions so users know what each is good for
- Passes --model flag to Claude Code

**Advanced (v0.3+):**
- Auto-routing based on mode + complexity + task length
- Opus for FORGE/IMPLEMENT/SECURITY/DEBUG, Sonnet for analysis modes, Haiku for simple tasks
- "Suggested model" indicator next to dropdown, user can override
- Cross-provider routing: Claude for code, Gemini for research, Ollama for lightweight tasks
- Extends the existing smart routing (which already routes to Ollama) to paid providers

### 6. Research Tool Onboarding
Research mode already works with live data IF the user has web search / MCP tools installed in Claude Code. Most users don't, and it's not obvious they're getting stale training data instead of live results.

**Goal:** Make it easy and explicit to set up live research capabilities.
- SETUP RESEARCH quick action (like SETUP GIT) that walks users through installing tools
- Recommended tools listed in-app with one-click setup instructions:
  - **Agent-Reach** (github.com/Panniantong/Agent-Reach) — web, YouTube, Reddit, Twitter/X, RSS
  - **Last30Days** (github.com/mvanhorn/last30days-skill) — trending topic synthesis across platforms
  - **bookfinder-general** (already documented) — book search and summarization
- Research mode could detect whether web tools are available and show a hint if not
- More of a documentation/onboarding improvement than a code feature

### 7. LENS Mode (v0.3)
Editorial and sensitivity review — stress-tests your game's content for reception and perception.
- Flags cultural representation issues, uncomfortable mechanic parallels, content rating implications, regional sensitivity
- Not censorship — flags and explains, you decide. Like PITCH for design, LENS is for perception.
- Quick actions: CONTENT REVIEW, REPRESENTATION CHECK, RATING ASSESSMENT, REGIONAL SCAN, LANGUAGE AUDIT
- Analog version: faction naming, historical framing, component art descriptions, gendered rule language
- System prompt needs careful writing to be useful without being preachy — benefits from real user feedback first
- Placed in v0.3 to allow v0.2 users to inform what the mode should prioritize

### 7. Wargame Design Skills (Analog Mode)
Wargame-specific skills for the analog skill library.
- Hex grid systems, combat results tables (CRTs), zones of control, supply lines
- Order of battle design, scenario design, victory conditions
- Skills can reference user's own framework from their wargame design book
- **Status:** Deferred until the book is further along

## Completed (v0.1)

### Phase 1-7: Foundation
- Tauri 2 desktop app, CRT dark + SNES light themes
- 14-mode system with analog overrides
- Claude Code integration with streaming, session resume
- Project management, GDD auto-parse, knowledge banks
- Session safety (branches, snapshots, undo, phase guard)
- Multi-provider support (Claude, Aider, Codex, Gemini)
- Ollama integration (briefings, code maps, prompt expansion, AI notes, smart routing)
- Parallel terminal tabs with git worktree isolation
- 16 supported platforms, skill library, quick links

### Phase 8: Learning System
- Dynamic CLAUDE.md rule extraction via Ollama
- Review modal, SAVE RULE quick action, inline rule bar, deduplication

### Phase 9: Activity & Thinking
- Real-time activity feed (tool calls, file reads, edits, commands)
- Thinking display, escape-to-cancel, per-tab feeds

### Phase 10: Security & UI/UX Modes
- SECURITY mode (OWASP, dependency scan, threat model)
- UI/UX mode (WCAG, layout review, contrast, accessibility)
- Both with analog overrides, knowledge banks, dedicated skills

### Phase 11: Session Intelligence
- ASK bot with live Claude context (sees running task, activity, output)
- Transcript browser (browse, view, rename, filter, delete, use-as-context)
- Render skill + diagram quick actions in 8 modes
- Auto-complexity indicator (dual-mode scope bar)
- Full UI/UX accessibility audit and fixes
- 47 skills (33 digital, 14 analog), 14 modes, 16 stacks
