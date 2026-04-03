# Devforge Visual Design Brief

Product: Devforge is a desktop game development environment (Tauri 2 app) that wraps Claude Code in a structured UI for game designers.

## Two Themes

### CRT Dark (default)
Deep navy-black backgrounds (#0a0c10, #0f1318, #151a22) with neon accent colors. Green (#00ff88) is the primary action color. Amber (#ffaa00) for warnings and secondary info. Blue (#44aaff) for implementation. Red (#ff4455) for danger/pitch. Purple (#aa55ff) for QA. Cyan (#00ddff) and teal (#00ccaa) for research/instruct. Borders are subtle dark blue-gray (#2a3a4d). The overall feel is a retro terminal/hacker aesthetic with CRT scanline overlay.

### SNES Light
Cream base (#F2F0E8) with muted, darkened versions of every accent color. Greens (#3D7A3D), ambers (#8A6A28), blues (#4A6A9F), purples (#6B5EAF). Text is dark charcoal (#2D2B3D). Borders are mid-gray (#9A99A0). Feels like a cleaned-up Super Nintendo UI. All colors pass WCAG AA contrast (4.5:1+) on the cream background.

## Typography

- **Press Start 2P** (pixel font, woff2): Used for headers, labels, panel titles, button text, and status indicators. Sizes range from 8px (labels) to 14px (major headers).
- **Share Tech Mono** (monospace): Used for body text, terminal output, form inputs, and longer content. Sizes 11-14px.
- No CDN fonts. Both are bundled as woff2 files.

## Layout

Three-column grid. Left sidebar (projects, modes, settings), center panel (terminal + prompt bar), right sidebar (diff viewer, logs, notes, files). Panels are collapsible. Sidebars are drag-resizable. The grid uses CSS Grid with minmax() tracks.

## Component Patterns

- Buttons use CSS class variants: `.btn-green`, `.btn-cyan`, `.btn-amber`, `.btn-red` with matching border and text color on dark/transparent backgrounds.
- `.btn-panel-micro` is a compact 7px pixel-font button used throughout sidebars.
- Panels have a `.panel-header` (pixel font title + action buttons) and `.panel-body` pattern with consistent 8px padding.
- Modals use a `.modal-overlay` (dark scrim) with a centered `.modal` card. Max-widths vary by content (420px-900px).
- Toggle switches are custom CSS: a 32x16px track with a sliding knob, green glow when active.
- Mode selector is a grid of colored buttons, each with a unique CSS class for its accent color.

## Spacing

4/8/12/16px grid. All gaps, padding, and margins use these increments.

## Iconography

17 custom SVG pixel-art icons (16x16 viewBox, 2px stroke, no fill). All use currentColor so they inherit the theme's text color. Used for panel headers (projects, modes, tasks, diff, log, notes, files, banks, skills, links, scope) and status indicators.

## Accessibility Built In

- `:focus-visible` amber outline (#ffaa00) on all interactive elements
- `prefers-reduced-motion` disables all animations and transitions
- Skip-to-content link
- ARIA labels on all buttons, dialog roles on modals, focus trapping
- 8px minimum font size enforced everywhere
- All status updates use `aria-live="polite"`

## Retro Polish

- Boot animation sequence on launch with pixel sprite character
- Oryx 8-bit sprite system (randomized character, idle/running/success/error animations)
- Sound effects for mode switches, send, success, error (toggleable)
- CRT scanline overlay (toggleable, CSS pseudo-element at low opacity)

## Key Design Principles

- Dark-first, light as alternative
- Pixel font for UI chrome, mono font for content
- Neon-on-dark in CRT, muted-on-cream in SNES
- Dense information display (this is a power-user tool, not a consumer app)
- Every accent color has a specific semantic meaning tied to a mode
