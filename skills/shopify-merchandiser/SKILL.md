---
name: shopify-merchandiser
description: Writes SEO-optimized Shopify product listings (title, description, tags, pricing notes) from a product idea, supplier link, or existing listing — and can create or update the listing directly in the connected Shopify store. Use when adding a new product, refreshing an underperforming listing, or drafting copy before publishing.
argument-hint: <product idea, supplier URL, or existing product handle/ID>
model: sonnet
allowed-tools:
  - Read
  - Write
  - Edit
  - WebFetch
  - mcp__Shopify__search_products
  - mcp__Shopify__get-product
  - mcp__Shopify__create-product
  - mcp__Shopify__update-product
  - mcp__Shopify__add-to-collection
  - mcp__Shopify__search_collections
---

## Your Task

**Input**: $ARGUMENTS

1. Determine what you're working with:
   - **New product idea** (text description or supplier link) → draft a full listing from scratch
   - **Existing product handle/ID** → call `get-product` first, then refine in place
2. Check for a brand voice reference (see Override Support below)
3. Draft the listing using the structure and rules below
4. Present the draft for approval before writing/publishing anything to the live store
5. Once approved, either:
   - Write the draft to a local file (if the user wants to review/edit further), or
   - Call `create-product` / `update-product` directly (if the user says to publish now)

---

## Override Support

Check for a brand voice file before drafting:

1. Look for `{overrides}/brand-voice.md` in the project (path may vary — ask if unclear, or check for a `CLAUDE.md`/config that defines it)
2. If found: apply its tone, banned words, and formatting rules
3. If not found: use the general best-practices below and ask the user 2-3 quick brand questions (target customer, tone: playful/premium/no-nonsense, any words to avoid) before drafting the first listing of the session

**Override file format** (`{overrides}/brand-voice.md`):
```markdown
# Brand Voice

## Tone
Playful, a little irreverent, never corporate-sounding.

## Target Customer
25-40, impulse buyers, scrolling on mobile.

## Avoid
- "premium", "luxury" (overused in this niche)
- Exclamation-point stacking ("Amazing!!!")

## Always Include
- A one-line "why this beats the alternative" hook near the top
```

---

## Listing Structure

### Title
**Formula**: `[Primary Keyword] + [Key Benefit/Differentiator] + [Modifier]` — keep under 70 characters for SEO.

- Generic: "Phone Case"
- Better: "Shockproof Phone Case with Card Holder"
- Best: "Shockproof Phone Case with Card Holder — Drop-Tested 10ft"

Avoid keyword-stuffing (3+ unrelated keywords crammed in) — it reads as spam and search engines discount it.

### Description
**Structure**: Hook → Benefits (not just features) → Specs → Trust/Urgency close

```
[1-line hook: the problem this solves or feeling it creates]

[2-4 short paragraphs or bullet points: benefits framed as outcomes —
"Keeps your phone safe through drops, splashes, and daily chaos" not
"Made of TPU material"]

Specs:
- [Material/dimensions/compatibility — factual, scannable]
- [Variant info: colors, sizes]

[Closing line: low-friction trust signal — shipping time, return policy,
guarantee — not generic urgency like "Buy now before it's gone!"]
```

**Rules**:
- Lead with the customer's problem/desire, not the product's material specs
- Bullet points for scanability — most shoppers skim on mobile
- One clear call-to-action, not three
- No unverifiable claims ("clinically proven", "#1 bestseller") unless the user supplies the source

### Tags / SEO Keywords
- 5-10 tags: mix of broad category + specific use-case + audience
- Pull from what real buyers search, not internal jargon (check `search_products` or `search_collections` for how similar items in the store are already tagged, for consistency)

### Pricing Notes (not a hard rule — flag, don't decide)
- If the user hasn't set a price, note typical margin ranges for the category if known, but defer the final number to them — pricing involves cost/supplier data this skill doesn't have

---

## Workflow

1. **Gather input** — product idea, supplier link (WebFetch it for specs/images if provided), or existing product via `get-product`
2. **Ask brand-voice questions** if no override file exists and this is the first listing this session
3. **Check for naming/tag consistency** — `search_products` or `search_collections` for similar existing items so the new listing matches store conventions
4. **Draft title + description + tags** per the structure above
5. **Present the draft** — never publish without explicit approval
6. **On approval**:
   - `create-product` for new listings (include collections via `add-to-collection` if the user names one)
   - `update-product` for refreshes of existing listings
7. **Confirm back** with a link/ID to what was created or changed

---

## Quality Checklist

Before presenting a draft, confirm:
- [ ] Title under 70 characters, leads with the real search keyword
- [ ] Description opens with a benefit/hook, not a spec dump
- [ ] No unverifiable or risky claims (medical, "best", guaranteed results) without a source
- [ ] Tags match existing store conventions where applicable
- [ ] Brand voice rules applied (banned words avoided, tone matches)
- [ ] Nothing published to the live store without explicit user approval

---

## Porting This Skill to Another Project

This file is self-contained — to use it in a different repo:
1. Copy `skills/shopify-merchandiser/SKILL.md` into that project's `skills/` directory
2. If that project has a `CLAUDE.md` routing file, add a line like: `**New product / listing copy** → apply shopify-merchandiser`
3. Optionally add `{overrides}/brand-voice.md` there for that store's specific tone
4. The Shopify MCP tools referenced here (`mcp__Shopify__*`) need to be connected in whatever session runs this skill — no other setup required
