# Luminous-Glass — Design Language

The full codified genre. Every rule cites its evidence base from the genre study (`../study/corpus.md`). "Seen: N" = distinct, unrelated compositions exhibiting the pattern; canon required ≥3.

## 1. Color system

**Two-pole neutral system** *(pixel-stats: dark pole ≈17.5% of all sampled pixels, light pole ≈19.3%; both in top-5 of 55–67 images)*
- Noir pole: `#0B0B0C → #33333A` ramp. Never pure #000 — always lifted, often domain-tinted: olive `#23271C` (enterprise+lime), forest `#1B251F` (sensors/health), petrol `#17232B` (defense), navy `#101623` (fintech).
- Light pole: sage `#E8EDE4` (the modern signature — green-tinted, calm), silver `#ECECEA`, warm cream/latte `#F1EBE2`/`#E7DDD0` for lifestyle/hospitality/personal finance (seen: 6).
- Both poles are first-class. Projects ship both; single screens may split light/dark halves (seen: 7+).

**Accent doctrine** *(stats: largest accent bucket = 0.42% of pixels; each accent in top-5 of only 1–2 images)*
- ONE saturated family per project, constant across light/dark modes. Tiny screen share, placed only on: primary actions, selected states, progress, the one number that matters, alert semantics.
- Domain temperature map (seen across 40+ projects): lime `#C8F04B` house default · thermal orange `#FF7A33` for security/defense/energy/breath · magenta `#F2379B` for intimate/personal · acid `#F2EF3F`×black×white triad for enterprise data tools (seen: 10) · electric blue/teal for infra/aero · green `#3ED47E` for money-good/health metrics.
- Spectrum gradients (red→violet) exclusively for scores (credit 730, seen: 3 in one family + stats) — never decorative.
- Pastel category-coding (pink/lilac/powder/butter soft cards) only in organization UIs — kanban, CRM, calendars (seen: 5).

**Atmosphere** *(seen: 20+ noir, 10+ light)*
- Radial glows over neutrals: magenta reminder glow, green AI glow, orange thermal wash, blue orb. Implemented as `radial-gradient` layers or blurred colored blobs, not tinted surfaces.
- Tinted near-blacks (`#10121D` blue-black, `#1D1112` red-black…) put color INTO noir without painting surfaces.
- Announcement moments: full-bleed soft gradients (peach→lilac→blue) with centered display copy (seen: 3).

## 2. Typography system

**Families** (free equivalents; originals unidentifiable at 1080px and irrelevant — voice matters):
- House: rounded geometric grotesque — **Outfit** (alt Poppins). Friendly, wide apertures, circular bowls.
- Noir fintech: tighter neutral grotesque — **Inter**.
- Dot-matrix voice: **Doto** (alt Handjet) — display numerals, note titles, loader moments (seen: 14+ incl. pixel type as UI type).
- Editorial serif italic: **Instrument Serif** italic — creative-tool headlines, prompt text, one word inside a grotesque line (seen: 3–4; optional tier).
- Mono for IDs/specs: JetBrains Mono (`ID F-2/22.3.2` class captions).

**Display grammar** (seen: 8+ two-tone, 5+ mixed-weight)
- Two-tone: dim `rgba(255,255,255,.62)` (or gray-on-light) for the setup, full white/ink bold for the payoff — split mid-line or by line. "Hello ␣**there!**" / "System **Status**".
- Stacked display lines, tight leading (1.04), tracking −0.02em, sentence case. Display statements may end with a period ("Create.", "Teach." — seen: 4).
- Hero numerals (seen: 25+): thin (300) for measures/scores — `730`, `24L`, `88 SCR`; bold (700) for money — `$331,224.74`. Units/`%`/`L` small (≈0.35em) and gray, sometimes superscript. Deltas as colored chips with arrows (`+6 pts` green / `-81%↓` red).
- Captions: small (13px), gray, CONVERSATIONAL — a human sentence, not a label ("This is $150,000.00 less than last month!").
- Anti: ALL-CAPS body, centered paragraphs, timid same-size numbers.

## 3. Surface & material

**Glass recipe** (seen: 33+; measured across the glass-screen exemplars):
```
background: photo/gradient/render (the atmosphere);
panel: backdrop-filter: blur(20–40px); background: rgba(255,255,255,.08–.15);
border: 1px solid rgba(255,255,255,.22); border-radius: 24–28px;
dividers inside: 1px rgba(255,255,255,.15);
text: white / rgba(255,255,255,.62) secondary;
```
- Dark glass on light photos: `rgba(11,11,12,.40)` + white/14% border (lawn 25mm chip, golf weather).
- Organic glass for wellness: petal/blob/rounded-triangle shapes arranged around a focal glow (seen: 4).
- Glass pills as controls (More Details ⌄, Deposit — €500 ⌄), glass tooltip chips on charts ("↑80% - Almost full").

**Cards & bento** (seen: 10+ mixed-surface grids)
- One grid mixes accent-field, white, gray, and black cards. Solid cards: `#FFFFFF` on light w/ NO border (separation by value against sage bg); `#1C1C20`/`#26262B` on noir.
- Color-field cards carry engraved texture: concentric-ring deboss (lime Gross Profit) or halftone dot patches (yellow Orders) — see `.lg-engrave`/`.lg-dotgrid` in tokens.
- Hatched/striped textures on progress tracks and status patches (seen: 3+).
- The bridging circular button: a round arrow button seated half-on-half between two stacked cards (lime→black) — signature connector (seen: 3).

## 4. Layout grammar

- Generous padding (20–28px card interiors), 12–16px gaps; baseline-aligned number+caption pairs.
- Split-mode screens: light hero top / dark utility bottom (retail home, seen: 3+).
- Month/date chip rows: neutral chips, selected = black chip w/ accent bar or dot.
- Pill-tab filters with count badges ("8 All notes" w/ colored dot badge).
- Bottom bars: floating black pills with overlapping circular icons + one accent FAB.
- Desktop dashboards: 12-col bento, glass side panels, giant faint display type may sit BEHIND the UI (seen: 7).
- Density is LOW; if crowded, remove modules — never shrink the hero stat.

## 5. Data-viz language

- Dot-matrix/LED family (seen: 14+): bar-forest (2px thin bars), dot-tick rulers under charts, LED-segment inline bars, dot-grid area charts, heatmap chips (tinted surface + colored LED underline per cell).
- Line charts: relaxed squiggle w/ terminal dot + dark pill tooltip showing value+date (seen: 3+).
- Pies: glowing blurred orbs (blue/violet/green) with thin white leader lines to labels (seen: 2 + donuts 6+).
- Areas: layered translucent cohorts w/ dot legend (Age 32/42/52/62).
- Candles/deltas: green/red duotone (seen: 3).
- Gauges: radial arcs w/ needle or ring-progress; ring-progress ON buttons (circular CTA with progress rim).
- Hazard bars: label left, % right, thin colored bar under (cream/red by severity).
- Axis/grid: dashed hairlines only, tiny gray labels, no boxed legends.

## 6. Composition & presentation (the "shot" language)

- Photography as ground (seen: 30+): domain photos (grass, course, patient, cargo) or lifestyle blur; UI floats as glass. Scientific-sublime variants: thermal bodies, x-ray blur, wireframe terrain (seen: 4).
- 3D renders as environments: terrain, isometric offices, satellites, product renders IN cards (seen: 4+).
- Device staging: raw-material props — black rock, perforated metal, concrete, liquid-chrome fabric (seen: 13); dramatic single-source light; monochrome light-bath scenes in accent color (seen: 4).
- Hands are art-directed props: black gloves (tactical/outdoor), red nails, dark silhouettes, paint matched to content (seen: 15+).
- Giant display type behind/around devices (a lowercase wordmark or product name set huge and faint) (seen: 7).
- Case-study slides: white client quote on black w/ underlined key phrases; Problem (accent card) / Solution (pastel card) pairs; gradient-metallic project wordmarks (seen: 4+).

## 7. Motion vocabulary (from motion studies)

- Camera orbits around staged devices (0.6–1.2s beats) → web: subtle parallax/rotate on scroll or hover.
- Focus pulls: blurred widget grid, one card sharp; walk focus card-to-card → `filter: blur(12px)→0` transitions.
- One-component-per-beat close-ups on full-bleed gradient fields → staggered reveals, generous timing.
- Glass overlays tracked to moving subjects (motion-blur photography) → position: sticky/transform-follow patterns.
- Dot-matrix sparkle loaders; scan/pulse rings on sensors.
- Easing `cubic-bezier(.22,.8,.28,1)`; nothing snappy-bouncy; calm luxury.

## 8. Voice & soul

- Verticals where the genre shines: health-tech, fintech, logistics, AI tools, sports analytics, energy, defense-ops, IoT.
- Copy: short, human, benefit-first; greetings with names; conversational captions on data; statements end with periods.
- The thesis: make dense technical data feel less clinical and more human — every design decision serves emotional clarity: one hero fact, atmospheric ground, calm glass, a single luminous accent.
