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

When triggered, follow these 5 steps in order. Each step has a defined output that feeds the next.

### Step 1 — Clarify scope

Confirm the niche keyword. Ask **only the questions you need** to run useful research — never more than 2.

**Required signals before you can research:**

- **Niche keyword** — if vague (e.g. "fashion," "AI tools," "side hustle"), ask the user to narrow it to a specific sub-niche. Don't proceed with a top-level category.
- **Target buyer** — if the niche has multiple plausible audiences, ask. If it has one obvious audience, infer and state your inference ("Assuming you're targeting [X] — let me know if you mean someone different").
- **Platform context** — if relevant to the niche, ask where they'd sell it (Etsy, Fiverr, Gumroad, Shopify, social platform, own site). For niches where platform is obvious (e.g. wedding photography = own site + service platforms), infer.

**Skip clarification if:** the user has already pasted niche-scout output from a prior run, OR the user clearly stated the niche + target + platform in their request.

State your understood scope back to the user in one sentence before running research, so they can correct if you got it wrong.

---

### Step 2 — Research the niche (web search)

Use `web_search` to pull live market data. Run a minimum of **3 distinct searches** before moving to analysis. Search examples (adapt to the specific niche):

- `[niche] best sellers [platform] 2026` — finds current top performers
- `[niche] reviews complaints [platform]` — pulls buyer language and pain points
- `[niche] pricing [platform]` — establishes price ranges
- `[niche] new sellers [platform]` — gauges market entry difficulty
- Niche-specific industry queries (e.g. for "freelance pixel art commissions": `Fiverr pixel art top gigs`, `pixel art commission Twitter 2026`)

**For each search, capture:**
- Top 10-15 sellers / products / shops by name
- Price ranges observed
- Common title patterns, SEO tags, keywords
- 5-10 review snippets (literal phrases, not summaries — these become the Buyer Language Bank later)
- Saturation read: how many sellers/results show up

Do NOT skip web search. Output quality depends entirely on current data. If web search fails or is unavailable, stop and tell the user the skill needs web search to produce useful output.

---

### Step 3 — Pattern analysis

Synthesize what's working in the niche. Identify:

- **Dominant aesthetic / style / approach** — what do the top 5-10 performers visually or structurally have in common?
- **Pricing clusters** — where do most listings sit? Are there 2-3 visible tiers?
- **Buyer language** — what literal phrases do buyers use in reviews? (You'll use these in the Buyer Language Bank section of the output.)
- **Gift / use-occasion framings** — what occasions or use-cases are the top performers leaning on?
- **Common positioning angles** — what story does the niche's leaders tell about themselves?

Output of this step is internal — feeds the next steps. Don't show it to the user yet.

---

### Step 4 — Gap identification

Look explicitly for what's **missing** in the niche. This is where buyer differentiation opportunities live. Identify:

- **Aesthetics or styles underserved** — "every top seller does X, almost none do Y"
- **Sub-niches inside the broader niche** — e.g. "dog mom" market is saturated, but "rescue mom" or "senior dog mom" sub-niches have fewer sellers
- **Empty price tiers** — e.g. "$10-15 saturated, $25-35 sparse, $50+ premium-only"
- **Underserved use-occasions** — e.g. "everyone targets birthday gifts, nobody targets adoption anniversaries"
- **Underserved buyer demographics** — e.g. "this niche assumes mid-20s women — what about Gen X buyers?"

Score the gap clarity: are the gaps obvious and enterable, or marginal? This score feeds the **Differentiation Opportunity** sub-score in Step 5.

---

### Step 5 — Score and output

Now produce the Opportunity Pack (full structure defined in the next section: `## Output: Opportunity Pack`).

**Scorecard scoring rubric:**

- **Demand /25** — based on search volume signals, recent activity, review velocity. 25 = strong stable demand. 10 = niche but real. 0 = no signal.
- **Competition /25** — INVERTED. Higher score = LESS saturated. 25 = wide open. 10 = competitive but enterable. 0 = saturated, race-to-the-bottom pricing.
- **Profit Potential /25** — based on observed price tiers, margin viability for the typical fulfillment model. 25 = healthy margins, multiple viable price tiers. 10 = thin margins, one viable tier. 0 = race-to-bottom pricing dominant.
- **Differentiation Opportunity /25** — based on the gap analysis in Step 4. 25 = multiple clear, enterable gaps. 10 = one viable gap, requires strong positioning. 0 = no clear gaps, market is fully served.

**Total = sum out of 100.**

**Traffic-light verdict:**
- 70-100 → **GREEN** (enter — strong viability)
- 40-69 → **YELLOW** (enter with strong differentiation — pick a clear gap to anchor on)
- 0-39 → **RED** (avoid or pivot to a related sub-niche)

Be honest in scoring. If the niche is saturated, score it accordingly — buyers respect honest reads more than inflated verdicts. RED scores are useful: they save the user from sinking weeks into a doomed niche.

---

After producing the scorecard, render the full Opportunity Pack output as defined in the next section.

## Output: Opportunity Pack

<!-- TODO Day 10: define the structured output sections (TL;DR, scorecard, competitive landscape, design direction, market gaps, pricing recommendation, buyer language bank, note on data depth, next step pointer) -->

## Output format notes

<!-- TODO Day 10: markdown rules, section ordering, length targets -->

## Limitations

<!-- TODO Day 10: web-search snapshot caveat, broad-keyword degradation note -->
