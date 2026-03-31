# Devforge Roadmap — Public Version

> For the website bot. This is the customer-facing roadmap to show on the landing page.
> Keep it concise and exciting. No internal process details, no implementation notes.
> Frame everything as user benefits, not technical tasks.

---

## What's Live (v0.2.1)

- 16 specialized modes (FORGE, GDD, PITCH, IMPLEMENT, DEBUG, RESEARCH, QA, FREEFORM, MARKETING, INSTRUCT, TEST, SECURITY, UI/UX, DISCUSS, MOD, PACKAGE)
- 50 built-in game dev skills (37 digital, 13 tabletop)
- 20 supported platforms (Godot GDScript, Godot C#, Unity, Unreal, Rust, Python, Ikemen GO/MUGEN, iOS, Android, and 11 more including retro consoles)
- Godot 4 C# stack with dedicated GodotSharp skill covering source generators, signals, exports, memory management, and Unity migration patterns
- Edit project settings, path validation, last-used project auto-load
- Resizable prompt bar and failed prompt recovery
- Manage learned rules (edit and delete from RULES modal)
- Ollama CORS proxy (no environment variables needed) and auto-reconnect
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
- Activity feed showing what Claude is doing in real time
- Dynamic learning system. Claude gets smarter about your project over time
- Full accessibility audit (WCAG AA compliant)

---

## Coming in v0.3

### Smart Model Routing
Devforge picks the right model for the job automatically. Opus for planning and deep analysis, Sonnet for implementation, Haiku for quick lookups. On by default. Override any time. Complexity-aware: big projects get upgraded automatically.

### Remote Dispatch (Telegram & Discord)
Message Devforge from your phone. Send tasks to a terminal tab or ask the free ASK bot what Claude is doing. Bot confirms before expensive work, respects your daily budget. Send and receive screenshots, concept art, and asset previews. Works with voice messages too.

### LENS Mode
Editorial review for your game's content. Flags representation issues, content rating implications, and regional sensitivity before your players find them. PITCH stress-tests your design. LENS stress-tests your perception.

### More Languages in Code Browser
Syntax highlighting for all 20 stacks. Swift, Kotlin, Ruby, Assembly, and MAME added. Every stack's primary language works in the built-in code viewer.

### Full Skill & Research Audit
Research sweep across all 20 stacks to fill gaps and validate coverage. Includes:
- Multiplayer infrastructure (traditional, MMO, and async patterns like Dark Souls and Journey)
- 3D game dev tooling (Blender pipelines, shaders, rigging, LOD, navmesh)
- Pen & paper RPG systems and open SRDs
- Per-stack community research to find what developers actually struggle with

### MOD Mode Expansion
Strategy and simulation game modding (Dominions 6, Conquest of Elysium 5, Aurora 4X, Dwarf Fortress). ROM hacking for classic consoles (Super Mario World, Zelda, Sonic, Pokemon). Arcade ROM modding via MAME.

### Usage Alerts & Burn Rate Monitoring
Set budget thresholds. Get notified at 50%, 75%, 90% of your daily spend. Live burn rate tracking catches runaway tasks. Auto-pause autonomous tabs if costs spike. See exactly how much Ollama saved you in concrete dollar amounts.

### Pen & Paper RPG Design
Full tabletop RPG design support in analog mode. Dice system design, character creation frameworks, class/archetype building, encounter balance, bestiary generation. Pulls from open SRDs (d20, Fate, Powered by the Apocalypse). Generates fillable character sheets, GM screens, and random tables.

### Localization & Translation
Translate your game for regional distribution. Extract strings, translate to any language, generate locale files in the right format for your stack. Syncs translations when source text changes. Lives in PACKAGE mode because localization is part of shipping.

### Art Asset Pipeline
Free, browser-based art generation. Nano Banana generates base sprites, Grok animates them as video loops, SpriteMaster converts video to sprite sheets. Devforge orchestrates the pipeline with your project context. ComfyUI as a local alternative for offline work.

### Native System Notifications
Task completion notifications that work when Devforge is minimized. System tray alerts, taskbar progress bar, and Telegram/Discord pings when you're away from the machine.

### Devforge MCP Server
Use Devforge's modes, skills, and context system from inside VS Code, Cursor, or raw Claude Code. Free and open source. Built last so it includes everything from v0.3.

---

## v0.4 and Beyond

### ASK Bot Enhancements
Selectable portrait, pop-out as a floating window, portrait reactions to conversation.

### Sprite Visualizer
Watch pixel characters "work" on your code in an animated forge scene. Activity feed drives sprite behavior. Reading a file makes a character open a book, running tests pulls a lever.

### Remote Visualizer
Stream the sprite visualizer to your phone. Watch your workers from the couch.

### Devforge Companion App
Native iOS/Android app. Remote dispatch, ASK bot, usage monitoring, task progress, and visualizer stream in one place.

### Voice Input
Speak prompts instead of typing. Mic button next to BUILD & SEND. Works with Telegram and Discord voice messages too.

### Can It Run Doom?
Yes.

---

## How to Present This on the Website

- v0.3 is a major release. Lead with smart model routing and remote dispatch as headlines
- The art pipeline and RPG support are the most shareable items
- Multiplayer infrastructure is the broadest audience expansion
- "Devforge saved you $47 this month" (Ollama savings) is a concrete selling point worth highlighting
- The MCP server being free and open source shows confidence in the product
- Keep the tone direct. "Coming soon" not "we're excited to announce"
