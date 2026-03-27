# DevForge Website — Project Brief for Claude Code

## What This Is

A static single-page landing site for **DevForge**, a desktop game development environment (Tauri 2 app) that wraps Claude Code in a structured UI for game designers. This site lives on GitHub Pages (free hosting).

The actual DevForge app lives at `~/OneDrive/Documents/Devforge/`. Planning docs live at `~/OneDrive/Documents/PIH/Ideas/DevForge/`.

---

## Who the User Is

Not a programmer. Comfortable following instructions and installing tools, but needs things explained. Works a day job and builds this in spare time. See PIH project for full user profile.

---

## Anonymity Rule

**No real name AND no "Conflict Simulations LLC" on any public-facing content.** This is a hard rule. Use "DevForge" as the brand only.

---

## What the Page Needs

1. **Headline** — what DevForge is in one sentence
2. **3-4 feature bullets** — modes, git safety, GDD-as-source-of-truth, context management
3. **Screenshot or GIF** — placeholder for now, will be replaced with real screen recording
4. **"Buy on Itch — $20" button** — links to Itch.io page (URL TBD)
5. **Mailing list signup** — for people not ready to buy (provider TBD — Buttondown or Mailchimp free tier)

## What It Does NOT Need (Yet)

- Blog, docs, multi-page anything
- Custom domain (use GitHub Pages free URL)
- Payment processing (Itch handles that)
- JavaScript framework — plain HTML/CSS is fine

---

## Visual Design

The website MUST match DevForge's visual identity. The full design brief is at `visual_design_brief.md` in this repo.

**Key points:**
- **CRT Dark theme** as the default (deep navy-black backgrounds, neon accents)
- **Press Start 2P** (pixel font) for headings and UI chrome
- **Share Tech Mono** for body text
- Both fonts bundled as woff2 in `assets/fonts/` — no CDN
- Green (#00ff88) primary action color, amber (#ffaa00) secondary
- 4/8/12/16px spacing grid
- Retro terminal/hacker aesthetic with subtle CRT scanline overlay
- All colors must pass WCAG AA contrast (4.5:1+)

---

## Tech Stack

- Static HTML + CSS (no build step, no framework)
- GitHub Pages hosting (free)
- Fonts bundled locally as woff2
- No JavaScript required unless needed for mailing list embed

---

## File Structure

```
devforge-website/
  index.html          — the landing page
  css/
    style.css         — all styles
  assets/
    fonts/            — Press Start 2P + Share Tech Mono woff2 files
    images/           — screenshots, logo, placeholder images
  visual_design_brief.md — full design spec (reference, not deployed)
  CLAUDE.md           — this file
  .gitignore
```

---

## Deployment

GitHub Pages serves from the root of the `main` branch. No build step needed — just push and it's live.

---

## REQUIRED: Use Design Skills (Not Raw Code)

**Do NOT vibecode this site.** The #1 priority is that this looks like a real product page, not an AI-generated template. To achieve this, you MUST use the following Claude Code skills when building and reviewing the frontend:

### Skills to invoke:

| Skill | What it does | When to use |
|---|---|---|
| `frontend-design` | Production-grade frontend with high design quality | When writing any HTML/CSS for the page |
| `frontend-design-pro` | Jaw-dropping interfaces + real photo URLs from Unsplash/Pexels | When building hero section, picking images |
| `ui-ux-pro-max` | 50+ styles, 161 palettes, 57 font pairings, UX guidelines | When making any design decision (layout, spacing, color) |
| `accesslint:contrast-checker` | WCAG contrast analysis | After setting colors — verify all pass AA |
| `accesslint:refactor` | Auto-fix accessibility issues | After initial build, before final commit |
| `stop-slop` | Remove AI writing patterns from prose | After writing ANY user-facing text (headlines, bullets, descriptions) |

### How to use them:

1. **Before writing any HTML/CSS**, invoke `ui-ux-pro-max` to plan the design approach using the CRT Dark palette and retro terminal style from `visual_design_brief.md`
2. **When building the page**, invoke `frontend-design` or `frontend-design-pro` — do NOT just write raw HTML/CSS from scratch
3. **After writing any copy** (headline, feature bullets, descriptions), invoke `stop-slop` to strip AI writing patterns. Landing page copy must sound like a human wrote it — no "unleash", "seamlessly", "elevate", "empower", or any of the usual AI tells
4. **After building**, invoke `accesslint:contrast-checker` to verify all color pairs pass WCAG AA
5. **Final pass**, invoke `accesslint:refactor` to catch any remaining accessibility issues

### If skills are not installed:

These are Claude Code plugin skills. If they're not available when you start a session, tell the user they need to install them. The install commands are:

```bash
claude mcp add-skill frontend-design
claude mcp add-skill frontend-design-pro
claude mcp add-skill ui-ux-pro-max
claude mcp add-skill accesslint
```

If those exact commands don't work, search for the correct install method — these are community skills/plugins for Claude Code. The user has them installed on their home PC but may need to reinstall on their work ThinkPad.

---

## Key Principles

- Match the app's visual identity exactly — this is a premium tool, not a generic landing page
- Accessibility built in from the start (focus-visible, reduced-motion, contrast)
- Mobile-responsive (single column on small screens)
- Fast — no heavy assets, no JS frameworks, minimal dependencies
- Dense, information-forward design (power-user audience, not consumer)
- **No AI slop** — no generic hero gradients, no "Welcome to DevForge", no stock startup-page patterns. This should feel like a retro terminal, not a SaaS landing page
