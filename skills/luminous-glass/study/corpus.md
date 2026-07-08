# Luminous-Glass Study Corpus

A distillation of a modern "atmospheric glass" UI genre, built from a broad study of ~180 public design compositions in this aesthetic family. This file records the abstracted evidence base behind the genre laws — **rules, not sources**. Nothing here references or reproduces any specific studio, client, project, or account.

Observation axes: palette · typography · surface/material · layout · data-viz · composition · mood · why-it-works
Canon rule: a rule ships only if seen ≥3× across different, unrelated compositions.

## Palette statistics
Method: pixel-frequency extraction across 180 sampled primary compositions (~1.8M px, 17-step buckets).

- **Two-pole neutral system:** dark pole #000000/#111111/#222222/#333333 (≈17.5% of all px) AND light pole #cccccc/#dddddd/#eeeeee/#ffffff (≈19.3%). Both modes are core; dark = dramatic signature, light = silver/cream daylight mode.
- **Neutrals are strictly achromatic (S=0.00).** No tinted-gray volume. Color arrives as GLOW layered over neutral: tinted near-blacks #111122 (blue), #112222 (teal), #221111 (red), #111100 (yellow-black), #223333 — each only 0.4–0.8% but spread over many compositions = the atmospheric-glow signature.
- **Accents are surgical, project-scoped:** largest accent bucket #1166ff (electric blue) = just 0.42% of px; then #33bbff sky, #3377ee blue, #7744ee violet, #aaee66 acid lime, #ee8844/#ee7722 orange, #eebb66 amber. Each accent appears in only 1–2 compositions → one accent family per project, small screen share, high contrast against the neutral field.
- Warm browns (#553322, #886633…) read as photography/skin/wood in covers, not UI chrome.

**RC-palette-01:** two-pole achromatic neutral system (noir + silver/cream).
**RC-palette-02:** color = glow/atmosphere over neutrals, not tinted surfaces.
**RC-palette-03:** one saturated accent family per project; accents are pixels-rare, attention-rich.

## Rule candidates → canon (abstracted)

The following patterns each recurred ≥3× across unrelated compositions and graduated to canon. They are stated as genre rules; no source composition is identified.

- **Color:** two-pole neutral (noir + silver/sage/cream); color as glow/accent only; accent follows domain temperature (lime = default; thermal orange = security/energy/breath; magenta = intimate/personal; acid yellow×black = enterprise data; blue/teal = infra/aero; spectrum gradients for scores only); pastel category-coding for kanban/CRM.
- **Typography:** two-tone display headlines (dim setup + bold payoff); hero numerals (thin for measures/scores, bold for money) with small gray units/deltas and a conversational caption; rounded geometric grotesque as house family; dot-matrix pixel type as data-display and title voice; serif italic reserved for creative/editorial accents.
- **Surface:** UI floats as glass over atmosphere (blur 20–40px, white 8–15% tint, 1px white/20% border, hairline dividers); bento grids mix accent + white + gray + black cards; color-field cards carry engraved/halftone texture; glass goes organic (petals/blobs) in wellness.
- **Data-viz:** the number is the protagonist; dot-matrix/LED is the data-texture language; expressive-but-precise charts (squiggle + tooltip, glowing-orb pies, cohort areas, green/red candles, radial gauges); green/red/yellow status semantics.
- **Composition:** photography (or 3D render) as ground with UI floating over it; presentation modes of in-hand macro, studio-on-raw-props, real-context flat-lay, editorial type poster; giant display type behind devices; art-directed hands; monochrome light-bath scenes in the accent color.
- **Mood:** dense technical data made emotional and human — atmosphere over sterility, calm luxury over clutter.

## Motion
Method: sampled top motion pieces, 4 frames each.

- **RC-motion-01:** slow camera ORBIT around a device staged on a sculptural plinth — presentation beat; translates to subtle parallax/rotate on hover.
- **RC-motion-02:** depth-of-field focus pulls — a grid of widgets blurred, ONE card sharp; focus walks card to card.
- **RC-motion-03:** component close-ups — a single chip/widget oversized and centered on a full-bleed radial-gradient field, one component per beat.
- **RC-motion-04:** glass overlays MOTION-TRACKED to moving human subjects shot with motion blur — the kinetic version of glass-over-photography.
- **RC-motion-05:** storytelling structure: device scenes → case-study slides (quote + Problem/Solution columns) → editorial mixed-type paragraph slides with inline UI-chips and avatar cutouts inside the sentence.
- **RC-motion-06:** dot-matrix sparkle/logo animations (pixel-grid asterisks blinking).
- **CSS translation:** slow transforms (0.6–1.2s ease-out), blur(12px)→blur(0) focus transitions, staggered one-per-beat reveals, scan/pulse ring animations, dot-matrix blink for loaders.

## Hero anatomy (abstracted)

- **Type behavior:** two-tone display is THE headline move — gray-line/white-line stacks, regular-then-bold stacked lines, or inline light+bold; the payoff word carries the weight. Giant numerals: THIN weight for scores/measures, MEDIUM-BOLD for money. Units and deltas ride small and gray beside the numeral; deltas as colored chips with arrows. Captions under values are small, gray, conversational. Font family: rounded geometric grotesque in most modern work; tighter Inter/SF-class in noir fintech; dot-matrix pixel type for note titles/numerals; serif italic only in creative/editorial moments.
- **Card system:** bento mixes surfaces in one grid — accent + white + gray + black cards together. Radii ~20–28px mobile. Cards carry title-regular → value-bold-large → caption-gray-small, left-aligned, generous padding. Color-field cards get engraved textures (concentric circles, halftone dots). A circular arrow button BRIDGES stacked cards half-on-half — signature connector.
- **Glass recipe:** background photo/gradient shows through; panel = blur(20–40px) + white 8–15% tint + 1px white/20% border; text white; secondary text white/60%; hairline dividers white/15%; glass pills for actions; dark glass (black 30–50% + blur) for chips on light photos. Organic glass: petal/blob shapes for wellness.
- **Data-viz anatomy:** LED/dot-matrix everywhere — bar-forest charts (thin 2px bars), dot-tick rulers under charts, LED-segment mini bars, dot-grid charts, heatmap chips with colored LED underline. Charts: bar forests, squiggle lines with terminal dot + pill tooltip, layered area charts with cohort legends, glowing-orb pies with thin leader lines, candle charts green/red, spectrum bars for scores, radial arcs/gauges. Tooltips = glass chips with arrow+text.
- **Component library:** pill buttons (white-on-dark / black-on-light), circular icon buttons, toggles with big knobs, pill-tab filters with count badges, month/date chips (selected = black with accent bar), stat quad cards, avatar chips + clusters, notification dots, search pills, AI ask-bar with suggestion chips, colored agent cards, hazard bars with right-aligned %, calendar glass with accent selected day.
- **Scene/prop craft:** liquid-chrome fabric, perforated metal, black rocks, concrete plinths, color-field backdrops; art-directed hands (gloves for tactical/outdoor, painted for minerals, dark silhouettes for noir contrast).

## CANON
*(genre rules, ≥3 occurrences across different compositions; modern era weighted)*

**Color**
1. Two-pole achromatic neutral system: noir (#0a0a0a–#333) and silver/sage/cream light (#ccc–#fff, often green-tinted #e8ede4 or warm latte) — both first-class; projects ship BOTH modes with one constant accent family.
2. Color arrives as GLOW and accent, never as tinted gray volume: radial glows over neutrals (magenta, green, orange, blue), luminous accents on interactive/emphasis only (pixels-rare, attention-rich).
3. Accent follows domain temperature: LIME/green = the house default (retail, AI, eco, tech); THERMAL ORANGE = security/defense/energy/breath; MAGENTA-PINK = intimate/personal (reminders, hydration, glucose); ACID YELLOW×BLACK = enterprise data; blue/teal = infra/aero; spectrum gradients ONLY for scores.
4. Pastel category-coding (pink/lilac/powder/yellow soft cards) for kanban/CRM organization contexts.

**Typography**
5. Two-tone display headlines: gray+white (or light+bold) split mid-line or per-line; the payoff word gets the weight/value.
6. Hero numerals: thin for measures/scores, bold for money; units/deltas small beside them; delta chips colored w/ arrows; conversational gray captions underneath.
7. Rounded geometric grotesque as house family (free equivalents: Poppins/Outfit/Sora); tighter grotesque (Inter) for noir fintech; DOT-MATRIX pixel type as data-display AND title voice (numerals, note titles, tick charts); serif italic reserved for creative/editorial accents; display statements may end with a period.

**Surface & material**
8. UI floats as GLASS over atmosphere (photo or gradient): blur 20–40px, white 8–15% tint, 1px white/20% border, hairline white/15% dividers; dark-glass chips on light photos; glass goes ORGANIC (petals/blobs) in wellness.
9. Bento grids MIX surfaces in one grid: accent + white + gray + black cards side by side; color-field cards carry engraved/debossed texture (concentric rings, halftone).
10. Backgrounds are never dead: noir gets a subtle glow or tinted near-black; light mode gets sage/latte tint or soft gradient wash; announcement moments go full-bleed gradient with centered display copy.

**Layout & components**
11. Split-screen mobile compositions: light top half + dark bottom half in one screen (or inverse) with the accent bridging both.
12. Signature components: circular arrow button bridging stacked cards; pill buttons + circular icon buttons; pill-tab filters w/ count badges; month chips w/ selected-black+accent-bar; stat cards (title-regular/value-bold/caption-gray); glass tooltip chips w/ arrows; AI ask-bar with suggestion chips; hazard bars w/ right-aligned %.
13. Radii ~20–28px cards, full-round pills/circles; generous padding; baseline-aligned number+caption pairs.

**Data-viz**
14. The number is the protagonist — one giant stat per view; charts support, never dominate.
15. Dot-matrix/LED is the data-texture language: bar-forests, dot-tick rulers, LED segments, dot-grid charts, heatmap chips w/ LED underline.
16. Expressive-but-precise charts: squiggle line w/ terminal dot + pill tooltip; glowing-orb pie w/ thin leader lines; layered cohort areas; green/red candles; spectrum score bars; radial gauges/rings; strand-flows.
17. Status semantics: green good / red bad / yellow attention, often as LED dots or colored deltas.

**Composition & mood (presentation)**
18. Photography (domain or lifestyle) IS the background; UI floats over it — including 3D renders (terrain, offices) and scientific-sublime imagery (thermal bodies, x-ray blur, wireframe terrain).
19. Presentation modes: in-hand macro w/ dramatic light; studio devices on raw-material props (rock, mesh, chrome-liquid, concrete); real-context flat-lay; editorial type posters; giant display type BEHIND devices; monochrome light-bath scenes in the accent color; art-directed hands (gloves, nails, paint).
20. Reel/motion grammar: slow orbits, focus pulls between cards, one-component-per-beat close-ups on gradient fields, glass overlays tracked to moving subjects, case-study slides (quote + Problem/Solution color cards), dot-matrix sparkle loaders. CSS: 0.6–1.2s ease-out, blur-focus transitions, staggered reveals, pulse rings.
21. Soul: dense technical data made EMOTIONAL and human — atmosphere over sterility, calm luxury over clutter.

## Anti-patterns
*(what this genre never does)*
- Flat #000000 or #ffffff backgrounds with no atmosphere/tint/glow.
- More than ONE saturated accent family per screen (multi-color chaos) — except explicit category-coding pastels and score spectrums.
- Tinted-gray surface volume (colored cards as default surface) — color is for emphasis, not wallpaper.
- Dense borders/outlines everywhere; visible 2px+ strokes — separation comes from surface value shifts, blur, and hairlines.
- Skeuomorphic textures, heavy drop-shadows (shadows are soft/large/low-alpha), bevels, glossy 2010s gradients on controls.
- Small timid numerals; centered walls of text; ALL-CAPS body copy.
- Sharp corners (<12px) on cards; mixed radius chaos.
- Charts with heavy gridlines, borders, legends-first design; default-library look.
- Stock-photo cheese (handshakes, pointing-at-screens); UI floating on void white with hard shadows.
- Emoji as UI icons (except deliberate greeting emoji); default blue links; system-default type.
