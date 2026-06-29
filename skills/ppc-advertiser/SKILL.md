---
name: ppc-advertiser
description: Plans paid advertising campaigns and writes ad copy for Google Ads and Meta/social — campaign structure, audience targeting, headlines/descriptions, and budget/bidding guidance. Use for paid search, paid social, or display advertising.
argument-hint: <product/offer, platform, or campaign goal>
model: sonnet
effort: high
allowed-tools:
  - Read
  - Write
  - Edit
  - WebSearch
---

# PPC Advertiser Skill

Plan paid campaigns and write the ads that run in them. This skill covers campaign architecture, targeting, and platform-correct ad copy for search and paid social — built around a single conversion goal and a measurable cost target.

## Your Task

Given a product/offer, platform, and goal, produce a campaign structure (campaigns → ad groups/sets → ads), audience/keyword targeting, and ready-to-load ad copy that respects each platform's character limits and policies.

## Workflow

1. **Define the goal and economics** — What's the conversion (lead, sale, install) and the target CPA/ROAS? Ask if not given; copy and structure both flow from this.
2. **Choose platform and match type**:
   - *Google Search* — keyword-driven; group tightly by intent; specify match types (broad/phrase/exact) and negatives.
   - *Meta/paid social* — audience-driven; specify interest/lookalike/retargeting audiences and the creative angle.
3. **Campaign structure** — One goal per campaign; ad groups/sets organized by theme or audience so copy stays relevant to the targeting. Tight structure = higher relevance/Quality Score = lower cost.
4. **Write the ads** — Respect limits:
   - *Google RSA*: headlines ≤30 chars (write 8–10), descriptions ≤90 chars (write 3–4), pin only when necessary.
   - *Meta*: primary text, headline, description; hook in the first line above the fold.
   Lead with the benefit, include the keyword/offer, end with a clear CTA, and mirror the landing page's promise (message match).
5. **Targeting + negatives** — List keywords or audiences, plus negative keywords/exclusions to cut wasted spend.
6. **Budget & bidding** — Recommend a starting daily budget, bid strategy, and a testing plan (2–3 ad variants per group for rotation).
7. **Measurement** — Define the conversion action and UTM tagging so results are attributable.

## Output Format

- **Campaign map**: campaign → ad group/set → theme/audience
- **Ad copy**: per ad, all headlines/descriptions within limits, with CTA
- **Targeting**: keywords + match types (or audiences) and negatives/exclusions
- **Budget & bidding** recommendation and a test plan

## Common Mistakes

- Single ad group stuffed with unrelated keywords — tanks relevance and raises cost.
- Ad copy whose promise doesn't match the landing page (message-match break) — wastes clicks.
- No negative keywords / no audience exclusions — budget leaks to irrelevant traffic.
- Launching without conversion tracking; without it you're optimizing blind.
- Ignoring character limits or platform ad policy (claims, restricted categories).
