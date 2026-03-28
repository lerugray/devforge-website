# DevForge Website Update Brief — v0.1 Release

> For the website bot. These are all changes since the product_brief.md was written.
> Update the website and product_brief.md to reflect these changes.

---

## Numbers That Changed

| What | Old | New |
|------|-----|-----|
| Modes | 12 | **14** (added SECURITY + UI/UX) |
| Skills | 44 | **47** (added OWASP Security, WCAG Accessibility, Visual Diagrams & Charts) |
| Price | $20 | Keep whatever the website currently shows |

---

## New Features to Add to the Website

### Phase 8: Dynamic Learning System
- **CLAUDE.md auto-learning** — after each session, Ollama analyzes the transcript and suggests project rules (corrections, conventions, gotchas). Review, edit, accept, or reject each rule before it's written to your project's CLAUDE.md
- Claude Code reads CLAUDE.md every session, so the AI gets smarter about your project over time
- **SAVE RULE quick action** in every mode for manual rule capture
- **Inline rule bar** below the prompt input for quick rule entry
- **Deduplication engine** prevents duplicate rules
- Works without Ollama for manual rules; auto-extraction requires Ollama

### Phase 9: Activity Feed & Thinking Display
- **Real-time activity feed** above the terminal shows what Claude is doing: file reads, edits, bash commands, color-coded
- **Thinking display** — see Claude's reasoning/thinking stream (toggleable via THINKING button)
- **Escape-to-cancel** — press Escape to stop Claude mid-execution
- Per-tab activity feeds for worktree tabs

### Phase 10: Two New Modes
- **SECURITY mode** (crimson) — OWASP audit, dependency scan, threat model, code review, auth review, data flow mapping. Has analog override for rules integrity auditing
- **UI/UX mode** (pink) — WCAG audit, layout review, contrast check, user flow, responsive audit, accessibility tree. Has analog override for component usability

### Phase 11: Session Intelligence
- **ASK bot with live Claude context** — while Claude is working, the ASK bot (Ollama, free) can see the current task, activity feed, and recent output. Ask "what is Claude doing right now?" and get a live answer. Header shows "USE ASK FOR QUESTIONS" hint during execution
- **Transcript browser** — every Claude response is saved as a markdown transcript. Click TRANSCRIPTS to browse, view, rename, filter, or delete past transcripts. Click CTX to load a past transcript as context for your next prompt
- **Diagram generation** — quick actions in 8 modes (GDD, Implement, Instruct, Marketing, Discuss, Research + analog variants) to generate architecture diagrams, flowcharts, infographics, and comparison charts as PNG. Mention "diagram" or "chart" in any task and the render skill auto-injects
- **Auto-complexity indicator** — the scope bar auto-calculates project complexity from lines of code, file count, git commits, GDD size, tasks, and stack. In Forge mode it switches to manual "TARGET" mode with a green glow for setting desired complexity

### UI/UX Audit Improvements (both phases)
- SVG pixel-art panel icons (replaced emoji)
- Focus-visible styles on all interactive elements
- prefers-reduced-motion support
- WCAG AA contrast compliance
- 8px minimum font size
- Keyboard accessible project selection and interactive elements
- ARIA roles on scope bar, collapsible panels, modals
- SNES theme border contrast fixed for WCAG 1.4.11

### Layout Changes
- Right sidebar reorganized into SESSION / PROJECT / TEST tabs
- Scratch Notes, Quick Links, Session History moved to header-button modals
- Scope meter and Build Status compacted into context bar chips
- Tool buttons (AI NOTES, RULES, RESEARCH, SHARE, HISTORY, LINKS, NOTES, TRANSCRIPTS) in context bar

---

## Updated Mode Table (14 modes)

| Mode | Color | What It Does |
|------|-------|-------------|
| **FORGE** | White | Generates project scaffolding from your design idea |
| **GDD** | Green | Maintains your Game Design Document |
| **PITCH** | Red | Stress-tests your design for scope and feasibility |
| **DISCUSS** | Amber | Open-ended design conversation |
| **IMPLEMENT** | Blue | Writes code with GDD context and phase guard |
| **DEBUG** | Orange | Root cause analysis with minimal collateral changes |
| **RESEARCH** | Cyan | Persistent knowledge bank with book search |
| **QA** | Purple | Systematic testing audit with severity ratings |
| **FREEFORM** | Gray | No guardrails, think out loud |
| **MARKETING** | Gold | Store listings, devlogs, social posts with anti-AI filter |
| **INSTRUCT** | Teal | Step-by-step walkthroughs with exact paths |
| **TEST** | Lime | Playtest observation logging with routing |
| **SECURITY** | Crimson | OWASP audits, dependency scanning, threat modeling |
| **UI/UX** | Pink | WCAG compliance, layout review, accessibility audit |

---

## Updated Skill Library (47 skills)

- 33 digital skills (was 30): added OWASP Security, WCAG Accessibility, Visual Diagrams & Charts
- 14 analog/tabletop skills (unchanged)

---

## Key Messaging Updates

- "12 modes" → "14 specialized modes"
- "44 skills" → "47 built-in skills"
- Add: "Claude learns your project rules over time" (the learning system is a differentiator)
- Add: "See what Claude is doing in real time" (activity feed)
- Add: "Browse your full conversation history" (transcript browser)
- Add: "Generate diagrams and visual aids directly" (render skill)
- Add: "Auto-calculated project complexity" (complexity indicator)
- The SECURITY and UI/UX modes strengthen the "game dev specific" angle — these aren't generic, they have game-specific quick actions

---

## What NOT to Change

- Core positioning (GDD-first, mode-based discipline, git safety)
- Target audience (game designers, not programmers)
- Tone (direct, specific, no AI hype)
- The competitive position section is still accurate
