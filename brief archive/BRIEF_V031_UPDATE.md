# Website Update Brief — v0.3.1

> For the website bot. Changes to reflect on the site.

## Version Bump: v0.3.0 -> v0.3.1

The Mac-compat patch release. Wraps up the v0.3 arc with the
cost-transparency stack, two new modes (LENS + the TEST mode
REPORT button), the local-only Habits dashboard, the ASK Bot
pop-out, native notifications, and a long-overdue path-join
bugfix that turned out to silently strand every Mac/Linux v0.3.0
user's data. Bundle identifier renamed and a migration shim
recovers data from both the old proper-path and the malformed
legacy path.

The "What's Live" header should update to v0.3.1.

## What Changed

### Mac compatibility (the headline)

Devforge now ships on macOS 14+ (Apple Silicon) in addition to
Windows 10/11. The itch listing's "macOS/Linux when demand
exists" line is obsolete — Mac is shipping. Linux is not.

- **Apple Silicon `cargo tauri build`** clean, produces both
  `.app` and `.dmg`.
- **Native notifications** via `tauri-plugin-notification`:
  NSUserNotification on Mac, Windows Toast on Win. Devforge pings
  you when long Claude runs finish even if minimized.
- **Bundle identifier** renamed from `com.devforge.app` to
  `com.devforge.Devforge` to clear a macOS `.app`-collision
  warning. Migration shim recovers v0.3.0 user data from the old
  bundle's data dir — fully transparent on first v0.3.1 launch.
- **`joinPath` helper + path-join bugfix** — Tauri's
  `appDataDir()` returns no trailing separator on Mac/Linux, so
  v0.3.0's naive concat produced a malformed sibling path. EVERY
  Mac/Linux v0.3.0 user's projects, banks, history, voice
  profile, and prompt favorites went to the wrong place. The
  v0.3.1 migration shim now checks both candidate paths and writes
  to the correct one. (Windows users were unaffected.)
- **`customPrompt()` async modal** — replaces `window.prompt()`
  which silently no-ops in WKWebView on Mac.

### Cost transparency (Claude only)

A new live stack of cost surfaces. Every visualization is sourced
from Claude's `total_cost_usd` per result event — no estimation
guesswork, no subscription-time-burn confusion.

- **Pre-send dollar estimate** next to the token count
  (`~3374 tok | ~$0.01`). Uses list pricing for whichever model
  auto-routing picks, so Forge/Debug/Security read Opus pricing,
  most others read Sonnet, short prompts read Haiku.
- **Live running-cost chip** in the activity feed header
  (`~$0.04 running`). Updates from streaming chars during a
  Claude session. Color escalation: amber → orange at $0.25 →
  red at $1+.
- **Burn-rate alert** — chip pulses red and appends rate
  (`· 142 t/s`) when output sustains above 100 tok/sec for 3
  seconds. Catches runaway responses in autonomous tabs before
  they cost a session's worth of credit.
- **Daily / weekly budget caps** — set in STATS. Going over
  triggers a soft confirm dialog, never a hard block. Weekly is
  a rolling 7-day window.
- **STATS cost cards** — Total Spent, Avg Cost / Prompt,
  Today's Spend, This Week's Spend, plus a Top Spend by Project
  bar chart.
- **Always-visible Today's-spend chip** in the footer; click
  opens STATS.
- **Ollama Savings dollarized** — card subtitle shows the dollar
  estimate of what locally-routed requests would have cost on
  Sonnet input rate.

### LENS mode (17th)

Editorial and sensitivity reviewer. Stress-tests how content
will be perceived: cultural representation, mechanic parallels,
content rating implications (ESRB/PEGI/CERO), regional sensitivity
(China content rules, German violence laws, Australian
classification, etc.), language audit. *PITCH stress-tests your
design; LENS stress-tests your perception.* Five quick actions,
analog override, Ctrl+Shift+5 shortcut. Not a censor — surfaces
concerns with severity tiers (Notable / Concerning / High-risk)
and 2-3 options per finding including "leave as-is and document
the intent."

### Other new features

- **TEST mode REPORT button** — generates a structured markdown
  playtest report from the current test log (auto-grouped by tag:
  Bugs → Rules → Balance → Timing → Questions → Feedback →
  Working → Notes). COPY to clipboard or SAVE TO FILE writes
  `playtest-YYYY-MM-DD-HHmm.md` to the project root.
- **HABITS · LAST 7 DAYS in STATS** — four self-insight cards from
  data Devforge already collects: Top Mode, Avg Prompts / Session,
  Peak Spend Day, Active Days (n / 7). All computed locally.
- **ASK Bot pop-out** — Click POP OUT in the ASK modal to detach
  the bot into its own Tauri secondary window. Live context flows
  main → pop-out: claudeRunning, task, mode, elapsed runtime,
  last 10 activity-feed entries, last 500 chars of streamed text.
  Polls every 3 seconds plus on every send. Stays visible during
  mode switches.
- **Code Browser language coverage** expanded from 14 to 20:
  added Swift (iOS), Kotlin (Android), Ruby (RPG Maker),
  asm6502 (NES), INI (Ikemen `.def`/`.cns`/`.cmd`); `.p8`
  (PICO-8) maps to existing Lua core grammar.

### Infrastructure

- Smoke test suite expanded from 243 to 496 checks (+253). All
  green. Rust suite still 11 / 11.

## What to Update on the Site

### Hero / feature section
- Add **Mac support** as a headline feature. Currently the site
  positions Windows-only.
- Add **cost transparency** as a feature card or bullet —
  pre-send estimate, live running chip, daily/weekly caps,
  per-project breakdowns.
- Add **LENS mode** to whatever surfaces the mode list.
- Mention **native notifications** in the feature copy somewhere.

### Mode list
Total is now **17 modes**. Current site likely says 12 or 16.
Full list: Forge, GDD, Pitch, Discuss, Implement, Debug,
Research, QA, Freeform, Marketing, Instruct, Test, Security,
UI/UX, Mod, Package, **Lens**.

### Platform stacks
**20 stacks** now (was 14 or 16 depending on version). New
additions: Swift/iOS, Kotlin/Android, Ruby/RPG Maker, asm6502/NES,
INI/Ikemen GO. PICO-8 (`.p8`) routes to the existing Lua grammar.

### Requirements / system requirements
Drop "macOS/Linux when demand exists." Replace with:
- Windows 10/11 **or macOS 14+ (Apple Silicon)**
- Claude Code CLI installed (or Aider, Codex CLI, Gemini CLI)
- Optional: Ollama for free local AI features

### Pricing (if surfaced)
The itch listing shows **$9 (early access, one-time)** as of
2026-05-03. Match if the website currently shows a different
price.

### Reliability / "behind the scenes" section
- **496 smoke tests** (was 243). +253 tests in v0.3.1 covering
  pop-out capability, bundle ID migration, malformed-path
  fallback, joinPath usage, Mac path validation, fs scope.
- The migration shim recovered v0.3.0 user data on first v0.3.1
  Mac launch — verified live during the Mac handoff session.

### Version number
Update any version references from v0.3.0 to v0.3.1.

### itch.html mirror
The repo has both `index.html` and `itch.html`. Both need the
v0.3.1 bump. The itch.html copy should mirror the new
`docs/ITCH_LISTING.md` in the main devforge repo (already updated
2026-05-03).

## Why This Matters

v0.3.1 is the bridge from "Windows-only Devforge" to "real
multi-platform tool." The first paying customer landed on
2026-05-02 (a $9 early access purchase from itch.io); the Mac
shipped the following day. The cost-transparency stack is
prep-work for the realistic concern paying users have about how
much Devforge sessions actually cost when running through their
own Claude subscription.

The Mac launch + cost transparency + LENS mode together cover
the three things v0.2.x users were most explicitly asking for in
external feedback (Mac availability, knowing what a session
costs before sending, and a reviewer-class mode for content
sensitivity work).

## Source

Changes pushed to `devforge` main as of 2026-05-03 09:00 EDT.
- Tauri config at `src-tauri/tauri.conf.json` reads
  `version: "0.3.1"`, identifier `com.devforge.Devforge`.
- Windows installer + MSI at
  `src-tauri/target/release/bundle/{nsis,msi}/Devforge_0.3.1_*`
  (built 2026-05-03 home-PC).
- Mac `.app` + `.dmg` to be built on a Mac session (toolchain
  notes in `HANDOFF-2026-05-02-mac-compat.md`).
- Updated MANUAL.pdf + QUICKSTART.pdf at `docs/MANUAL.pdf` /
  `docs/QUICKSTART.pdf`.
- Updated itch listing copy at `docs/ITCH_LISTING.md`.

ROADMAP_PUBLIC.md may need updating to reflect v0.3.1 completion
and whatever's next on the v0.4.0 horizon.
