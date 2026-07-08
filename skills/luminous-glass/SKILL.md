---
name: luminous-glass
description: Use when building ANY UI or product visual that should carry the luminous-glass genre — dark atmospheric surfaces OR sage/cream light modes, frosted glass over photography, one luminous accent per project, giant hero numerals, dot-matrix data textures, editorial device presentation. Trigger on /luminous-glass, "luminous glass", "make it look premium/atmospheric", or any new frontend/app/marketing-shot that wants this aesthetic. Covers web (tokens+components), SwiftUI, and product presentation shots.
---

# Luminous-Glass

A codified design genre distilled from a broad study of ~180 public design compositions in this "atmospheric glass" aesthetic family. **Genre codification, not replication**: produce NEW work in the family; never copy any specific screen, project, or brand. Abstracted evidence base: `study/corpus.md`.

Refresh ritual: re-study a fresh sample of public work in the genre, diff new observations against `study/corpus.md` CANON, and update tokens/laws that changed.

## The 12 Laws

1. **Two poles, one accent.** Every project owns a noir pole (#0B0B0C-class, never pure black) AND a light pole (sage `#E8EDE4` / cream `#F1EBE2`, never sterile white) — plus exactly ONE saturated accent family constant across both. Ship screens in both modes; mix them inside one layout (light top / dark bottom).
2. **Accent follows domain temperature.** Lime `#C8F04B` = house default (tech/AI/retail/eco). Thermal orange = security/energy/breath. Magenta = intimate/personal. Acid yellow×black = enterprise data. Blue/teal = infra/aero. Full spectrum gradients = scores only.
3. **Color is glow, not wallpaper.** Neutrals stay achromatic; color arrives as radial glows, luminous accents on interactive/emphasis, and tinted near-blacks. Accent pixels are rare and therefore powerful.
4. **The number is the protagonist.** One giant stat per view — thin weight for measures/scores, bold for money; units/deltas small and gray beside it; a conversational gray caption under it ("that's $132,569 more than last month!" — invented copy, not from any source).
5. **Two-tone headlines.** Split display lines by value or weight: dim half + white/bold payoff ("Hi there, *here's* **what's happening in your stores.**"). The payoff word carries the weight.
6. **UI floats as glass over atmosphere.** Photography, gradients, or 3D renders ARE the background; panels are blur(20–40px) + white 8–15% tint + 1px white/22% border + hairline dividers. Dark glass on light photos. Organic glass (petals/blobs) for wellness.
7. **Bento mixes surfaces.** One grid holds accent + white + gray + black cards side by side; color-field cards carry engraved/halftone texture; a circular arrow button may bridge two stacked cards. Radii 20–28px; pills fully round.
8. **Dot-matrix is the data voice.** LED bar-forests, dot-tick rulers, LED-segment bars, dot-grid charts, heatmap chips with LED underlines — and pixel type (Doto) for display numerals and note-title moments.
9. **Charts are expressive but precise.** Squiggle line + terminal dot + pill tooltip; glowing-orb pies with thin leader lines; layered cohort areas; green/red candles; radial gauges; hatched progress tracks. Green=good, red=bad, yellow=attention. No default-library look.
10. **Backgrounds are never dead.** Noir gets a glow or domain tint; light gets sage/latte warmth; announcements go full-bleed gradient with centered display copy.
11. **Presentation is editorial.** Devices on raw-material props (rock, mesh, chrome liquid), art-directed hands, giant type behind devices, monochrome light-bath scenes, case-study slides with underlined quote phrases. Marketing shots are part of the design system, not an afterthought.
12. **Soul: technical data made human.** Dense domains rendered emotional — atmosphere over sterility, calm luxury over clutter. If it feels clinical, add atmosphere; if it feels busy, remove elements, never shrink the hero number.

## Anti-patterns (instant genre-breakers)

Flat #000/#fff backgrounds · multiple accent families per screen · colored cards as default surface · visible heavy borders (separation = surface value + hairlines) · hard drop-shadows/bevels · timid numerals · sharp corners <12px · default-library charts with gridline soup · centered text walls · emoji-as-icons · system-default type.

## Routing table

| Task | Load |
|---|---|
| Any web UI build (app, dashboard, landing) | `references/tokens.css` + `references/components-web.md` |
| Understanding/extending the genre, judging fidelity | `references/design-language.md` |
| Native macOS/iOS (SwiftUI) | `references/swiftui-adapter.md` (+ tokens for values) |
| README hero, App Store shot, product poster, OG image | `references/art-direction.md` |
| Calibration ("does this look right?"), inspiration | `references/moodboard.md` + `examples/demo.html` |
| Rule provenance / refresh | `study/corpus.md` |

## Working method

1. Pick the **domain accent** (Law 2) and declare it in one line before designing.
2. Start from `tokens.css` variables — never invent ad-hoc values; extend tokens if genuinely missing.
3. Build the hero moment first (Law 4/5), then support it; check against anti-patterns before finishing.
4. For each screen ask: *where is the atmosphere?* (Law 6/10) and *what single element is luminous?* (Law 3).
5. Validate with the squint test against `examples/demo.html` and 2–3 `moodboard.md` anchors: same family?
