# Luminous-Glass — SwiftUI Adapter

The same system translated for native macOS/iOS apps. Values mirror `tokens.css`; laws mirror `../SKILL.md`.

## Palette

```swift
import SwiftUI

extension Color {
    init(hex: UInt32) {
        self.init(.sRGB,
            red:   Double((hex >> 16) & 0xFF) / 255,
            green: Double((hex >> 8)  & 0xFF) / 255,
            blue:  Double(hex & 0xFF) / 255)
    }
}

enum LG {
    // noir pole
    static let black    = Color(hex: 0x0B0B0C)
    static let ink      = Color(hex: 0x131316)
    static let coal     = Color(hex: 0x1C1C20)
    static let graphite = Color(hex: 0x26262B)
    static let olive    = Color(hex: 0x23271C)
    static let forest   = Color(hex: 0x1B251F)
    static let petrol   = Color(hex: 0x17232B)
    static let navy     = Color(hex: 0x101623)
    // light pole
    static let sage   = Color(hex: 0xE8EDE4)
    static let silver = Color(hex: 0xECECEA)
    static let cream  = Color(hex: 0xF1EBE2)
    static let latte  = Color(hex: 0xE7DDD0)
    // accents (one family per app — Law 2)
    static let lime    = Color(hex: 0xC8F04B)
    static let green   = Color(hex: 0x3ED47E)
    static let acid    = Color(hex: 0xF2EF3F)
    static let orange  = Color(hex: 0xFF7A33)
    static let magenta = Color(hex: 0xF2379B)
    static let blue    = Color(hex: 0x1F6BFF)
    static let teal    = Color(hex: 0x2FD4C8)
    static let violet  = Color(hex: 0x7A4BF0)
    // status
    static let good = Color(hex: 0x3ED47E)
    static let bad  = Color(hex: 0xFF4B4B)
    static let warn = Color(hex: 0xF2C83F)
    // geometry
    static let rChip: CGFloat = 12
    static let rCard: CGFloat = 24
    static let rCardLG: CGFloat = 28
}
```

## Atmosphere (Law 10 — backgrounds never dead)

```swift
struct LGNoirBackground: View {
    var accent: Color = LG.lime
    var body: some View {
        ZStack {
            LG.black
            RadialGradient(colors: [accent.opacity(0.16), .clear],
                           center: .init(x: 0.8, y: -0.1), startRadius: 0, endRadius: 640)
            RadialGradient(colors: [LG.blue.opacity(0.10), .clear],
                           center: .init(x: -0.1, y: 1.1), startRadius: 0, endRadius: 520)
        }
        .ignoresSafeArea()
    }
}
```

## Glass (Law 6) — exact recipe

```swift
struct LGGlass: ViewModifier {
    var radius: CGFloat = LG.rCardLG
    func body(content: Content) -> some View {
        content
            .padding(24)
            .background(.ultraThinMaterial)                       // blur
            .background(Color.white.opacity(0.06))                // tint (total ≈ 8–15%)
            .clipShape(RoundedRectangle(cornerRadius: radius, style: .continuous))
            .overlay(RoundedRectangle(cornerRadius: radius, style: .continuous)
                .strokeBorder(Color.white.opacity(0.22), lineWidth: 1))
            .shadow(color: .black.opacity(0.22), radius: 24, y: 12)
    }
}
extension View { func lgGlass(radius: CGFloat = LG.rCardLG) -> some View { modifier(LGGlass(radius: radius)) } }

// dark glass over light photos:
// .background(.thinMaterial) + .background(LG.black.opacity(0.35)) + white .14 border
```
Hairline dividers inside glass: `Divider().overlay(Color.white.opacity(0.15))`.

## Typography (Laws 4/5/7)

SF Pro (system) plays the tight-grotesque role natively; use `.rounded` design for the house voice. Ship Outfit/Doto as bundled fonts only if brand-critical.

```swift
enum LGType {
    static func heroThin(_ s: CGFloat = 96) -> Font { .system(size: s, weight: .light,  design: .rounded) } // scores/measures
    static func heroMoney(_ s: CGFloat = 72) -> Font { .system(size: s, weight: .bold,  design: .rounded) } // money
    static func display(_ s: CGFloat = 40)  -> Font { .system(size: s, weight: .regular, design: .rounded) }
    static func value(_ s: CGFloat = 30)    -> Font { .system(size: s, weight: .bold,   design: .rounded) }
    static let caption = Font.system(size: 13, weight: .regular)
    static let mono    = Font.system(size: 12, design: .monospaced)   // IDs/specs
}

// Two-tone display (Law 5):
struct TwoTone: View {
    var dim: String; var payoff: String
    var body: some View {
        (Text(dim).foregroundStyle(.white.opacity(0.62))
         + Text(payoff).bold().foregroundStyle(.white))
        .font(LGType.display())
        .lineSpacing(-2)
    }
}

// Hero stat with unit + delta chip (Law 4):
struct LGHeroStat: View {
    var value = "730"; var unit = "pts"; var delta = "+6 pts"; var good = true
    var body: some View {
        HStack(alignment: .top, spacing: 10) {
            Text(value).font(LGType.heroThin())
            VStack(alignment: .leading, spacing: 8) {
                Text(unit).font(.system(size: 15, weight: .medium)).opacity(0.45)
                Text(delta)
                    .font(.system(size: 13, weight: .semibold))
                    .padding(.horizontal, 10).padding(.vertical, 4)
                    .background((good ? LG.good : LG.bad).opacity(0.22), in: Capsule())
                    .foregroundStyle(good ? LG.good : LG.bad)
            }.padding(.top, 18)
        }
    }
}
```
Dot-matrix numerals: bundle "Doto" (`Font.custom("Doto", size: 96)`) or approximate with `.monospaced` + tracking; use sparingly (reminder-class moments).

## Cards & bento (Law 7)

```swift
struct LGCard<Content: View>: View {
    enum Surface { case accent(Color), white, gray, black }
    var surface: Surface; @ViewBuilder var content: Content
    var body: some View {
        VStack(alignment: .leading, spacing: 6) { content }
            .frame(maxWidth: .infinity, alignment: .leading)
            .padding(22)
            .background(bg, in: RoundedRectangle(cornerRadius: LG.rCard, style: .continuous))
            .foregroundStyle(fg)
    }
    private var bg: Color {
        switch surface { case .accent(let c): c; case .white: .white; case .gray: LG.silver; case .black: LG.coal }
    }
    private var fg: Color {
        switch surface { case .accent, .white, .gray: Color(hex: 0x101013); case .black: .white }
    }
}
// Card anatomy: Text(title).font(.system(size:15,weight:.medium))
//               Text(value).font(LGType.value())
//               Text(caption).font(LGType.caption).opacity(0.55)
// Bento: LazyVGrid mixing .accent/.white/.gray/.black — never one surface.
```

## Controls

```swift
// Pill button (accent with glow):
Button("Let's go!") {}
    .font(.system(size: 15, weight: .semibold, design: .rounded))
    .padding(.horizontal, 22).padding(.vertical, 12)
    .background(LG.lime, in: Capsule())
    .foregroundStyle(Color(hex: 0x101300))
    .shadow(color: LG.lime.opacity(0.35), radius: 22)

// Circular icon button:
Button { } label: { Image(systemName: "arrow.right") }
    .frame(width: 52, height: 52)
    .background(.white, in: Circle()).foregroundStyle(.black)

// Ring-progress gauge:
struct LGGauge: View {
    var value: Double; var accent = LG.lime
    var body: some View {
        ZStack {
            Circle().stroke(.white.opacity(0.14), lineWidth: 10)
            Circle().trim(from: 0, to: value)
                .stroke(accent, style: .init(lineWidth: 10, lineCap: .round))
                .rotationEffect(.degrees(-90))
            Text("\(Int(value * 100))%").font(.system(size: 24, weight: .semibold, design: .rounded))
        }.frame(width: 110, height: 110)
    }
}

// LED bar-forest (Law 8):
struct LGForest: View {
    var values: [CGFloat]; var hot: Int?; var accent = LG.orange
    var body: some View {
        HStack(alignment: .bottom, spacing: 4) {
            ForEach(values.indices, id: \.self) { i in
                RoundedRectangle(cornerRadius: 2)
                    .fill(i == hot ? accent : .white.opacity(0.28))
                    .frame(width: 3, height: 90 * values[i])
            }
        }
    }
}
```

## Motion (Law from motion canon)

```swift
extension Animation {
    static let lg = Animation.timingCurve(0.22, 0.8, 0.28, 1, duration: 0.9)   // slow beats
    static let lgFast = Animation.timingCurve(0.22, 0.8, 0.28, 1, duration: 0.24)
}
// Staggered blur-reveal:
// .opacity(shown ? 1 : 0).blur(radius: shown ? 0 : 12).offset(y: shown ? 0 : 14)
// .animation(.lg.delay(Double(index) * 0.12), value: shown)
// Sensor pulse: scale 0.9→1.25 + opacity .5→0, repeatForever, 2.2s.
```

## macOS notes

- Windows: hiddenTitleBar + `LGNoirBackground` behind everything; content bento in a `ScrollView`.
- `NSVisualEffectView`-backed materials (`.ultraThinMaterial`) already match the glass recipe.
- Respect Reduce Transparency: fall back to `LG.coal` solid cards (accessibility > aesthetics).
- Menu-bar/aux apps: one accent, noir base, hero numeral even in small popovers — the genre scales down.
