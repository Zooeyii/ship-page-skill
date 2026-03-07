# 🚀 Ship Page

**Create stunning, interactive landing pages with one prompt. Zero code. Zero dependencies.**

Ship Page is a [Claude Code Skill](https://docs.anthropic.com/en/docs/agents-and-tools/skills) that helps anyone — founders, indie hackers, developers, designers — go from idea to a production-ready landing page in minutes.

No frameworks. No build tools. No npm install. Just one beautiful HTML file you can deploy anywhere.

> **"Your landing page shouldn't be a template. It should be an experience."**

<!-- TODO: Add GIF demo here -->
<!-- ![Ship Page Demo](assets/demo.gif) -->

---

## ✨ What Makes This Different

**Built for Shipping** — This isn't a generic website builder. It's purpose-built for product launches: Product Hunt, GitHub releases, indie hacker ship days.

**Show, Don't Tell** — Can't articulate design preferences? No problem. Ship Page generates 3 visual previews and lets you pick what resonates. No design vocabulary required.

**⚡ Interactive by Default** — Unlike static page builders, every Ship Page comes alive with scroll animations, animated counters, particle effects, and micro-interactions that make visitors *stay*.

**Anti-AI-Slop** — No purple gradients on white. No "Revolutionize Your Workflow" headlines. Five curated presets inspired by real design references, not generic AI aesthetics.

**Zero Dependencies** — A single HTML file will work in 10 years. A React project from 2019? Good luck. Every Ship Page is one self-contained file with inline CSS and JS.

---

## Quick Start

### 1. Install the skill

```bash
# Create the skill directory
mkdir -p ~/.claude/skills/ship-page/references

# Copy the files
cp SKILL.md ~/.claude/skills/ship-page/
cp references/STYLE_PRESETS.md ~/.claude/skills/ship-page/references/
cp references/SECTION_LIBRARY.md ~/.claude/skills/ship-page/references/
```

### 2. Use it

Open Claude Code and just say what you need:

```
> "Create a landing page for my open-source CLI tool called FastBuild"
```

```
> "I'm launching on Product Hunt tomorrow, make me a page for my AI writing app"
```

```
> "Turn this README into an interactive landing page"
```

Claude will interview you about your product, show you style options, and generate a complete, interactive landing page.

### 3. Ship it

The output is a single HTML file. Deploy it anywhere:

```bash
# GitHub Pages — just commit and push
# Netlify / Vercel — drag and drop
# Or just... open it
open my-product-landing.html
```

---

##  Style Presets

Five curated visual directions. Each is a complete design system — not just a color swap.

| Preset | Vibe | Best For |
|--------|------|----------|
| **Mission Control** | Dark, tech, sci-fi HUD | Developer tools, AI products, SaaS |
| **Clean Slate** | Minimal, airy, Linear-esque | Productivity tools, B2B, professional |
| **Neon Playground** | Bold, dark, electric | Games, social apps, consumer products |
| **Warm Craft** | Organic, human, handmade | Personal brands, newsletters, community |
| **Glass Tower** | Premium, cinematic, luxury | Enterprise, fintech, premium SaaS |

<!-- TODO: Add preset preview screenshots -->

---

##  Section Library

Every landing page is assembled from battle-tested sections:

- **Hero** — Above the fold with animated headline, CTAs, and background effects
- **Features Grid** — Responsive cards with hover animations
- **How It Works** — Numbered steps with scroll-triggered reveals
- **Stats & Metrics** — Animated counters that count up on scroll
- **Testimonials** — Social proof cards
- **Pricing** — Tiered pricing with highlighted recommended plan
- **FAQ** — Accordion with smooth expand/collapse
- **CTA Final** — Last push before footer

Each section follows strict density limits to prevent overcrowding. Too much content? Ship Page automatically splits sections.

---

##  How It Works (The Skill)

```
Phase 1: Discovery
   ↓ Claude asks about your product, audience, and content
Phase 2: Style Preview  
   ↓ You pick from 3 generated visual directions
Phase 3: Generation
   ↓ Full landing page with animations and interactions
Phase 4: Iteration
   ↓ Adjust colors, layout, add/remove sections
   → Ship it 🚀
```

This skill uses **progressive disclosure** — the main SKILL.md is a concise ~200-line map, with detailed references loaded only when needed:

```
ship-page/
├── SKILL.md              (~200 lines — the map)
└── references/
    ├── STYLE_PRESETS.md   (loaded during style discovery)
    └── SECTION_LIBRARY.md (loaded during generation)
```

---

##  Philosophy

1. **Ship beats perfect.** A beautiful landing page today is worth more than a perfect one next month.
2. **Dependencies are debt.** A single HTML file will work anywhere, forever. No `node_modules`, no version conflicts, no build failures.
3. **Interactive > Static.** The web is not a PDF. Scroll animations, hover states, and micro-interactions make visitors remember your product.
4. **Generic is forgettable.** Every landing page should feel custom-crafted, not spit out by a template engine.
5. **You don't need to be a designer.** You just need to react to what you see.

---

##  Contributing

Found a bug? Want to add a new style preset? PRs are welcome!

- **New presets**: Add to `references/STYLE_PRESETS.md` following the existing format
- **New sections**: Add to `references/SECTION_LIBRARY.md` with HTML, CSS, and JS patterns
- **Skill improvements**: Edit `SKILL.md` — keep it under 250 lines

---

## License

MIT — do whatever you want with it.
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://docs.anthropic.com)

---

Built with Claude Code. Inspired by the belief that everyone deserves a beautiful launch.
