# Style Presets for Ship Page

Curated visual styles for landing pages. Each preset is inspired by real design references — no generic "AI slop" aesthetics.

Every preset includes: CSS variables, font pairing, background treatment, and animation style.

---

## Preset 1: "Mission Control" — Dark Tech

Inspired by: NASA dashboards, IDE themes, sci-fi HUDs.
Best for: Developer tools, AI products, SaaS platforms, open source projects.

```css
:root {
  --font-display: 'Montserrat', sans-serif;
  --font-body: 'Raleway', sans-serif;
  --bg-primary: #1e1a2b;
  --bg-secondary: #2c2440;
  --bg-card: rgba(142, 68, 173, 0.08);
  --text-primary: #f5f6fa;
  --text-secondary: #dcdde1;
  --accent: #8e44ad;
  --accent-light: #bf55ec;
  --accent-hover: #9b59b6;
  --cta-gradient: linear-gradient(135deg, #8e44ad 0%, #bf55ec 100%);
  --border-color: rgba(142, 68, 173, 0.3);
  --shadow-glow: 0 0 30px rgba(142, 68, 173, 0.3);
  --success: #7bed9f;
  --info: #70a1ff;
}
```

**Background treatment**: Subtle grid overlay (1px lines at ~50px intervals, ~0.1 opacity) + floating particle dots (small circles, random positions, slow float animation) + concentric pulse circles (3 rings, border-only, slow scale animation). Creates a "control room" atmosphere.

**Animation style**: Elements enter with `translateY(50px) → 0` + `opacity: 0 → 1`. Stagger delays (0.1s increments). Progress bars animate width. Counters count up. Background particles float continuously.

**CTA buttons**: Glass morphism — `backdrop-filter: blur(5px)`, semi-transparent background, border glow on hover. Hover: slight scale(1.05) + box-shadow glow.

**Section dividers**: Horizontal gradient line (transparent → accent → transparent).

**Font import**: `https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Raleway:wght@300;400;500;600;700&display=swap`

---

## Preset 2: "Clean Slate" — Minimal Light

Inspired by: Linear, Notion, Stripe's whitespace. Japanese design philosophy (ma — negative space).
Best for: Productivity tools, B2B SaaS, professional services, content platforms.

```css
:root {
  --font-display: 'Outfit', sans-serif;
  --font-body: 'Source Sans 3', sans-serif;
  --bg-primary: #fafaf9;
  --bg-secondary: #f5f3f0;
  --bg-card: #ffffff;
  --text-primary: #1a1a1a;
  --text-secondary: #6b6b6b;
  --accent: #2563eb;
  --accent-light: #60a5fa;
  --accent-hover: #1d4ed8;
  --cta-gradient: linear-gradient(135deg, #2563eb 0%, #7c3aed 100%);
  --border-color: #e5e5e5;
  --shadow-soft: 0 1px 3px rgba(0,0,0,0.04), 0 4px 12px rgba(0,0,0,0.04);
  --shadow-hover: 0 4px 20px rgba(0,0,0,0.08);
}
```

**Background treatment**: Almost nothing — that's the point. Pure white/off-white with occasional very subtle dot grid pattern (1px dots at ~24px intervals, ~0.15 opacity). Let content breathe. One or two large, soft radial gradient blobs (very low opacity, like 0.03) for warmth.

**Animation style**: Understated. Elements fade in with very small translateY(15px). No particles, no flashy effects. Hover states are subtle — shadow change, gentle scale(1.02). Micro-interactions on buttons only.

**CTA buttons**: Solid accent color, rounded-lg (8-12px radius). Hover: darken + subtle shadow lift. No gradients unless specifically chosen. White text on colored bg.

**Section dividers**: None — use generous whitespace (120-160px padding) between sections instead.

**Card style**: White bg, subtle border (1px solid var(--border-color)), soft shadow. Hover: shadow deepens slightly.

**Font import**: `https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&family=Source+Sans+3:wght@300;400;500;600;700&display=swap`

---

## Preset 3: "Neon Playground" — Bold Creative

Inspired by: Vercel's dark mode, gaming UIs, synthwave aesthetics, neon signs.
Best for: Creative tools, games, social apps, consumer products, anything that wants to feel exciting.

```css
:root {
  --font-display: 'Space Grotesk', sans-serif;
  --font-body: 'DM Sans', sans-serif;
  --bg-primary: #0a0a0a;
  --bg-secondary: #141414;
  --bg-card: rgba(255, 255, 255, 0.03);
  --text-primary: #ffffff;
  --text-secondary: #a0a0a0;
  --accent: #00ff88;
  --accent-secondary: #ff00aa;
  --accent-hover: #00cc6a;
  --cta-gradient: linear-gradient(135deg, #00ff88 0%, #00cc88 100%);
  --border-color: rgba(255, 255, 255, 0.08);
  --shadow-neon: 0 0 40px rgba(0, 255, 136, 0.15);
  --shadow-neon-hover: 0 0 60px rgba(0, 255, 136, 0.25);
}
```

**Background treatment**: Near-black base. Mesh gradient in hero (2-3 large, very blurred radial gradients at low opacity — one green-ish, one pink-ish, creating depth). Subtle noise texture overlay (CSS: use a tiny repeating SVG or pseudo-element pattern). Optional: thin grid lines for structure.

**Animation style**: Bold entrances — elements can slide in from sides, scale up, or use clip-path reveals. Stagger aggressively (0.15s+). Numbers/counters should have a slight "scramble" effect before landing on final value. Hover states are pronounced — glow effects, color shifts.

**CTA buttons**: Dark button with neon accent text/border. Hover: fills with accent color, text goes dark. Glow effect on hover (box-shadow with accent color). Pill shape (border-radius: 999px).

**Section dividers**: Gradient line (accent → accent-secondary → transparent) or a single decorative SVG wave.

**Special element**: Feature cards have a subtle border gradient (transparent → accent on hover, animated with background-position trick).

**Font import**: `https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=DM+Sans:wght@300;400;500;600;700&display=swap`

---

## Preset 4: "Warm Craft" — Organic & Human

Inspired by: Notion's warmth, indie brand aesthetics, Wes Anderson color palettes, letterpress printing.
Best for: Personal brands, newsletters, community products, lifestyle apps, non-tech audiences.

```css
:root {
  --font-display: 'Fraunces', serif;
  --font-body: 'Nunito', sans-serif;
  --bg-primary: #fef9f3;
  --bg-secondary: #faf0e4;
  --bg-card: #ffffff;
  --text-primary: #2d2418;
  --text-secondary: #7a6f63;
  --accent: #e07b39;
  --accent-light: #f4a261;
  --accent-hover: #c4682f;
  --cta-gradient: linear-gradient(135deg, #e07b39 0%, #e0976b 100%);
  --border-color: #e8ddd0;
  --shadow-warm: 0 2px 12px rgba(45, 36, 24, 0.06);
}
```

**Background treatment**: Warm off-white/cream base. Subtle paper texture (CSS noise or SVG pattern at very low opacity). Can use a hand-drawn-style SVG illustration or doodle as a decorative background element. Avoid anything that looks "tech" — no grids, no particles.

**Animation style**: Gentle and organic. Elements fade in with slight scale(0.98 → 1) rather than translateY. Timing curves should be soft (`cubic-bezier(0.34, 1.56, 0.64, 1)` for a slight bounce). Hover effects are warm — scale, color shift, shadow growth.

**CTA buttons**: Rounded (12-16px radius), solid warm accent. Hover: slight translate-y(-2px) + shadow grow. Can use a slight rotation (1-2deg) for playfulness.

**Section dividers**: Decorative — wavy SVG border, or a hand-drawn-style line, or a small centered ornament/icon.

**Special elements**: Pull quotes with large serif font. Cards with slightly rounded corners (16px) and warm shadows. Optional: subtle CSS illustration elements (circles, squiggles) as decoration.

**Font import**: `https://fonts.googleapis.com/css2?family=Fraunces:wght@300;400;500;600;700&family=Nunito:wght@300;400;500;600;700&display=swap`

---

## Preset 5: "Glass Tower" — Premium Corporate

Inspired by: Apple product pages, Porsche Design, luxury brand websites.
Best for: Enterprise products, premium SaaS, fintech, anything that needs to communicate trust and sophistication.

```css
:root {
  --font-display: 'Sora', sans-serif;
  --font-body: 'Karla', sans-serif;
  --bg-primary: #09090b;
  --bg-secondary: #18181b;
  --bg-card: rgba(255, 255, 255, 0.04);
  --text-primary: #fafafa;
  --text-secondary: #a1a1aa;
  --accent: #e4e4e7;
  --accent-gold: #c9a84c;
  --accent-hover: #ffffff;
  --cta-gradient: linear-gradient(135deg, #e4e4e7 0%, #c9a84c 100%);
  --border-color: rgba(255, 255, 255, 0.06);
  --shadow-premium: 0 8px 32px rgba(0, 0, 0, 0.4);
}
```

**Background treatment**: Deep black/charcoal. Very subtle radial gradient spotlight effect in hero (white/warm, centered, extremely low opacity ~0.03). Optional: a very slow-moving ambient light effect (CSS animation shifting background-position of a radial gradient). No patterns, no particles — pure, clean darkness.

**Animation style**: Cinematic. Elements fade in slowly (0.8-1s duration). Large hero text can use a letter-by-letter reveal or clip-path wipe. Scroll-triggered sections reveal with smooth translateY(40px). Everything feels unhurried and deliberate.

**CTA buttons**: Two styles — primary: white/light text on transparent bg with border, hover fills white with dark text. Secondary: ghost button with subtle border. Both use transition timing that feels "luxury" — slightly slower (0.4s).

**Section dividers**: Thin line (1px, very low opacity white) or no divider — just generous spacing.

**Special elements**: Large, cinematic typography in hero. Numbers/metrics displayed in thin, tall font weight. Cards use glass morphism (blur + transparent bg + subtle border). Can use a gold accent sparingly for highlights.

**Font import**: `https://fonts.googleapis.com/css2?family=Sora:wght@200;300;400;500;600;700&family=Karla:wght@300;400;500;600;700&display=swap`

---

## Preset 6: "Horizon" — Blue Cyber

Inspired by: Tron Legacy interfaces, cyberpunk dashboards, flight sim HUDs.
Best for: Data tools, monitoring dashboards, infrastructure products, API platforms.

Based on a real, tested template — every value below comes from production code.

```css
:root {
  --font-display: 'Rajdhani', sans-serif;
  --font-body: 'Exo 2', sans-serif;
  --bg-primary: #1e272e;
  --bg-secondary: #192a56;
  --bg-card: rgba(0, 168, 255, 0.08);
  --text-primary: #f5f6fa;
  --text-secondary: #dcdde1;
  --accent: #00a8ff;
  --accent-light: #0097e6;
  --accent-hover: #0084c9;
  --cta-gradient: linear-gradient(135deg, #00a8ff 0%, #0097e6 100%);
  --border-color: rgba(0, 168, 255, 0.3);
  --shadow-glow: 0 0 30px rgba(0, 168, 255, 0.25);
}
```

**Background treatment**: Grid overlay (50px intervals, blue-tinted at ~0.1 opacity) + concentric pulse circles (3 rings, border-only, slow scale animation) + horizontal scan lines (gradient lines that drift vertically, 15s loop). Creates a "monitoring dashboard" atmosphere. Particles are small blue dots that blink on/off (3s alternating).

**Animation style**: Elements enter with `translateY(50px) → 0` + `opacity: 0 → 1` with 0.3s staggered delays. h1 has an underline that grows from 0 to 100% width over 1.5s. Charts and images scale from 0.9 → 1.0. Progress bars sweep across.

**CTA buttons**: Semi-transparent blue (`rgba(0, 168, 255, 0.2)`) with blue border, hover fills solid blue. Sharp corners (5px radius) — not pill-shaped. Feels precise and technical.

**Section dividers**: Horizontal gradient line (transparent → blue → transparent), or a thin scanning-line animation.

**Special elements**: Data points that blink randomly. Image containers have a rotating scan overlay (gradient spinning 360deg on 3s loop). Clean uppercase headings with letter-spacing.

**Font import**: `https://fonts.googleapis.com/css2?family=Rajdhani:wght@300;400;500;600;700&family=Exo+2:wght@300;400;500;600;700&display=swap`

---

## Preset 7: "Dual Tone" — Red & Green Contrast

Inspired by: Trading terminal UIs, editorial magazine covers, bold brand identities.
Best for: Fintech, analytics platforms, bold consumer brands, creative agencies, portfolio sites.

Based on a real, tested template — every value below comes from production code.

```css
:root {
  --font-display: 'Clash Display', sans-serif;
  --font-body: 'Satoshi', sans-serif;
  --bg-primary: #121212;
  --bg-secondary: #1a1a1a;
  --bg-card: rgba(255, 255, 255, 0.03);
  --text-primary: rgba(255, 255, 255, 0.87);
  --text-secondary: rgba(255, 255, 255, 0.6);
  --accent: #c83e4d;
  --accent-secondary: #4a9f7b;
  --accent-hover: #a8323f;
  --cta-gradient: linear-gradient(135deg, #c83e4d 0%, #4a9f7b 100%);
  --border-color: rgba(255, 255, 255, 0.1);
  --shadow-glow: 0 0 15px rgba(200, 62, 77, 0.3);
}
```

**Background treatment**: Near-black base (#121212). Subtle grid (40px intervals, white at 0.03 opacity). Particles use a dual-color radial gradient (`radial-gradient(circle, rgba(202, 75, 75, 0.3) 0%, rgba(74, 159, 123, 0.1) 100%)`) — creates a warm, moody atmosphere with two-toned glowing dots.

**Animation style**: Smooth cubic-bezier entrances (`0.16, 1, 0.3, 1`). Elements enter with `translateY(50px) scale(0.95) → translateY(0) scale(1)` — the slight scale adds weight. Stagger delays 0.2s per element. Chart bars use `scaleY(0 → 1)` from bottom with gradient fills (green→red). Timeline items slide in from left with glowing dot markers.

**Key design feature — gradient text**: h1 uses `background: linear-gradient(135deg, var(--accent), var(--accent-secondary))` with `-webkit-background-clip: text` and `color: transparent`. This red→green gradient heading is the signature look.

**CTA buttons**: Pill-shaped (30px radius), glass morphism (`backdrop-filter: blur(5px)`), very subtle border (`rgba(255,255,255,0.1)`). Hover: glow with accent shadow + slight translateY(-2px). Two button variants — red-tinted and green-tinted for primary/secondary.

**Section dividers**: Vertical gradient line for timelines (`linear-gradient(to bottom, var(--accent), var(--accent-secondary))`). Cards have heavy box-shadow (`0 10px 30px rgba(0,0,0,0.5)`) for depth.

**Special elements**: Timeline with vertical gradient line + glowing dot markers. Bar charts with red-to-green gradient fills. Cards use backdrop-filter blur for glass effect. The dual-color system means you always pair red and green — red for emphasis/CTA, green for data/positive indicators.

**Font import**: `https://fonts.googleapis.com/css2?family=Clash+Display:wght@300;400;500;600;700&display=swap` (Note: Clash Display is on fontsource — fallback to `'Sora', sans-serif` if CDN unavailable. Use `https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700&family=Work+Sans:wght@300;400;500;600;700&display=swap`)

---

## Mixing Presets

When user says "Mix elements", combine thoughtfully:
- Typography from one + Colors from another = usually works
- Background treatment from one + Animation style from another = test carefully
- NEVER mix more than 2 presets — it creates visual chaos
- When in doubt, pick the preset closest to the user's vibe and customize from there
