# 🎨 Brand Consistency AI Skill

> Keep every marketing deliverable perfectly on-brand — works with Claude, GPT-4, Gemini, and any LLM.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![LLM Agnostic](https://img.shields.io/badge/LLM-Agnostic-blueviolet)](#use-with-any-llm)
[![Claude Optimized](https://img.shields.io/badge/Claude-Optimized-orange)](https://claude.ai)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## What Is This?

**Brand Consistency AI Skill** is a ready-to-use framework that turns any LLM into a full-stack brand guardian. Feed it your brand config once, and your AI will:

- ✅ Generate copy, presentations, social posts, and reports that are always on-brand
- ✅ Audit existing materials against a 100-point compliance checklist
- ✅ Apply the right specs for every platform (Instagram, WeChat, LinkedIn, print, email, video…)
- ✅ Validate color contrast (WCAG AA) and visual hierarchy automatically
- ✅ Adapt tone of voice across channels — LinkedIn serious, Xiaohongshu warm, X punchy

No design system knowledge required. Drop in your `brand-config.json` and start.

---

## Quick Start (5 minutes)

### 1. Clone this repo

```bash
git clone https://github.com/YOUR_USERNAME/brand-consistency-ai-skill.git
cd brand-consistency-ai-skill
```

### 2. Generate your brand config

```bash
python3 scripts/init_brand_config.py --output my-brand.json --brand "Your Company"
```

Edit `my-brand.json` with your actual colors, fonts, personality traits, and messaging guidelines. See [`references/brand-config-template.md`](references/brand-config-template.md) for field-by-field instructions, and [`assets/brand-config-example.json`](assets/brand-config-example.json) for a real-world example (Anthropic's brand).

### 3. Use with any LLM {#use-with-any-llm}

Paste the following into Claude, GPT-4, Gemini, or any chat interface:

```
I'm attaching my brand-config.json. Please act as my brand consistency assistant.
For all outputs: follow the tone, colors, and typography defined in the config.
If I share a material for review, score it against the review checklist.
```

Attach your `my-brand.json` — you're ready.

> **Optimized for Claude**: The included `SKILL.md` follows Claude's skill format for tighter instruction-following. Works with other models too — just attach `SKILL.md` alongside your config for best results.

---

## What's Inside

```
brand-consistency-ai-skill/
│
├── assets/
│   └── brand-config-example.json     # Full worked example (Anthropic brand)
│
├── references/
│   ├── brand-config-template.md      # Schema docs — how to fill every JSON field
│   ├── visual-identity.md            # Color rules, typography, logo, layout grids
│   ├── tone-of-voice.md              # Writing frameworks for 10+ channels & formats
│   ├── review-checklist.md           # 100-point brand compliance scoring checklist
│   └── deliverable-specs.md          # Exact dimensions for every platform & format
│
├── scripts/
│   ├── init_brand_config.py          # Generate a brand config template
│   ├── validate_brand.py             # Validate config completeness + color contrast
│   └── generate_color_palette.py     # Export a visual HTML/SVG color palette
│
├── SKILL.md                          # Core skill instruction file (used by AI)
└── README.md
```

---

## Key Features

### 🔧 Brand Config JSON
A single structured file that captures everything about your brand: colors, typography, personality traits, messaging, and platform-specific defaults. The AI reads this file to personalize every output to your brand.

### 📐 Platform-Aware Specs
The `deliverable-specs.md` reference covers 50+ deliverable types — from Instagram Reels (1080×1920px) to WeChat Official Account covers (900×383px) to A4 print bleed specs (300 DPI, CMYK). The AI checks the right specs automatically before producing any material.

### 🎯 Tone-of-Voice Engine
The `tone-of-voice.md` framework translates abstract personality traits (Confident, Playful, Trustworthy…) into concrete writing rules by channel. Your LLM adapts the same message for LinkedIn vs. Xiaohongshu vs. email without you having to specify how.

### 📋 100-Point Compliance Audit
Upload any existing material (poster, deck, social image) and the AI scores it across Logo (20pts), Color (20pts), Typography (20pts), Imagery (15pts), Layout (15pts), Copy (10pts). You get a scored report with specific issues and recommended fixes.

### 🛠 CLI Utilities
Three Python scripts for power users:

```bash
# Check color contrast compliance (WCAG AA)
python3 scripts/validate_brand.py --config my-brand.json --check colors

# Validate config completeness
python3 scripts/validate_brand.py --config my-brand.json --check all

# Generate a visual color palette
python3 scripts/generate_color_palette.py --config my-brand.json --output palette.html
```

---

## Example Prompts

Once your LLM has the brand config loaded:

```
Write a LinkedIn post announcing our new product launch.
```
```
Create a 10-slide investor deck outline with brand-compliant slide titles.
```
```
[Attach a poster image] Review this poster for brand compliance and give me a score.
```
```
Write 5 versions of our tagline, each for a different channel: email subject line,
Instagram caption, billboard, WeChat article opener, and pitch deck title slide.
```

---

## Brand Config Structure (overview)

```json
{
  "brand_name": "Acme Corp",
  "brand_identity": {
    "personality_traits": ["Bold", "Approachable", "Innovative"],
    "tagline": "Build What Matters"
  },
  "colors": {
    "primary": [{ "name": "Navy", "hex": "#0A1628" }],
    "accent":  [{ "name": "Electric Blue", "hex": "#0066FF" }]
  },
  "typography": {
    "heading_font": "Inter",
    "body_font": "Georgia"
  },
  "verbal_identity": {
    "tone_descriptors": ["Direct", "Human", "Expert"],
    "words_to_avoid": ["synergy", "leverage", "disrupt"]
  }
}
```

See the full schema in [`references/brand-config-template.md`](references/brand-config-template.md).

---

## Adapting for Your Brand

1. Run `init_brand_config.py` to generate a full template
2. Fill in your brand's actual values (your designer or brand guide is the source of truth)
3. Optionally run `validate_brand.py --check all` to catch missing fields
4. Load into Claude, GPT-4, Gemini, or any LLM — done

The reference documents (`visual-identity.md`, `tone-of-voice.md`, etc.) are universal frameworks — **you never need to edit them**. All personalization lives in your `brand-config.json`.

---

## Requirements

- Python 3.8+ (for CLI scripts only)
- No external dependencies for core scripts
- Access to any LLM — Claude ([claude.ai](https://claude.ai)), GPT-4 ([chatgpt.com](https://chatgpt.com)), Gemini ([gemini.google.com](https://gemini.google.com)), or API

---

## Contributing

Contributions welcome! Ideas that would make great PRs:
- Additional platform specs (Pinterest, Threads, Bluesky…)
- Brand config examples for different industries
- A web UI for generating brand configs
- Integration with Figma Tokens or Style Dictionary

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

MIT — free to use, modify, and distribute. See [LICENSE](LICENSE) for details.

---

## Star History

If this saved you time, a ⭐ helps others find it. Thank you!

---

*Works with any LLM. Optimized for [Claude](https://claude.ai) by Anthropic. Not officially affiliated with Anthropic.*
