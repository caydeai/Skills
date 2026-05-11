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

`niche-scout` is a custom Claude Skill. To run it, you need one of:

**1. Claude.ai** — Pro, Max, Team, or Enterprise plan ($20/mo minimum)
[claude.ai](https://claude.ai) — Custom Skills are NOT available on the free tier. Code execution must be enabled in Settings.

**2. Claude Code** — CLI for developers
[claude.ai/code](https://claude.ai/code) — Filesystem-based, most flexible install path.

Both paths use Claude's native web search. Output degrades significantly without it.

> Note: This is similar to how Etsy SEO tools (Sale Samurai, eRank) require an Etsy subscription. The skill is the tool; Claude is the engine that runs it.

---

### Install on Claude.ai

1. Download the `niche-scout/` folder from this repo:
   - Go to [github.com/caydeai/skills](https://github.com/caydeai/skills)
   - Click the green **Code** button → **Download ZIP**
   - Extract the zip. Inside, find the `niche-scout/` folder.
2. Zip just the `niche-scout/` folder (so the zip contains SKILL.md at the top level when extracted).
3. In Claude.ai, go to **Settings → Features**.
4. Make sure **Code execution** is enabled.
5. Find the **Custom Skills** section, click **Upload skill**, select your zip file.
6. The skill is now active in any new Claude conversation. Try saying: "Scout the [your niche] niche for me."

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
