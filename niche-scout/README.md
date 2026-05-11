# niche-scout

A Claude Skill for evaluating a niche before committing to a business build.

Run it on your idea — get back a full opportunity pack: competitive landscape, design patterns, market gaps, pricing analysis, and a go/no-go scorecard.

Works on:
- Identity-based niches (e.g. "dog mom")
- Product-type niches (e.g. "minimalist wall art")
- Service niches (e.g. "freelance pixel art commissions")

[See sample output →](./examples/sample-output-minimalist-desk-plants.md)

---

## What you need to run this

`niche-scout` runs on Claude (by Anthropic). Two install paths:

**1. Claude.ai** — [claude.ai](https://claude.ai) (free or Pro)
Free tier handles light use of this skill. Pro ($20/mo, paid directly to Anthropic, not included) recommended for heavy use or running [The Workshop](https://gumroad.com/caydeai/the-workshop)'s full trio without hitting limits.

**2. Claude Code** — [claude.ai/code](https://claude.ai/code) (CLI)
Same account as Claude.ai. Recommended if you're comfortable with terminal tools.

Both paths use web search natively. Output degrades significantly without it.

> Note: This is similar to how Etsy SEO tools (Sale Samurai, eRank) require an Etsy subscription to function. The skill is the tool; Claude is the engine that runs it.

---

## Install

### Claude.ai (web/desktop)

1. Open a new conversation at [claude.ai](https://claude.ai)
2. [Installation steps TBD — written Day 10 once skill body is complete and install path verified]

### Claude Code

1. From your terminal, navigate to where you keep Claude skills
2. Clone this repo:
```bash
   git clone https://github.com/caydeai/skills.git
```
3. [Activation steps TBD — written Day 10 once skill body is complete]

---

## How to use it

Once installed, just describe what you want in natural language. The skill auto-triggers on phrases like:

- "Scout the [niche] niche for me"
- "Is [niche] worth entering?"
- "Help me research [niche] before I build"
- "What's the competition like for [niche]?"

The skill will ask 1-2 clarifying questions if needed, then produce a full opportunity pack.

---

## What's next

If your niche scores YELLOW or GREEN, the natural next step is [`product-shaper`](https://gumroad.com/caydeai/the-workshop) — part of The Workshop (Module 1 of CaydeOS). It takes the niche output from this skill and helps you define the specific product or service to build.

The Workshop also includes:
- `product-drafter` — turns the product spec into your first working deliverable
- `launch-stack` — turns the deliverable into a launch checklist with platform-specific content
- The full CaydeOS framework
- A live case study (one of my own AI-run stores, updated as it evolves)
- Make.com scenarios for the agent layer
- 60-90 min walkthrough video

Free updates for life to launch-day buyers.

---

## License

MIT — see [LICENSE](../LICENSE) in repo root.

## About

Built by [Cayde](https://tiktok.com/@caydeai) — solo operator running a public 90-day AI agent business build.

Landing page: [caydeai.carrd.co](https://caydeai.carrd.co)
