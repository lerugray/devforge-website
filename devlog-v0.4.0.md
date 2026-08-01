# DevForge v0.4.0

v0.4.0 is the content-depth release. Platform coverage expands to 20+ engines and targets, AUTO tabs get a real coordinator, and the security surface around session spawning tightens. Every new skill was web-verified against current docs before it shipped. MANUAL and QUICKSTART were rewritten around the autonomy arc so the docs match how people actually run the tool day to day.

**Highlights**

- **103 new stack skills.** Coverage now spans iOS/Android, Godot, Unity, Unreal, Ren'Py, LOVE, GameMaker, RPG Maker, GB Studio, NES/GB/GBA/Genesis, PICO-8, plus 10 classic source-port MOD targets: Doom, Quake 1-3, Diablo, Duke 3D and friends. Stack skills are the prompts and patterns DevForge loads when you pick a platform, so this release is a real breadth jump for MOD and IMPLEMENT work.
- **Run Coordinator sidebar.** Live status for every active AUTO tab, plus crash recovery when a run dies mid-flight. You can see what is still working without flipping through terminals.
- **hands_off.yaml awareness.** AUTO tabs warn before touching files a project marked hand-tuned, so parallel work stops short of your curated assets and hand-edited scenes.
- **Per-provider concurrency caps.** Claude 4 / Gemini 3 / Ollama 2, global 9. The flat limit is gone. Per-tab provider runtime and AUTO-tab resume work end-to-end, with a MERGE action for parallel worktree tabs when you want the results back in the main tree.
- **Security hardening.** Session spawning now uses a hard provider allowlist, closing an arbitrary-executable hole. SSRF allowlist hardening lands with opt-in remote Ollama hosts for people who run models off-box.
- **Obsidian vault export, thinner builds, denser tests.** Export GDD, session notes, transcripts, research, and task lists from the project sidebar. Thin-LTO plus stripping cut download size. The smoke suite grew from 496 to 1085 checks, all green.

Next up from the public roadmap: smarter autonomous tabs that feed the task list one step at a time, stack-aware test suite generation in TEST mode, anonymous usage insights (opt-in, off by default), and the v0.5 Ship & Share arc (localization in PACKAGE mode, a free open-source DevForge MCP server, and Telegram remote dispatch).
