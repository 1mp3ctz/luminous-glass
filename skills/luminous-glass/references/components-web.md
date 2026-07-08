# Luminous-Glass — Web Component Recipes

Complete HTML/CSS recipes using ONLY `tokens.css` variables. Copy, adapt content, keep the anatomy. All examples assume tokens.css is loaded (+ Google-font import from its header).

## 0. Page atmosphere (always start here — Law 10)

```html
<body class="lg-noir">
<style>
.lg-noir {
  min-height:100vh; color:var(--lg-text-on-dark);
  font-family:var(--lg-font-ui);
  background:
    radial-gradient(1200px 800px at 78% -10%, rgba(200,240,75,.14), transparent 60%),
    radial-gradient(900px 700px at -10% 110%, rgba(31,107,255,.10), transparent 55%),
    var(--lg-black);
}
.lg-light {
  min-height:100vh; color:var(--lg-text-on-light);
  font-family:var(--lg-font-ui);
  background:
    radial-gradient(1000px 700px at 85% -5%, rgba(255,255,255,.8), transparent 60%),
    var(--lg-sage);
}
</style>
```
Swap the glow color for the project accent. Never a flat background.

## 1. Two-tone display headline (Law 5)

```html
<h1 class="lg-display">Hi there, <em>here's</em> <strong>what's happening<br>in your build.</strong></h1>
<style>
.lg-display{
  font-size:var(--lg-fs-display); font-weight:var(--lg-w-reg);
  line-height:var(--lg-leading-display); letter-spacing:var(--lg-track-display);
  color:var(--lg-text-dim-on-dark); max-width:14ch;
}
.lg-display em{ font-style:normal; color:var(--lg-text-dim-on-dark); }
.lg-display strong{ color:var(--lg-text-on-dark); font-weight:var(--lg-w-bold); }
/* on .lg-light: dim = var(--lg-text-dim-on-light); strong = var(--lg-text-on-light) */
</style>
```

## 2. Hero stat (Law 4)

```html
<div class="lg-hero-stat">
  <div class="lg-hero-num">730<span class="lg-unit">pts</span><span class="lg-delta lg-delta--good">+6 pts ↗</span></div>
  <div class="lg-hero-label">Excellent</div>
  <p class="lg-caption">Updated 5 days ago — next update in 2 days.</p>
</div>
<style>
.lg-hero-num{
  font-size:var(--lg-fs-hero); font-weight:var(--lg-w-thin); /* money → var(--lg-w-bold) */
  line-height:.95; letter-spacing:-0.03em; display:flex; align-items:flex-start; gap:12px;
}
.lg-unit{ font-size:.22em; font-weight:var(--lg-w-med); color:var(--lg-caption-on-dark); margin-top:.5em; }
.lg-delta{ font-size:14px; font-weight:var(--lg-w-med); padding:4px 10px; border-radius:var(--lg-r-pill); margin-top:1em; }
.lg-delta--good{ background:color-mix(in srgb, var(--lg-good) 22%, transparent); color:var(--lg-good); }
.lg-delta--bad { background:color-mix(in srgb, var(--lg-bad) 20%, transparent);  color:var(--lg-bad); }
.lg-hero-label{ font-size:18px; color:var(--lg-text-dim-on-dark); margin-top:6px; }
.lg-caption{ font-size:var(--lg-fs-caption); color:var(--lg-caption-on-dark); }
</style>
```

## 3. Glass card (Law 6) — the workhorse

```html
<section class="lg-glass">
  <header class="lg-glass-head">Booking Details</header>
  <div class="lg-row"><span>Marsh Retreat</span></div>
  <div class="lg-row"><span>Total</span><b>€2500</b></div>
  <button class="lg-pill lg-pill--glass">More Details ⌄</button>
</section>
<style>
.lg-glass{
  backdrop-filter:blur(var(--lg-glass-blur)); -webkit-backdrop-filter:blur(var(--lg-glass-blur));
  background:var(--lg-glass-tint); border:1px solid var(--lg-glass-border);
  border-radius:var(--lg-r-card-lg); padding:24px; box-shadow:var(--lg-shadow-float);
}
.lg-glass-head{ font-size:15px; padding-bottom:12px; border-bottom:1px solid var(--lg-glass-hairline); margin-bottom:8px; }
.lg-row{ display:flex; justify-content:space-between; padding:10px 0; font-size:15px; color:var(--lg-text-dim-on-dark); }
.lg-row b{ color:var(--lg-text-on-dark); font-weight:var(--lg-w-med); }
/* dark glass for light-photo grounds: */
.lg-glass--dark{ background:var(--lg-glass-dark); border-color:var(--lg-glass-dark-border); }
</style>
```

## 4. Buttons & pills

```html
<button class="lg-pill lg-pill--solid">Book</button>
<button class="lg-pill lg-pill--accent">Let's go!</button>
<button class="lg-pill lg-pill--glass">Year to date ⌄</button>
<button class="lg-circle" aria-label="next">→</button>
<style>
.lg-pill{
  font:inherit; font-size:15px; font-weight:var(--lg-w-med);
  padding:12px 22px; border-radius:var(--lg-r-pill); border:none; cursor:pointer;
  transition:transform var(--lg-t-fast) var(--lg-ease), box-shadow var(--lg-t-fast) var(--lg-ease);
}
.lg-pill:hover{ transform:translateY(-1px); }
.lg-pill--solid{ background:var(--lg-white); color:var(--lg-text-on-light); }
.lg-pill--accent{ background:var(--lg-lime); color:#101300; box-shadow:var(--lg-shadow-glow-lime); }
.lg-pill--glass{ background:var(--lg-glass-tint); color:var(--lg-text-on-dark);
  border:1px solid var(--lg-glass-border); backdrop-filter:blur(20px); }
.lg-circle{
  width:52px; height:52px; border-radius:50%; border:none; cursor:pointer;
  background:var(--lg-white); color:var(--lg-text-on-light); font-size:20px;
  display:grid; place-items:center;
}
</style>
```

## 5. Bento pair with bridging button (Law 7 — signature)

```html
<div class="lg-bento-pair">
  <div class="lg-card lg-card--accent lg-engrave">
    <div class="lg-card-title">Gross Profit</div>
    <div class="lg-card-value">$177,349.50</div>
    <p class="lg-card-cap">$44,357.23 more than this time last month.</p>
  </div>
  <button class="lg-bridge" aria-label="details">↗</button>
  <div class="lg-card lg-card--black lg-engrave">
    <div class="lg-card-title">Net Profit</div>
    <div class="lg-card-value">$331,224.74</div>
    <p class="lg-card-cap">$44,357.23 more than this time last month.</p>
  </div>
</div>
<style>
.lg-bento-pair{ position:relative; display:grid; gap:10px; max-width:420px; }
.lg-card{ border-radius:var(--lg-r-card); padding:22px; }
.lg-card--accent{ background:var(--lg-acid); color:#141400; }
.lg-card--black{ background:var(--lg-coal); color:var(--lg-text-on-dark); }
.lg-card--white{ background:var(--lg-white); color:var(--lg-text-on-light); }
.lg-card--gray{ background:var(--lg-silver); color:var(--lg-text-on-light); }
.lg-card-title{ font-size:15px; font-weight:var(--lg-w-med); }
.lg-card-value{ font-size:34px; font-weight:var(--lg-w-bold); margin:10px 0 4px; letter-spacing:-0.02em; }
.lg-card-cap{ font-size:13px; opacity:.55; }
.lg-bridge{
  position:absolute; left:50%; top:50%; transform:translate(-50%,-50%);
  width:56px; height:56px; border-radius:50%; border:6px solid var(--lg-black); /* match page bg */
  background:var(--lg-graphite); color:#fff; font-size:18px; cursor:pointer; z-index:2;
}
</style>
```
Bento grids: mix `--accent/--white/--gray/--black` cards in one `grid`; never all one color.

## 6. Stat card (title → value → caption anatomy)

```html
<div class="lg-card lg-card--white lg-stat">
  <div class="lg-stat-head"><span>Shot In</span><span class="lg-arrow">↗</span></div>
  <div class="lg-stat-value">72%</div>
  <div class="lg-card-cap">Increased by 3%</div>
</div>
<style>
.lg-stat-head{ display:flex; justify-content:space-between; font-size:14px; font-weight:var(--lg-w-med); }
.lg-arrow{ opacity:.5 }
.lg-stat-value{ font-size:42px; font-weight:var(--lg-w-bold); letter-spacing:-0.02em; margin:14px 0 2px; }
</style>
```

## 7. Dot-matrix voice (Law 8)

```html
<div class="lg-dot-num">8</div><div class="lg-dot-label">hours</div>
<h3 class="lg-dot-title">NEW PLAN</h3>
<style>
.lg-dot-num{ font-family:var(--lg-font-dot); font-weight:700; font-size:120px; line-height:1; }
.lg-dot-title{ font-family:var(--lg-font-dot); font-size:26px; letter-spacing:.08em; }
.lg-dot-label{ font-size:15px; color:var(--lg-text-dim-on-dark); }
</style>
```

## 8. LED bar-forest + dot-tick ruler (charts, SVG-free)

```html
<div class="lg-forest" style="--n:24">
  <!-- generate N spans; height = value% ; accent the peak(s) -->
  <span style="--h:35%"></span><span style="--h:55%"></span><span style="--h:42%"></span>
  <span class="is-hot" style="--h:88%"></span><span style="--h:60%"></span><!-- ... -->
</div>
<div class="lg-ticks"><span class="on"></span><span class="on"></span><span></span><span></span><span></span></div>
<style>
.lg-forest{ display:flex; align-items:flex-end; gap:4px; height:96px; }
.lg-forest span{ flex:1; height:var(--h); border-radius:2px; background:rgba(255,255,255,.28); }
.lg-forest .is-hot{ background:var(--lg-orange); }
/* light mode: rgba(16,16,19,.22) bars */
.lg-ticks{ display:flex; gap:6px; margin-top:8px; }
.lg-ticks span{ width:5px; height:5px; border-radius:50%; background:rgba(255,255,255,.22); }
.lg-ticks .on{ background:var(--lg-lime); }
</style>
```

## 9. Squiggle line + terminal dot + pill tooltip (SVG)

```html
<div class="lg-squiggle">
  <svg viewBox="0 0 320 120" fill="none">
    <path d="M8 40 C40 20, 60 90, 92 66 S150 20, 176 58 S240 108, 268 84"
          stroke="var(--lg-acid)" stroke-width="3" stroke-linecap="round"/>
    <circle cx="268" cy="84" r="6" fill="var(--lg-acid)"/>
  </svg>
  <div class="lg-tip" style="left:71%; top:52%"><b>$149.31</b><span>Mar 04</span></div>
</div>
<style>
.lg-squiggle{ position:relative; }
.lg-tip{
  position:absolute; transform:translate(-50%,-130%);
  background:var(--lg-graphite); border:1px solid var(--lg-glass-border);
  border-radius:14px; padding:8px 12px; display:grid; line-height:1.2;
}
.lg-tip b{ font-size:14px } .lg-tip span{ font-size:11px; color:var(--lg-caption-on-dark) }
</style>
```

## 10. Radial gauge (ring progress, SVG)

```html
<svg class="lg-gauge" viewBox="0 0 120 120" style="--val:.78">
  <circle cx="60" cy="60" r="50" stroke="rgba(255,255,255,.14)" stroke-width="10" fill="none"/>
  <circle cx="60" cy="60" r="50" stroke="var(--lg-lime)" stroke-width="10" fill="none"
    stroke-linecap="round" stroke-dasharray="314" stroke-dashoffset="calc(314 * (1 - var(--val)))"
    transform="rotate(-90 60 60)"/>
  <text x="60" y="66" text-anchor="middle" fill="currentColor"
        font-family="Outfit" font-size="26" font-weight="600">78%</text>
</svg>
<style>.lg-gauge{ width:120px; height:120px }</style>
```

## 11. Progress bar with hatched track (Law 9)

```html
<div class="lg-progress"><div class="lg-progress-fill" style="width:62%"><span class="lg-knob">⋮</span></div></div>
<style>
.lg-progress{ height:22px; border-radius:var(--lg-r-pill); overflow:visible; position:relative;
  background-image:repeating-linear-gradient(135deg, rgba(255,255,255,.16) 0 4px, transparent 4px 9px); }
.lg-progress-fill{ height:100%; border-radius:var(--lg-r-pill); background:var(--lg-lime); position:relative; }
.lg-knob{ position:absolute; right:-4px; top:50%; transform:translateY(-50%);
  width:30px; height:30px; border-radius:50%; background:var(--lg-lime);
  border:3px solid rgba(0,0,0,.4); display:grid; place-items:center; color:#131300; font-size:12px; }
</style>
```

## 12. Spectrum score bar (scores ONLY)

```html
<div class="lg-spectrum"><span class="lg-spectrum-marker" style="left:82%"></span></div>
<div class="lg-spectrum-scale"><span>300</span><span>630</span><span>690</span><span>720</span></div>
<style>
.lg-spectrum{ height:26px; border-radius:var(--lg-r-pill); background:var(--lg-spectrum); position:relative; }
.lg-spectrum-marker{ position:absolute; top:-7px; width:2px; height:40px; background:currentColor;
  border-radius:2px; }
.lg-spectrum-scale{ display:flex; justify-content:space-between; font-size:11px; opacity:.5; margin-top:6px; }
</style>
```

## 13. Pill tabs with count badge + month chips

```html
<nav class="lg-tabs">
  <button class="lg-tab is-active"><i class="lg-badge">8</i> All notes</button>
  <button class="lg-tab">Important</button><button class="lg-tab">To-do</button>
</nav>
<div class="lg-months">
  <span>may</span><span>jun</span><span>jul</span><span>aug</span><span>sep</span>
  <span class="is-sel">oct</span>
</div>
<style>
.lg-tabs{ display:flex; gap:8px; }
.lg-tab{ font:inherit; font-size:14px; padding:10px 16px; border-radius:var(--lg-r-pill);
  border:none; cursor:pointer; background:var(--lg-glass-tint); color:var(--lg-text-dim-on-dark);
  backdrop-filter:blur(16px); display:flex; align-items:center; gap:8px; }
.lg-tab.is-active{ background:var(--lg-white); color:var(--lg-text-on-light); }
.lg-badge{ font-style:normal; font-size:11px; background:var(--lg-violet); color:#fff;
  width:18px; height:18px; border-radius:50%; display:grid; place-items:center; }
.lg-months{ display:flex; gap:6px; font-size:12px; }
.lg-months span{ padding:8px 12px; border-radius:12px; background:rgba(255,255,255,.07); opacity:.6; }
.lg-months .is-sel{ background:var(--lg-ink); opacity:1; position:relative; }
.lg-months .is-sel::after{ content:""; position:absolute; inset:auto 8px 5px 8px; height:3px;
  border-radius:2px; background:var(--lg-lime); }
</style>
```

## 14. Toggle, list row, hazard bar

```html
<label class="lg-toggle"><input type="checkbox" checked><span></span> On</label>
<div class="lg-listrow"><span class="lg-dotmark" style="background:var(--lg-orange)"></span>
  Shots Per Hour <b>546</b></div>
<div class="lg-hazard"><div class="lg-hazard-head"><span>Uranium Oxide</span><b>71%</b></div>
  <div class="lg-hazard-bar"><i style="width:71%; background:var(--lg-bad)"></i></div></div>
<style>
.lg-toggle{ display:inline-flex; align-items:center; gap:10px; font-size:14px; cursor:pointer; }
.lg-toggle input{ display:none }
.lg-toggle span{ width:52px; height:30px; border-radius:var(--lg-r-pill); background:rgba(255,255,255,.18);
  position:relative; transition:background var(--lg-t-fast); }
.lg-toggle span::after{ content:""; position:absolute; top:3px; left:3px; width:24px; height:24px;
  border-radius:50%; background:#fff; transition:transform var(--lg-t-fast) var(--lg-ease); }
.lg-toggle input:checked + span{ background:var(--lg-lime) }
.lg-toggle input:checked + span::after{ transform:translateX(22px) }
.lg-listrow{ display:flex; align-items:center; gap:10px; padding:12px 0; font-size:14px;
  border-bottom:1px solid var(--lg-glass-hairline); color:var(--lg-text-dim-on-dark); }
.lg-listrow b{ margin-left:auto; color:var(--lg-text-on-dark); font-weight:var(--lg-w-med) }
.lg-dotmark{ width:7px; height:7px; border-radius:50% }
.lg-hazard{ display:grid; gap:6px; font-size:14px }
.lg-hazard-head{ display:flex; justify-content:space-between }
.lg-hazard-bar{ height:4px; border-radius:2px; background:rgba(255,255,255,.14) }
.lg-hazard-bar i{ display:block; height:100% ; border-radius:2px }
</style>
```

## 15. AI surface (Law from RC-surface-03: AI = gradient glow)

```html
<div class="lg-ai">
  <p>Analyze product sales over last year. Compare revenue, quality, sales…</p>
  <button class="lg-circle lg-ai-wand">✦</button>
</div>
<div class="lg-askbar">
  <input placeholder="Ask anything or search" />
  <div class="lg-askchips"><span>Top spend today?</span><span>Any pending issues?</span></div>
</div>
<style>
.lg-ai{ position:relative; border-radius:var(--lg-r-card); padding:18px 64px 18px 18px;
  background:var(--lg-lime); color:#131300; font-size:15px; box-shadow:var(--lg-shadow-glow-lime); }
.lg-ai-wand{ position:absolute; right:10px; top:50%; transform:translateY(-50%);
  background:var(--lg-ink); color:#fff; }
.lg-askbar{ display:grid; gap:10px; }
.lg-askbar input{ font:inherit; font-size:15px; padding:14px 20px; border-radius:var(--lg-r-pill);
  border:1px solid var(--lg-glass-border); background:var(--lg-glass-tint); color:inherit;
  backdrop-filter:blur(20px); outline:none; }
.lg-askchips{ display:flex; gap:8px; flex-wrap:wrap; font-size:12px; }
.lg-askchips span{ padding:7px 12px; border-radius:var(--lg-r-pill);
  background:rgba(255,255,255,.09); border:1px solid var(--lg-glass-hairline); }
</style>
```
AI intro panels: add a green-glow gradient patch (`--lg-glow-green`) behind/inside a white card; bold the data inside the sentence ("boosted your time savings to **48.3 hours**").

## 16. Motion defaults (Law from motion canon)

```css
.lg-reveal{ opacity:0; transform:translateY(14px); filter:blur(var(--lg-focus-blur));
  animation:lgIn var(--lg-t-slow) var(--lg-ease) forwards; }
.lg-reveal:nth-child(2){ animation-delay:120ms } /* stagger one-per-beat */
.lg-reveal:nth-child(3){ animation-delay:240ms }
@keyframes lgIn{ to{ opacity:1; transform:none; filter:blur(0) } }
.lg-pulse::after{ /* sensor/scan ring */
  content:""; position:absolute; inset:-8px; border-radius:inherit;
  border:1px solid currentColor; opacity:.5; animation:lgPulse 2.2s var(--lg-ease) infinite; }
@keyframes lgPulse{ from{ transform:scale(.9); opacity:.5 } to{ transform:scale(1.25); opacity:0 } }
```

## Assembly checklist (per screen)

- [ ] Atmosphere layer present (glow/photo/gradient — never flat)
- [ ] ONE accent family; is it the domain-correct one?
- [ ] A hero moment (giant stat or two-tone display)
- [ ] Glass panels use the exact recipe (blur+tint+border+hairlines)
- [ ] Bento mixes surfaces; radii 20–28; pills round
- [ ] Data-viz uses the house chart anatomy (no library defaults)
- [ ] Captions conversational; deltas as colored chips
- [ ] Motion: staggered blur-reveals, calm easing
- [ ] Squint test vs `../examples/demo.html` + moodboard anchors
