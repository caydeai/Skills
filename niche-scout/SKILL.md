---
name: niche-scout
description: Use when the user wants to research a niche before committing to a business build. Produces a full opportunity pack — competitive landscape, design patterns, market gaps, pricing analysis, and a go/no-go scorecard. Works on identity-based niches (e.g. "dog mom"), product-type niches (e.g. "minimalist wall art"), or service niches (e.g. "freelance pixel art commissions"). Uses web search for live market data.
metadata:
  version: 1.0.0
  author: caydeai
  repo: github.com/caydeai/skills
---

# niche-scout

A Claude Skill for evaluating a niche before committing to a business build. Outputs an opportunity pack — competitive landscape, design patterns, gaps, pricing, and a numerical + traffic-light go/no-go verdict.

Tier: research-only. No execution toggle needed.

For deeper research (search volume trends, daily bestseller tracking, automated re-runs) and the production stack (`product-shaper` / `product-drafter` / `launch-stack`), see [The Workshop — Module 1 of CaydeOS](https://gumroad.com/caydeai/the-workshop).

---

## When to use this skill

Auto-triggers when the user wants niche-level research before committing to a build. Natural-language triggers include:

- "Scout the [niche] niche for me"
- "Is [niche] worth entering?"
- "Help me research [niche] before I build"
- "What's the competition like for [niche]?"
- "Run a niche check on [niche]"
- "Is there room in the [niche] market?"
- "Should I start a [niche] business?"

The skill works on three niche types:

- **Identity-based** — "dog mom," "rescue cat owner," "remote worker"
- **Product-type** — "minimalist wall art," "ceramic mugs," "Notion templates"
- **Service** — "wedding photography pricing pages," "freelance pixel art commissions," "podcast editing"

If the user provides a vague keyword like "fashion" or "AI tools," the skill will ask one clarifying question to narrow scope before running the research.

If the user has already run a clarifying question elsewhere (e.g. pasted output from another tool), the skill skips clarification and goes straight to research.

## How it works

<!-- TODO Day 10: write the 5-step workflow (clarify scope → research → pattern analysis → gap identification → output) -->

## Output: Opportunity Pack

<!-- TODO Day 10: define the structured output sections (TL;DR, scorecard, competitive landscape, design direction, market gaps, pricing recommendation, buyer language bank, note on data depth, next step pointer) -->

## Output format notes

<!-- TODO Day 10: markdown rules, section ordering, length targets -->

## Limitations

<!-- TODO Day 10: web-search snapshot caveat, broad-keyword degradation note -->
