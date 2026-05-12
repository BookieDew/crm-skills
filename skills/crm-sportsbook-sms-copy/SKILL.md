---
name: crm-sportsbook-sms-copy
description: Creates concise, compliant sportsbook SMS variants with character count, copy angle, segment fit, offer clarity check, CTA clarity check, T&C handling note, RG/compliance notes, commercial notes, recommended variant, and A/B test suggestion.
---

# CRM Sportsbook SMS Copy

## Purpose

Create SMS variants for sportsbook CRM campaigns that are short, clear, compliant, commercially controlled, and appropriate for `[TARGET_SEGMENT]`, `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, `[BRAND_TONE]`, `[T&CS]`, and `[REGULATORY_NOTES]`.

## Role in the Skill Pack

This is the first fully developed channel-specific copy skill. It uses campaign brief, offer mechanics, market context, localisation, and shared principles to produce SMS-only copy and review notes.

## When to Use

- The target channel is SMS.
- A CRM manager needs SMS copy variants.
- A campaign brief needs concise customer-facing text.
- Existing SMS needs improvement for clarity, RG safety, or offer explanation.
- An A/B test needs SMS variant logic.

## When Not to Use

- Do not write email copy; email should be a future channel-specific skill.
- Do not write push copy; push should be a future channel-specific skill.
- Do not design the full offer mechanic; use `crm-sportsbook-offer-mechanics`.
- Do not finalise compliance sign-off; use `crm-sportsbook-rg-compliance-review`.
- Do not invent `[T&CS]`, local regulation, current fixtures, or market facts.

## Required Inputs

### Minimum required inputs

- `[TARGET_CHANNEL]` must be SMS.
- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[TARGET_SEGMENT]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- CTA destination or CTA action.
- `[T&CS]` or clear note that T&Cs are missing.

### Recommended inputs

- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- Character-limit preference.
- Sender or brand naming rule.
- Expiry.
- Eligible markets.
- Minimum odds, minimum stake, and max bonus value where relevant.

### Advanced optional inputs

- Segment-specific motivations.
- Previous SMS performance.
- Opt-out wording requirement supplied at runtime.
- Local style guide supplied at runtime.
- Approved and prohibited words.
- A/B test hypothesis.
- Journey step number.

## Output

This skill produces SMS variants with character count, copy angle, segment fit, offer clarity check, CTA clarity check, T&C handling note, RG/compliance notes, commercial notes, recommended variant, and A/B test suggestion.

## Workflow

1. Load `crm-sportsbook-shared-principles`, campaign brief, offer mechanics, and market context where available.
2. Confirm `[TARGET_CHANNEL]` is SMS. If not, route to future channel-specific skill guidance rather than writing non-SMS copy.
3. Confirm `[TARGET_LANGUAGE]`, `[BRAND_TONE]`, `[T&CS]`, CTA, and offer constraints.
4. Identify the simplest SMS-friendly copy angle.
5. Draft 3 to 5 variants with one offer, one CTA, and clear T&C reference.
6. Count characters for each variant, including spaces and visible T&C reference.
7. Check offer clarity: can the customer understand value and action in one sentence?
8. Check CTA clarity: is the next action obvious?
9. Check RG/compliance: no chasing, no pressure, no certainty, no misleading claims.
10. Check commercial exposure: no open-ended value, no unapproved claims, no missing material constraint.
11. Recommend the best variant and one A/B alternative.

## Decision Logic

- If `[T&CS]` are missing, include a placeholder T&C reference and mark final copy `[NEEDS CONFIRMATION]`.
- If the mechanic is complex, simplify or recommend a different mechanic for SMS.
- If expiry is included, avoid aggressive urgency.
- If `[OFFER_VALUE]` is unclear, do not write final customer-facing value.
- If the segment is reactivation, avoid manipulative win-back language.
- If the segment is VIP, keep tone respectful and avoid exaggerated exclusivity unless confirmed.
- If copy refers to sport preference or event interest, require confirmed data.
- If local opt-out wording is required but missing, mark `[NEEDS CONFIRMATION]`.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-offer-mechanics`, optionally `crm-sportsbook-localisation`.
- Skills that should normally run after this one: `crm-sportsbook-localisation` if not already run, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, offer safety, SMS communication principles, and measurement principles.

## Sportsbook-Specific Considerations

Consider sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market, language, local style, fixture, league, local sport preference, local operator, local regulation, payment method, or geo-specific behaviour.

If market-specific knowledge is needed, ask for it, label it `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

This skill is SMS-only.

For SMS:

- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.
- Prefer one event hook or one value hook, not both if it makes the message dense.
- Do not bury material terms.
- Use plain customer language instead of internal CRM terminology.

Email and push should be acknowledged as future channel-specific skills and must not be blended into this SMS skill.

## Responsible Gaming & Compliance Guardrails

Apply baseline responsible-gaming rules even if the user says the market has no strict rules. SMS must avoid:

- Targeting self-excluded users.
- Targeting users with responsible-gaming risk flags.
- Encouraging chasing losses.
- Referring to previous losses as a reason to bet again.
- Saying or implying betting solves financial problems.
- Guaranteed-win language.
- Misleading risk-free claims unless approved.
- Aggressive urgency.
- Hidden or unclear T&Cs.
- Emotional pressure.
- Offers based on recent heavy losses.
- Manipulative win-back language.

## Commercial Guardrails

Protect margin and bonus cost in the wording:

- State `[OFFER_VALUE]` only when approved.
- Avoid implying unlimited value.
- Reference `[T&CS]` clearly.
- Avoid rich offer language for already active users unless justified.
- Use minimum odds, minimum stake, max bonus value, eligible markets, and expiry where relevant.
- Make sure the copy fits activation, retention, reactivation, event activation, cross-sell, or VIP engagement.

## Brand & UX Guardrails

SMS must be direct, understandable, and low-friction. Avoid jargon, misleading terms, fake personalisation, stereotypes, over-familiarity, and implication of certainty of winning. Make the next action obvious.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## SMS Copy Set

### Inputs
- [CONFIRMED] Market: [TARGET_MARKET]
- [CONFIRMED] Language: [TARGET_LANGUAGE]
- [CONFIRMED] Segment: [TARGET_SEGMENT]
- [CONFIRMED] Offer: [OFFER_MECHANIC] / [OFFER_VALUE]
- [CONFIRMED] T&Cs: [T&CS]

### Variants
| Variant | SMS copy | Character count | Copy angle | Segment fit | Offer clarity | CTA clarity | T&C handling | RG/compliance notes | Commercial notes |
|---|---|---:|---|---|---|---|---|---|---|
| A |  |  |  |  | Pass/Revise | Pass/Revise |  |  |  |
| B |  |  |  |  | Pass/Revise | Pass/Revise |  |  |  |

### Recommended Variant
- [RECOMMENDATION]

### A/B Test Suggestion
- Hypothesis:
- Variant logic:
- Primary KPI:
- Risk control:

### Open Items
- [NEEDS CONFIRMATION]
```

## Example User Request

Write SMS variants in `[TARGET_LANGUAGE]` for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` promoting `[OFFER_MECHANIC]` worth `[OFFER_VALUE]` on `[TARGET_EVENT]`. Use `[BRAND_TONE]`. Include `[T&CS]`.

## Example Output

```markdown
## SMS Copy Set

| Variant | SMS copy | Character count | Copy angle | Segment fit | Offer clarity | CTA clarity | T&C handling | RG/compliance notes | Commercial notes |
|---|---|---:|---|---|---|---|---|---|---|
| A | `[OFFER_VALUE]` with `[OFFER_MECHANIC]` on `[TARGET_EVENT]`. Bet on eligible markets today. `[T&CS]` apply. | 102 | Offer-led | Fits `[TARGET_SEGMENT]` if event affinity is confirmed | Pass | Pass | Clear reference | No urgency beyond neutral timing | Value must match approved cap |
| B | Back `[TARGET_EVENT]` with `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`. Tap to join. `[T&CS]` apply. | 96 | Event-led | Fits confirmed `[TARGET_SPORT]` interest | Pass | Pass | Clear reference | Avoids certainty claims | Eligible markets need confirmation |

- [RECOMMENDATION] Use Variant B if `[TARGET_EVENT]` affinity is confirmed; use Variant A if offer clarity is more important.
- [NEEDS CONFIRMATION] Final `[T&CS]`, opt-out requirement, expiry, and eligible markets.
```

