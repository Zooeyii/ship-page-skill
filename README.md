# Ship Page

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://docs.anthropic.com)



https://github.com/user-attachments/assets/962d1568-a1ab-44a1-84b9-5fdb38b4df26






A Claude Code Skill that generates interactive, production-ready landing pages from a single prompt. Zero dependencies — one HTML file, deploy anywhere.

For a live demo, check out the [Ship Page landing page](https://zooeyii.github.io/ship-page-skill/) — built with this skill.

https://github.com/user-attachments/assets/1448f163-fb97-4c3e-8e0b-a806c1521929



## Overview

Ship Page brings landing page generation into your terminal. Describe your product, pick a visual style, and get a complete interactive page with scroll animations, animated counters, particle effects, and micro-interactions — all in a single self-contained HTML file.

No frameworks. No build tools. No npm install.

## Features

- **Visual Style Discovery**: Can't describe what you want? Pick from 3 generated visual previews — no design vocabulary required
- **7 Curated Presets**: Complete design systems (not just color swaps) inspired by real design references
- **Interactive by Default**: Scroll-triggered reveals, animated counters, particle backgrounds, hover states
- **README Conversion**: Paste a GitHub README, get an interactive landing page
- **Anti-AI-Slop**: No purple gradients on white, no "Revolutionize Your Workflow" headlines
- **Zero Dependencies**: Single HTML file with inline CSS and JS — works today, works in 10 years
- **Ship-Ready**: Output works immediately on GitHub Pages, Netlify, Vercel, or just `open file.html`

## Installation

```bash
# Clone the repo
git clone https://github.com/Zooeyii/ship-page-skill.git /tmp/ship-page

# Create skill directory and copy files
mkdir -p ~/.claude/skills/ship-page/references
cp /tmp/ship-page/SKILL.md ~/.claude/skills/ship-page/
cp /tmp/ship-page/references/* ~/.claude/skills/ship-page/references/
```

## Usage

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

The output is a single HTML file. Deploy it anywhere:

```bash
# GitHub Pages — just commit and push
# Netlify / Vercel — drag and drop
# Or just open it
open my-product-landing.html
```

## Style Presets

Seven visual directions. Each is a complete design system — typography, colors, animations, background treatments.

| Preset | Vibe | Best For |
|--------|------|----------|
| **Mission Control** | Purple tech, sci-fi HUD | Developer tools, AI products, SaaS |
| **Clean Slate** | Minimal, airy, whitespace | Productivity tools, B2B, professional services |
| **Neon Playground** | Bold, dark, electric green | Games, social apps, consumer products |
| **Warm Craft** | Organic, human, handmade | Personal brands, newsletters, community |
| **Glass Tower** | Premium, cinematic, luxury | Enterprise, fintech, premium SaaS |
| **Horizon** | Blue cyber, dashboard feel | Data tools, APIs, infrastructure |
| **Dual Tone** | Red & green contrast | Fintech, analytics, bold brands |

Three of these presets (Mission Control, Horizon, Dual Tone) are extracted from real, tested production templates.

Don't like any of them? Mix elements from two presets, or describe your own direction.

## Section Library

Every landing page is assembled from battle-tested section templates:

| Section | Description |
|---------|-------------|
| **Hero** | Above the fold — headline, CTAs, background effects |
| **Features Grid** | Responsive cards with hover animations |
| **How It Works** | Numbered steps with scroll-triggered reveals |
| **Stats & Metrics** | Animated counters that count up on scroll |
| **Testimonials** | Social proof cards |
| **Pricing** | Tiered layout with highlighted recommended plan |
| **FAQ** | Accordion with smooth expand/collapse |
| **CTA Final** | Closing call to action before footer |

Each section follows strict density limits to prevent overcrowding. Too much content? Ship Page splits sections automatically.

## How It Works

```
Phase 1: Discovery     →  Claude asks about your product and content
Phase 2: Style Preview  →  You pick from 3 generated visual directions
Phase 3: Generation    →  Full page with animations and interactions
Phase 4: Iteration     →  Adjust colors, layout, sections — then ship
```

The skill uses progressive disclosure. The main instruction file is ~200 lines. Reference files load only when needed:

```
ship-page-skill/
├── SKILL.md                  (the map — always loaded)
├── docs/
│   └── index.html            (live demo page)
└── references/
    ├── STYLE_PRESETS.md      (loaded during style discovery)
    └── SECTION_LIBRARY.md    (loaded during page generation)
```

## Architecture

Ship Page is structured as a standard Claude Code Skill:

- **SKILL.md**: Core instruction file — defines the 4-phase workflow, section density rules, CSS architecture patterns, and anti-AI-slop checklist
- **references/STYLE_PRESETS.md**: 7 curated design systems with CSS variables, font pairings, background treatments, animation styles, and CTA patterns
- **references/SECTION_LIBRARY.md**: Complete HTML/CSS/JS templates for each section type, shared JavaScript patterns (IntersectionObserver, counters, smooth scroll), and a background effects library (particles, grids, gradients, noise)

## Principles

**Ship beats perfect.** A good landing page today beats a perfect one next month.

**Dependencies are debt.** A single HTML file works anywhere, forever. No `node_modules`, no version conflicts, no build failures.

**Interactive > Static.** The web is not print. Motion and interaction make people remember your product.

**Generic is forgettable.** Every page should feel like someone actually designed it.

## Contributing

Contributions are welcome. A few guidelines:

- **New presets**: Add to `references/STYLE_PRESETS.md` following the existing format
- **New sections**: Add to `references/SECTION_LIBRARY.md` with HTML, CSS, and JS patterns
- **Skill changes**: Edit `SKILL.md` — keep it under 250 lines

## License

Ship Page is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Built with [Claude Code](https://docs.anthropic.com).
