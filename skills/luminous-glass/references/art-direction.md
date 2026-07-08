# Luminous-Glass — Art Direction (Presentation Shots)

How to make YOUR app's hero images, README banners, App Store shots, and OG images carry the genre's presentation grammar. Codified from 30+ observed staging setups. $0 pipeline: HTML/CSS posters rendered via headless Chrome screenshot (`--screenshot --window-size=…`) or any browser at exact viewport — no image-gen APIs.

## The five staging modes (pick ONE per shot)

1. **Noir plinth** — device/screenshot on a dark sculptural scene; one glow in the project accent; giant faint type behind. (Most versatile; template A.)
2. **Color-field poster** — flat acid/accent background, screenshot tilted or straight, giant display type, texture patches (halftone/hatch). (Enterprise/data apps; template B.)
3. **Photo-immersive** — full-bleed domain photograph; ONE glass card floating (the retreat-booking pattern). Requires a good photo; UI must be minimal.
4. **Light-bath macro** — extreme close-up of one component, entire frame washed in one accent (monochrome scene). For feature announcements.
5. **Case-study slide** — black; white client-style quote with underlined key phrases; Problem (accent card) / Solution (pastel card) pair. For READMEs' "why" sections.

## Composition rules (apply to every shot)

- One light source; soft large shadows (`0 24px 60px rgba(0,0,0,.35)`), never hard drop-shadows.
- Device/screenshot tilted 4–10° OR perfectly straight — nothing in between.
- Type behind device: display font at 20–35vw, `opacity .06–.12`, may bleed off-canvas; device overlaps letters.
- Giant type ends with a period when it's a statement ("Build.", "Ship.").
- The accent appears exactly 2–3 times: glow, one UI element, maybe a chip.
- Margins are generous; never fill corners; watermark/logo small in a corner (like their "R").
- Text on shots: two-tone rule applies (dim setup + bold payoff).

## Template A — README/OG hero (1280×640), noir plinth

Self-contained; replace `{{...}}`; screenshot at exactly 1280×640.

```html
<!doctype html><meta charset="utf-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;700&display=swap');
  *{margin:0;box-sizing:border-box}
  body{width:1280px;height:640px;overflow:hidden;font-family:Outfit,sans-serif;color:#fff;
    background:
      radial-gradient(700px 480px at 82% -8%, rgba(200,240,75,.16), transparent 60%),
      radial-gradient(600px 420px at -6% 108%, rgba(31,107,255,.10), transparent 55%),
      #0B0B0C; position:relative}
  .behind{position:absolute; left:-30px; bottom:-70px; font-size:300px; font-weight:700;
    letter-spacing:-.04em; color:rgba(255,255,255,.07); user-select:none}
  .copy{position:absolute; left:72px; top:96px; max-width:420px}
  .copy h1{font-size:56px; line-height:1.04; letter-spacing:-.02em; font-weight:400;
    color:rgba(255,255,255,.62)}
  .copy h1 b{color:#fff; font-weight:700}
  .copy p{margin-top:18px; font-size:16px; color:rgba(255,255,255,.45)}
  .chip{display:inline-block; margin-top:26px; padding:10px 18px; border-radius:999px;
    background:#C8F04B; color:#131300; font-weight:600; font-size:14px;
    box-shadow:0 0 44px rgba(200,240,75,.35)}
  .shot{position:absolute; right:64px; top:70px; width:560px; border-radius:26px;
    transform:rotate(6deg);
    box-shadow:0 40px 90px rgba(0,0,0,.5); border:1px solid rgba(255,255,255,.16)}
</style>
<div class="behind">{{BigWord}}</div>
<div class="copy">
  <h1>{{Dim setup,}} <b>{{bold payoff.}}</b></h1>
  <p>{{One human sentence about what it does.}}</p>
  <span class="chip">{{v1.0 — ships today}}</span>
</div>
<img class="shot" src="{{app-screenshot.png}}" alt="">
```

## Template B — color-field poster (1200×1500, IG/product-page ratio)

```html
<!doctype html><meta charset="utf-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;700&display=swap');
  *{margin:0;box-sizing:border-box}
  body{width:1200px;height:1500px;overflow:hidden;font-family:Outfit,sans-serif;
    background:#F2EF3F; position:relative}   /* swap to project accent field */
  .tex{position:absolute; right:0; top:0; width:44%; height:30%;
    background-image:radial-gradient(rgba(0,0,0,.18) 1.6px, transparent 1.6px);
    background-size:9px 9px; border-radius:0 0 0 48px}
  h1{position:absolute; left:70px; top:64px; font-size:112px; line-height:.98;
    letter-spacing:-.03em; color:#111; font-weight:700; max-width:9ch}
  h1 span{color:rgba(17,17,17,.45)}
  .shot{position:absolute; left:50%; bottom:-40px; transform:translateX(-50%) rotate(-5deg);
    width:78%; border-radius:34px; box-shadow:0 60px 120px rgba(0,0,0,.35)}
  .foot{position:absolute; left:70px; bottom:56px; font-size:20px; color:#111;
    display:flex; gap:14px; align-items:center}
  .foot .dot{width:10px;height:10px;border-radius:50%;background:#111}
</style>
<div class="tex"></div>
<h1>{{Product}} <span>{{one-line genre statement.}}</span></h1>
<img class="shot" src="{{screenshot.png}}" alt="">
<div class="foot"><span class="dot"></span> {{yourname}} · {{year}}</div>
```

## Screenshot prep (feeding the templates)

- Capture the app in its best mode (usually noir) at 2× scale; crop to the hero moment — one giant stat visible.
- Round the screenshot corners IN the template (26–34px), add the 1px white/16% border — matches device-frame feel without fake bezels.
- If framing a phone: use simple CSS phone frame (rounded-rect 60px radius + notch pill), never skeuomorphic mockup PNGs from stock.

## App Store / marketing sequence (the carousel grammar)

Observed post → carousel structure, reusable for App Store screenshots:
1. Hero shot (staging mode 1/2/3) with two-tone claim.
2. Full clean screen (light mode).
3. Full clean screen (dark mode) — same accent visible in both.
4. Component close-up on gradient field (one feature, oversized).
5. Case-study/Problem–Solution slide OR brand slide (logo + wordmark on accent tile).

## Checklist per shot

- [ ] One staging mode, one accent, 2–3 accent occurrences
- [ ] Two-tone or period-statement typography
- [ ] Soft shadows only; tilt 4–10° or 0°
- [ ] Generous margins; small corner mark
- [ ] Would it sit naturally inside their feed? (squint vs moodboard)
