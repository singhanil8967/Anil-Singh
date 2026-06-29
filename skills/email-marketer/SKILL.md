---
name: email-marketer
description: Designs and writes email marketing — welcome/onboarding sequences, newsletters, promotional campaigns, and lifecycle flows with subject lines, segmentation, and CTAs. Use for any email campaign, drip sequence, or newsletter.
argument-hint: <campaign type, audience, or offer>
model: sonnet
effort: high
allowed-tools:
  - Read
  - Write
  - Edit
---

# Email Marketer Skill

Write email that gets opened, read, and clicked. This skill produces single sends and multi-step sequences, with the subject line, body, and CTA treated as one system aimed at a single action.

## Your Task

Given a campaign type and audience, produce ready-to-send email copy: subject lines, preview text, body, and CTA — for a one-off send or a full sequence with timing and goals per step.

## Workflow

1. **Pick the email type and goal**:
   - *Welcome/onboarding* — set expectations, deliver quick value, drive first key action.
   - *Newsletter* — recurring value; one primary CTA, not five.
   - *Promotional* — a specific offer with urgency and a deadline.
   - *Lifecycle* — abandoned cart, re-engagement, upgrade, win-back.
2. **Segment** — Who receives this and why? Note the segment and any personalization tokens. Relevance beats volume.
3. **Subject line + preview** — Write 3–5 subject options (≤50 chars, curiosity or benefit, no spam triggers). Preview text extends the subject, never repeats it.
4. **Body** — One idea, one CTA. Open with the reader's context, deliver the value/offer, remove friction, end with a single clear button. Keep it skimmable.
5. **CTA** — Action verb, one primary button. Secondary links are fine but must not compete.
6. **Sequence timing** — For multi-step flows, specify trigger, delay between emails, exit condition (e.g. stop on conversion), and the goal of each step.
7. **Deliverability check** — Avoid spam-trigger phrasing, all-caps, excessive punctuation, and image-only emails. Note a plain-text-friendly version where relevant.

## Output Format

- **Per email**: subject options · preview text · body · primary CTA
- **Sequence**: a table of step · trigger/delay · goal · subject, then the copy for each

## Common Mistakes

- More than one primary CTA per email — split intent halves clicks.
- Subject lines that over-promise relative to the body; opens rise, trust falls, unsubscribes climb.
- Sending to the whole list when a segment would be more relevant.
- Sequences with no exit condition, so converters keep getting "still thinking about it?" emails.
