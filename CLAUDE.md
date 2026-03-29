# DevForge Website — Project Brief for Claude Code

## What This Is

A static single-page landing site for **DevForge**, a desktop game development environment (Tauri 2 app) that wraps Claude Code in a structured UI for game designers. This site lives on GitHub Pages (free hosting).

The actual DevForge app lives at `~/OneDrive/Documents/Devforge/`. Planning docs live at `~/OneDrive/Documents/PIH/Ideas/DevForge/`.

---

## Current State (Updated 2026-03-27)

The landing page is built and live. SNES Light theme, Space Mono body font, Press Start 2P pixel headings. All content written, all colors WCAG AA verified, all copy run through stop-slop.

**What's done:**
- Full page with all sections (hero, positioning, features, screenshot placeholder, modes grid with modals, analog mode, session workflow, parallel terminals, tools, skills, stacks, providers, platform support, details grid, buy CTA, mailing list)
- SNES Light theme (cream base, muted accent colors)
- Space Mono (body) + Press Start 2P (headings) fonts bundled
- Interactive mode grid (click any mode for a description modal)
- $9 early access pricing, Windows-first with Mac/Linux tester callout
- Honest provider section (Claude Code tested, others configured but untested)
- WCAG AA contrast verified on all color pairs
- Accessibility: skip link, focus-visible, reduced-motion, semantic HTML, heading hierarchy

**Placeholders still needed:**
- Screenshot/GIF of the actual app (currently a dashed-border placeholder)
- Itch.io buy button URL (currently href="#")
- Mailing list form provider (currently action="#", needs Buttondown or Mailchimp)

---

## Who the User Is

Not a programmer. Comfortable following instructions and installing tools, but needs things explained. Works a day job and builds this in spare time.

---

## Anonymity Rule

**No real name AND no "Conflict Simulations LLC" on any public-facing content.** This is a hard rule. Use "DevForge" as the brand only.

---

## Visual Design

**SNES Light theme** (changed from CRT Dark during initial build — lighter theme works better for a sales page):
- Cool gray base (#E8E6ED), console gray inset (#D3D3D6), darker surface (#C8C7CC)
- Muted accent colors: green (#336533), amber (#725721), blue (#405b87), red (#8c4747), purple (#5c4fa0), cyan (#256262), teal (#245f43), orange (#7a3d1a), gold (#6a5218), lime (#44712b)
- Text: dark charcoal (#2D2B3D), dim (#4A485F)
- Borders: mid-gray (#9A99A0), stronger (#8B8A8D)
- All colors pass WCAG AA (4.5:1+) on both base and inset backgrounds

**Typography:**
- **Press Start 2P** (pixel font) for headings and UI chrome (bundled woff2)
- **Space Mono** for body text (bundled woff2, replaced Share Tech Mono)
- Share Tech Mono woff2 still in assets/fonts/ but no longer used on the website

**Spacing:** 4/8/12/16px grid

---

## Tech Stack

- Static HTML + CSS + minimal vanilla JS (mode modals)
- GitHub Pages hosting (free)
- Fonts bundled locally as woff2
- No build step, no framework

---

## File Structure

```
devforge-website/
  index.html              — the landing page
  css/
    style.css             — all styles
  assets/
    fonts/
      PressStart2P-Regular.woff2
      SpaceMono-Regular.woff2
      ShareTechMono-Regular.woff2  (legacy, unused)
    images/               — empty, awaiting screenshots
  product_brief.md        — full product spec (reference)
  visual_design_brief.md  — design system spec (reference)
  CLAUDE.md               — this file
  .gitignore
```

---

## Deployment

**Cloudflare Pages via Wrangler.** Git push alone does NOT deploy the site.

After every push, run:
```
npx wrangler pages deploy . --project-name devforge-website
```

The project is `devforge-website` on Cloudflare Pages, serving `usedevforge.com`.

---

## REQUIRED: Use Design Skills (Not Raw Code)

When making visual changes, use the design skill pipeline:

| Skill | When to use |
|---|---|
| `frontend-design` | When writing any HTML/CSS |
| `ui-ux-pro-max` | When making design decisions (layout, spacing, color) |
| `stop-slop` | After writing ANY user-facing text — this is mandatory |
| `accesslint:contrast-checker` | After changing colors — verify WCAG AA |
| `accesslint:refactor` | After structural HTML changes |

**stop-slop is not optional.** Run it on every piece of copy before committing.

---

## Key Principles

- SNES Light theme with muted colors on cream
- Pixel font for UI chrome, Space Mono for content
- Accessibility built in (focus-visible, reduced-motion, contrast)
- Mobile-responsive (single column at 640px breakpoint)
- Fast — no heavy assets, no JS frameworks
- Dense, information-forward (power-user audience)
- **No AI slop** — no generic patterns, no marketing fluff, no forbidden words
- **Forbidden words:** "AI-powered", "AI-driven", "seamlessly", "unleash", "elevate", "empower", "revolutionize", "comprehensive", "robust"
