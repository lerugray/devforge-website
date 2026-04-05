# Devforge Roadmap — Public Version

> For the website bot. This is the customer-facing roadmap to show on the landing page.
> Keep it concise and exciting. No internal process details, no implementation notes.
> Frame everything as user benefits, not technical tasks.

---

## What's Live (v0.2.9)

- 16 specialized modes (FORGE, GDD, PITCH, IMPLEMENT, DEBUG, RESEARCH, QA, FREEFORM, MARKETING, INSTRUCT, TEST, SECURITY, UI/UX, DISCUSS, MOD, PACKAGE)
- 50 built-in game dev skills (37 digital, 13 tabletop)
- 20 supported platforms (Godot GDScript, Godot C#, Unity, Unreal, Rust, Python, Ikemen GO/MUGEN, iOS, Android, and 11 more including retro consoles)
- Godot 4 C# stack with dedicated GodotSharp skill covering source generators, signals, exports, memory management, and Unity migration patterns
- Multi-provider support (Claude Code, Aider, Codex CLI, Gemini CLI) with reliable file detection and real-time streaming on all providers
- Gemini CLI runs with full activity feed, session resume, and auto-approval — same experience as Claude Code
- Edit project settings, path validation, last-used project auto-load
- Resizable prompt bar and failed prompt recovery
- Manage learned rules (edit and delete from RULES modal)
- Ollama CORS proxy (no environment variables needed) and auto-reconnect
- Automated test suite (Rust backend + JS smoke tests)
- MOD mode for modding Skyrim, Minecraft, Factorio, RimWorld, Stardew Valley, and BepInEx/Unity games
- PACKAGE mode for stack-aware build and distribution. itch.io, Steam, app stores, mod workshops, retro ROMs
- Fighting game support (Ikemen GO / MUGEN) with character creation, state machines, hitbox patterns, and frame data
- iOS and Android mobile development stacks
- Autonomous terminal tabs. Set a time budget, lock a mode, let Claude work solo
- Git panel. Version control in game-dev language (save points, timelines, upload/download)
- Model picker. Choose Opus, Sonnet, or Haiku per task
- Playtest asset generation. Counter sheets, hex maps, player aids, placeholder tilesets
- Mode-specific sprites, FX events, and boss milestones
- Live research with web search, book search, and trending topic tools
- Transcript browser. Browse, view, and reference your full conversation history
- Auto-complexity indicator that reads your project's actual size
- Activity feed showing what Claude is doing in real time (clears properly between projects, CLEAR button works)
- Dynamic learning system. Claude gets smarter about your project over time
- Full accessibility audit (WCAG AA compliant)
- Clean terminal output: Node.js deprecation warnings and other CLI noise suppressed
- Gemini CLI works with prompts of any size on Windows (piped via stdin, no command line limits)
- Missing provider detection: clear install instructions when a CLI isn't found
- Reliable CLI path resolution across all Node.js setups (nvm, volta, standard npm)
- Forge mode respects "ask me questions" — won't generate files until you say go
- Clean terminal output: Gemini console noise, Node.js warnings, and other CLI artifacts suppressed

---

## Coming in v0.3 — Smarter Routing, Cost Control & Visibility

### Smart Model Routing
Devforge picks the right model for the job automatically. Opus for planning and deep analysis, Sonnet for implementation, Haiku for quick lookups. On by default. Override any time. Complexity-aware: big projects get upgraded automatically.

### Usage Alerts & Burn Rate Monitoring
Set budget thresholds. Get notified at 50%, 75%, 90% of your daily spend. Live burn rate tracking catches runaway tasks. Auto-pause autonomous tabs if costs spike. See exactly how much Ollama saved you in concrete dollar amounts.

### Smarter Autonomous Tabs
Ollama reads your task list and feeds tasks to Claude one at a time. Autonomous tabs become actual multi-step workflows instead of single prompts. Progress reports after each step.

### ASK Bot Upgrade
Pop-out as a floating window that stays open while Claude works. Selectable pixel art portrait. Portrait reacts to conversation. Non-programmers get a persistent, friendly guide visible at all times.

### LENS Mode
Editorial review for your game's content. Flags representation issues, content rating implications, and regional sensitivity before your players find them. PITCH stress-tests your design. LENS stress-tests your perception.

### More Languages in Code Browser
Syntax highlighting for all 20 stacks. Swift, Kotlin, Ruby, Assembly added. Every stack's primary language works in the built-in code viewer.

### Stack-Aware Test Automation
TEST mode becomes a full automated testing hub. Devforge picks the right test framework for your stack and generates a test suite. Run tests from a button, see pass/fail results in the activity feed, and failed tests auto-route to Debug mode with context pre-filled. Config validation for stacks where you can't run the game directly: file consistency checks for Ikemen GO characters, mod structure validation, ROM header checks. Works across all 20 platforms.

### Native System Notifications
Task completion notifications that work when Devforge is minimized. System tray alerts, taskbar progress bar.

### Anonymous Usage Insights
Opt-in, transparent, no personal data collected. Help us understand which features you use and where you hit friction. You can view exactly what gets sent before opting in. Off by default.

---

## v0.4 — Content Depth & Project Visualization

### Full Skill & Research Audit
Research sweep across all 20 stacks to fill gaps and validate coverage. Includes:
- Multiplayer infrastructure (traditional, MMO, and async patterns like Dark Souls and Journey)
- 3D game dev tooling (Blender pipelines, shaders, rigging, LOD, navmesh)
- Pen & paper RPG systems and open SRDs
- Per-stack community research to find what developers actually struggle with
- Curated open source tool and engine catalog integrated into quick links across all modes

### MOD Mode Expansion
Open source game modding: Doom, Quake, Diablo, Duke Nukem 3D, and more — games with public source code and active modding communities. Source repos and community links built in. Strategy and simulation game modding (Dominions 6, Conquest of Elysium 5, Aurora 4X, Dwarf Fortress). ROM hacking for classic consoles (Super Mario World, Zelda, Sonic, Pokemon). Arcade ROM modding via MAME.

### Pen & Paper RPG Design
Full tabletop RPG design support in analog mode. Dice system design, character creation frameworks, class/archetype building, encounter balance, bestiary generation. Pulls from open SRDs (d20, Fate, Powered by the Apocalypse). Generates fillable character sheets, GM screens, and random tables.

### Art Asset Pipeline
Free, browser-based art generation. Nano Banana generates base sprites, Grok animates them as video loops, SpriteMaster converts video to sprite sheets. Devforge orchestrates the pipeline with your project context. ComfyUI as a local alternative for offline work.

### Obsidian Vault Export
One-click export of your project's GDD, session notes, transcripts, research, and task lists into a linked Obsidian wiki. Graph view turns your project history into a visual knowledge map. Works with any markdown wiki tool.

---

## v0.5 — Ship & Share

### Localization & Translation
Translate your game for regional distribution. Extract strings, translate to any language, generate locale files in the right format for your stack. Syncs translations when source text changes. Lives in PACKAGE mode because localization is part of shipping.

### Devforge MCP Server
Use Devforge's modes, skills, and context system from inside VS Code, Cursor, or raw Claude Code. Free and open source.

### Remote Dispatch (Telegram)
Message Devforge from your phone. Send tasks to a terminal tab or ask the free ASK bot what Claude is doing. Bot confirms before expensive work, respects your daily budget. Send and receive screenshots and concept art.

---

## Idea Bank

- **Sprite Visualizer** Watch pixel characters "work" on your code. Activity feed drives sprite behavior.
- **Companion App** Native iOS/Android app for remote dispatch, ASK bot, and usage monitoring.
- **Voice Input** Speak prompts instead of typing. Mic button next to BUILD & SEND.
- **Can It Run Doom?** Yes.

---

## How to Present This on the Website

- v0.3 leads with smart model routing, test automation, and the ASK bot upgrade as headlines
- Stack-aware test automation is a strong differentiator — no other tool generates tests that know your game engine
- Usage alerts and "Devforge saved you $47 this month" (Ollama savings) is a concrete selling point
- v0.4's art pipeline and RPG support are the most shareable items
- Multiplayer infrastructure is the broadest audience expansion
- The MCP server being free and open source shows confidence in the product
- Keep the tone direct. "Coming soon" not "we're excited to announce"
