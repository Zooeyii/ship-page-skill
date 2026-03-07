# Ship Page

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://docs.anthropic.com)

**One prompt. One HTML file. A landing page that actually looks good.**

Ship Page is a [Claude Code Skill](https://docs.anthropic.com/en/docs/agents-and-tools/skills) that generates interactive, production-ready landing pages — no frameworks, no build tools, no npm install. Just a single self-contained HTML file you can deploy anywhere.

> "Your landing page shouldn't be a template. It should be an experience."

<!-- TODO: Replace with actual demo GIF -->
<!-- ![Demo](assets/demo.gif) -->

---

## Why This Exists

Most AI-generated web pages look the same. Purple gradients on white backgrounds. "Revolutionize Your Workflow" headlines. Cards with rounded corners and drop shadows. You've seen it a thousand times.

Ship Page takes a different approach:

**Show, don't tell.** You can't describe what you want, but you know it when you see it. So instead of asking you to pick colors and fonts, Ship Page generates three visual previews and lets you choose.

**Interactive by default.** Landing pages aren't PDFs. Every Ship Page includes scroll-triggered animations, animated counters, particle effects, hover states, and micro-interactions — the kind of details that make visitors actually stay on your page.

**Zero dependencies.** The output is a single HTML file with inline CSS and JS. No node_modules, no build step, no framework lock-in. It works today, and it'll work in 10 years.

---

## Quick Start

### Install

```bash
git clone https://github.com/Zooeyii/ship-page-skill.git /tmp/ship-page

mkdir -p ~/.claude/skills/ship-page/references
cp /tmp/ship-page/SKILL.md ~/.claude/skills/ship-page/
cp /tmp/ship-page/references/* ~/.claude/skills/ship-page/references/
```

### Use

Open Claude Code and describe what you need:

```
> "Create a landing page for my open-source CLI tool called FastBuild"
```

```
> "I'm launching on Product Hunt tomorrow — make me a page for my AI writing app"
```

```
> "Turn this README into an interactive landing page"
```

Claude will ask about your product, show you style options, and generate a complete page.

### Ship

```bash
open my-product-landing.html
```

That's it. Drop the file on GitHub Pages, Netlify, Vercel, or just open it in a browser.

---

## Style Presets

Five visual directions. Each is a complete design system — typography, colors, animations, background treatments — not just a color swap.

| Preset | Vibe | Best For |
|--------|------|----------|
| **Mission Control** | Dark, tech, sci-fi HUD | Developer tools, AI products, SaaS |
| **Clean Slate** | Minimal, airy, lots of whitespace | Productivity tools, B2B, professional services |
| **Neon Playground** | Bold, dark, electric | Games, social apps, consumer products |
| **Warm Craft** | Organic, human, handmade feel | Personal brands, newsletters, community |
| **Glass Tower** | Premium, cinematic, slow animations | Enterprise, fintech, premium SaaS |

Don't like any of them? Mix elements from two presets, or describe your own direction. The presets are starting points, not cages.

---

## What You Get

Every landing page is assembled from a library of battle-tested sections:

**Hero** — Above the fold with headline, CTAs, and background effects. **Features Grid** — Responsive cards with hover animations. **How It Works** — Numbered steps with scroll-triggered reveals. **Stats & Metrics** — Counters that animate on scroll. **Testimonials** — Social proof cards. **Pricing** — Tiered layout with a highlighted plan. **FAQ** — Accordion with smooth expand/collapse. **CTA Final** — Last push before the footer.

Each section has strict density limits. Too much content for one section? Ship Page splits it automatically instead of cramming everything in.

---

## How the Skill Works

```
Phase 1: Discovery    → Claude asks about your product and content
Phase 2: Style Preview → You pick from 3 generated visual directions
Phase 3: Generation   → Full page with animations and interactions
Phase 4: Iteration    → Adjust anything, then ship
```

The skill uses progressive disclosure — the main instruction file is ~200 lines. Reference files (presets, section templates) load only when needed:

```
ship-page/
├── SKILL.md                  (the map — always loaded)
└── references/
    ├── STYLE_PRESETS.md      (loaded during style discovery)
    └── SECTION_LIBRARY.md    (loaded during page generation)
```

---

## Principles

**Ship beats perfect.** A good landing page today is worth more than a perfect one next month.

**Dependencies are debt.** A single HTML file works anywhere, forever. A React project from 2019? Good luck.

**Interactive > Static.** The web is not print. Motion and interaction make people remember your product.

**Generic is forgettable.** Every page should feel like someone actually designed it for this specific product.

---

## Contributing

PRs welcome. A few guidelines:

- **New presets** — Add to `references/STYLE_PRESETS.md`, follow the existing format
- **New sections** — Add to `references/SECTION_LIBRARY.md` with HTML, CSS, and JS
- **Skill changes** — Edit `SKILL.md`, keep it under 250 lines

---

## License

MIT

---

Built with [Claude Code](https://docs.anthropic.com).
