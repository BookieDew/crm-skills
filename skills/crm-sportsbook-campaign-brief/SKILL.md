---
name: crm-sportsbook-campaign-brief
description: Creates a complete sportsbook CRM campaign brief combining market context, event opportunity, segment, offer mechanic, channel plan, copy direction, exclusions, RG and compliance notes, commercial logic, A/B test idea, and success metrics.
---

# CRM Sportsbook Campaign Brief

## Purpose

Create a complete CRM campaign brief that synthesises market context, event opportunity, segment definition, offer mechanic, channel plan, copy direction, exclusions, RG and compliance notes, commercial logic, A/B test idea, and success metrics.

## Role in the Skill Pack

This is the central synthesis skill. It receives inputs from market context, event opportunity, segmentation, and offer mechanics, then feeds SMS copy, localisation, compliance review, journey building, testing, and analysis.

## When to Use

- A CRM manager asks for a full campaign brief.
- Multiple campaign components need to be joined into one launch-ready plan.
- A campaign needs objective, segment, offer, channel, suppression, measurement, and review structure.
- An existing idea needs to become an actionable brief.

## When Not to Use

- Do not write all final SMS variants; use `crm-sportsbook-sms-copy`.
- Do not perform final launch review; use `crm-sportsbook-rg-compliance-review`.
- Do not invent market or event facts.
- Do not analyse completed performance; use `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- Campaign objective.
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- Proposed `[OFFER_MECHANIC]` or request for recommendation.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[OFFER_VALUE]`
- `[BRAND_TONE]`
- `[T&CS]`
- `[REGULATORY_NOTES]`
- Launch timing.
- Eligible markets.
- Suppression rules.

### Advanced optional inputs

- Segment size.
- Budget and bonus-cost limit.
- Customer value bands.
- Previous campaign learnings.
- Control-group rules.
- Measurement window.
- Trading or risk restrictions.
- Localisation notes supplied at runtime.

## Output

This skill produces a complete campaign brief with objective, context, audience, offer, channel plan, copy direction, exclusions, RG/compliance notes, commercial rationale, A/B test idea, metrics, and open confirmations.

## Workflow

1. Load `crm-sportsbook-shared-principles`.
2. Import or create structured market context.
3. Import or define event opportunity.
4. Import or define player segment and exclusions.
5. Import or recommend offer mechanic and constraints.
6. Define channel plan for `[TARGET_CHANNEL]`.
7. Define copy direction and required T&C handling.
8. Define RG, compliance, UX, brand, and commercial risks.
9. Add A/B test idea and control group.
10. Add success metrics and analysis cuts.
11. Mark missing facts with assumption labels.
12. Route final campaign to compliance review before launch.

## Decision Logic

- If any mandatory suppression cannot be verified, mark campaign `[RISK]` and require review.
- If `[T&CS]` are missing, do not finalise copy or launch language.
- If `[REGULATORY_NOTES]` are missing, use baseline RG rules and mark local review `[NEEDS CONFIRMATION]`.
- If event relevance is weak, recommend revising audience or event hook.
- If offer cost is high relative to value, reduce value or tighten eligibility.
- If segment is already active, avoid rich offers unless incrementality is justified.
- If `[TARGET_CHANNEL]` is SMS, prioritise one clear offer, one CTA, and simple terms reference.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`.
- Skills that should normally run after this one: `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, offer safety, channel principles, measurement principles, and final campaign quality checklist.

## Sportsbook-Specific Considerations

Account for sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market. Do not hardcode country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If market-specific knowledge is needed, ask for it, mark an interim assumption `[ASSUMPTION]`, mark the item `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt the brief to `[TARGET_CHANNEL]`.

For SMS:

- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be acknowledged as future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules even if the user says the market has no strict rules. Avoid targeting self-excluded users, RG-risk users, users selected because of recent heavy losses, or users without channel eligibility.

Avoid chasing-loss language, references to previous losses as a reason to bet again, financial-solution claims, guaranteed-win language, misleading risk-free claims unless approved, aggressive urgency, hidden T&Cs, emotional pressure, offers based on recent heavy losses, and manipulative win-back language.

## Commercial Guardrails

Protect margin and bonus cost. Match offer value to customer value, avoid over-incentivising already active users, avoid rich offers to bonus abusers, avoid open-ended exposure, use minimum odds, minimum stake, max bonus value, eligible markets, clear expiry, and connect the campaign to activation, retention, reactivation, event activation, cross-sell, or VIP engagement.

## Brand & UX Guardrails

Keep the campaign direct and useful. Explain customer value quickly, make the next action obvious, avoid jargon, misleading terms, fake personalisation, stereotypes, and any implication of certainty of winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Campaign Brief

### Objective
- [CONFIRMED]

### Runtime Context
- [CONFIRMED] [TARGET_MARKET]:
- [CONFIRMED] [TARGET_LANGUAGE]:
- [CONFIRMED] [TARGET_CHANNEL]:
- [CONFIRMED] [TARGET_EVENT]:

### Audience
- Target: [TARGET_SEGMENT]
- Exclusions:

### Offer
- Mechanic: [OFFER_MECHANIC]
- Value: [OFFER_VALUE]
- Constraints:

### Channel Plan
- Channel: [TARGET_CHANNEL]
- Timing:
- CTA:

### Copy Direction
- Angle:
- Required T&C handling:

### RG & Compliance Notes
- [RISK]
- [NEEDS CONFIRMATION]

### Commercial Logic
- Cost control:
- Margin protection:

### A/B Test Idea
- Hypothesis:
- Variants:

### Success Metrics
- Primary KPI:
- Secondary KPIs:
- Control group:

### Launch Readiness
- [RECOMMENDATION]
```

## Example User Request

Create a campaign brief for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`, using `[TARGET_CHANNEL]`, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, and `[TARGET_EVENT]`.

## Example Output

```markdown
## Campaign Brief

- [CONFIRMED] Objective: Drive eligible participation around `[TARGET_EVENT]`.
- [CONFIRMED] Audience: `[TARGET_SEGMENT]`.
- [RECOMMENDATION] Offer: `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`, capped by `[T&CS]`.
- [RISK] Launch requires suppression of self-excluded, RG-risk, bonus abuse risk, ineligible-channel, and frequency-capped users.
- [NEEDS CONFIRMATION] `[REGULATORY_NOTES]`, final `[T&CS]`, eligible markets, and expiry.
- [RECOMMENDATION] Test offer-led SMS versus event-led SMS with a control group.
```

