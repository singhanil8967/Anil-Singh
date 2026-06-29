---
name: landing-page-optimizer
description: Writes and optimizes high-converting landing pages — value proposition, hero copy, page structure, social proof, CTAs, and CRO recommendations. Use when building a landing page or improving an existing page's conversion rate.
argument-hint: <URL, product/offer, or page goal>
model: sonnet
effort: high
allowed-tools:
  - Read
  - Write
  - Edit
  - WebFetch
---

# Landing Page Optimizer Skill

Turn traffic into action. This skill writes new landing pages and diagnoses existing ones for conversion — built around one offer, one audience, and one primary action.

## Your Task

Given an offer (or an existing page URL) and a conversion goal, produce either a full landing-page copy structure or a prioritized CRO audit with specific rewrites. Hold the page to a single conversion goal — competing CTAs are the most common conversion killer.

## Workflow

1. **Lock the one goal** — Define the single action the page exists to drive (sign up, buy, book, download). Everything that doesn't serve it is a candidate for removal.
2. **Nail the value proposition** — One clear statement of *what it is, who it's for, and why it's better*. This is the hero headline. Draft 3 options.
3. **Structure the page** (top to bottom):
   - *Hero* — headline + subhead + primary CTA + supporting visual/proof.
   - *Problem/agitation* — name the pain in the reader's words.
   - *Solution & benefits* — benefits first, features second; tie each feature to an outcome.
   - *Social proof* — testimonials, logos, numbers, case results.
   - *Objection handling* — FAQ, guarantee, risk reversal.
   - *Final CTA* — restate the offer and the single action.
4. **CTA design** — One primary action repeated down the page; action + value verb ("Start my free trial", not "Submit"). Reduce form fields to the minimum.
5. **Message match** — Page promise must match the ad/email/link that sent the visitor. A mismatch spikes bounce.
6. **CRO audit (existing pages)** — Diagnose: unclear value prop, slow load, weak/below-the-fold CTA, too many CTAs, missing proof, friction in the form. Prioritize fixes by likely impact × ease.
7. **Test plan** — Recommend one high-leverage A/B test (usually headline or CTA) at a time.

## Output Format

- **New page**: section-by-section copy with headline options and CTA
- **Audit**: prioritized findings (issue · impact · specific fix) and a single recommended A/B test

## Common Mistakes

- Competing CTAs / navigation that lets visitors wander off the conversion path.
- Feature lists with no benefit translation — readers buy outcomes, not specs.
- Burying the value proposition or the CTA below the fold.
- No social proof or risk reversal near the decision point.
- A/B testing many things at once so no result is attributable.
