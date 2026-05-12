---
name: crm-sportsbook-event-opportunity
description: Identifies sportsbook CRM campaign opportunities around runtime-supplied sports, fixtures, tournaments, local events, calendar moments, and betting moments without inventing current events.
---

# CRM Sportsbook Event Opportunity

## Purpose

Identify campaign opportunities around sports, fixtures, tournaments, local events, calendar moments, and betting moments using only runtime-supplied or verified event data.

## Role in the Skill Pack

This skill turns market context into event-led campaign opportunities and feeds segmentation, offer design, campaign briefs, journeys, and A/B tests.

## When to Use

- A campaign should connect to `[TARGET_EVENT]`.
- The CRM manager wants sports calendar opportunities.
- A segment needs event-relevance scoring.
- A sportsbook offer needs event timing or bet-moment alignment.
- A campaign brief needs activation logic around pre-match or live betting.

## When Not to Use

- Do not invent current fixtures, tournaments, live events, or event schedules.
- Do not finalise a segment; use `crm-sportsbook-player-segmentation`.
- Do not design the full offer; use `crm-sportsbook-offer-mechanics`.
- Do not produce final SMS; use `crm-sportsbook-sms-copy`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[TARGET_EVENT]` or event theme supplied at runtime.
- Campaign objective.

### Recommended inputs

- `[TARGET_SPORT]`
- Event date and start time supplied at runtime.
- Eligible markets or bet types.
- Segment sport affinity.
- Pre-match versus live betting objective.
- `[REGULATORY_NOTES]`

### Advanced optional inputs

- Historical event performance.
- Event-level turnover, GGR, margin, and conversion data.
- Segment-level affinity scores.
- Odds boost or bet builder availability supplied at runtime.
- Trading or risk constraints supplied at runtime.

## Output

This skill produces an event opportunity map with campaign angles, segment fit, timing windows, offer fit, channel fit, risks, and recommendations.

## Workflow

1. Load `crm-sportsbook-shared-principles` and market context.
2. Confirm whether `[TARGET_EVENT]` and `[TARGET_SPORT]` are supplied or verified.
3. If current event data is needed but not supplied, mark it `[NEEDS CONFIRMATION]`.
4. Score event relevance against segment sport preference, bet type preference, and lifecycle objective.
5. Identify timing: early announcement, pre-match, live-eligible moment, reminder, last chance, or post-event retention.
6. Match possible offer mechanics to event behaviour and commercial constraints.
7. Flag RG, compliance, margin, and operational risks.
8. Recommend the strongest event opportunity and the safest fallback.

## Decision Logic

- If event data is missing, do not invent it.
- Prioritise events with confirmed relevance to `[TARGET_SEGMENT]`.
- Use pre-match timing for considered bets and simple qualification mechanics.
- Use live-oriented timing only when product availability, channel rules, and RG considerations support it.
- Avoid complex mechanics close to event start when SMS clarity would suffer.
- Avoid rich offers for low-margin or high-abuse contexts.
- If event relevance is weak, recommend a broader lifecycle campaign or request better event data.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`.
- Skills that should normally run after this one: `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel communication principles, and measurement principles.

## Sportsbook-Specific Considerations

Assess sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market, event schedule, local league, local sport preference, local operator, local regulation, payment method, or geo-specific behaviour.

If event knowledge is needed, ask for the fixture or calendar details, mark them `[NEEDS CONFIRMATION]`, state any interim logic as `[ASSUMPTION]`, or instruct research if research tools are available. Do not invent current fixtures or current events.

## Channel-Aware Design Rules

Adapt event recommendations to `[TARGET_CHANNEL]`.

For SMS:

- Use one clear event hook.
- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be handled by future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules. Do not use event timing to create emotional pressure or aggressive urgency. Do not target self-excluded users, RG risk users, users selected because of recent heavy losses, or users without valid channel eligibility.

Avoid chasing-loss language, financial-solution claims, guaranteed-win language, misleading risk-free claims unless approved, hidden T&Cs, and manipulative win-back framing.

## Commercial Guardrails

Protect margin around event volatility. Match offer value to customer value, avoid over-incentivising already active event bettors, avoid rich offers to bonus abusers, cap bonus exposure, set eligible markets, use minimum odds and minimum stake where relevant, define expiry, and align mechanic to activation, retention, reactivation, event activation, cross-sell, or VIP engagement.

## Brand & UX Guardrails

Make event value clear without implying certainty of winning. Avoid stereotypes about fans or bettors. Do not use fake personalisation such as claiming a customer follows `[TARGET_SPORT]` unless that is confirmed.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Event Opportunity Map

### Confirmed Event Context
- [CONFIRMED] [TARGET_EVENT]:
- [CONFIRMED] [TARGET_SPORT]:
- [CONFIRMED] Event timing:

### Opportunities
| Opportunity | Segment fit | Offer fit | Timing | Risk | Recommendation |
|---|---|---|---|---|---|
| [TARGET_EVENT] angle | [TARGET_SEGMENT] | [OFFER_MECHANIC] | [EVENT_TIMING] | [RISK] | [RECOMMENDATION] |

### Needs Confirmation
- [NEEDS CONFIRMATION] Current fixture or event details:
```

## Example User Request

Find campaign opportunities around `[TARGET_EVENT]` for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` using `[TARGET_CHANNEL]`.

## Example Output

```markdown
## Event Opportunity Map

- [CONFIRMED] Event: [TARGET_EVENT]
- [CONFIRMED] Sport: [TARGET_SPORT]
- [NEEDS CONFIRMATION] Exact event timing and eligible bet markets.
- [RECOMMENDATION] Use a simple pre-event [OFFER_MECHANIC] for customers with confirmed [TARGET_SPORT] affinity and valid channel consent.
- [RISK] Do not use last-minute pressure or imply likely winnings.
```

