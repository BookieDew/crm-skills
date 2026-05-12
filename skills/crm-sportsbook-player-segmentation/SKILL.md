---
name: crm-sportsbook-player-segmentation
description: Defines and evaluates sportsbook CRM player segments by lifecycle stage, value, activity, bet type, sport preference, VIP status, bonus sensitivity, churn risk, RG flags, sharp or arb sensitivity, and channel eligibility.
---

# CRM Sportsbook Player Segmentation

## Purpose

Define and evaluate sportsbook CRM player segments for activation, retention, reactivation, event activation, cross-sell, VIP engagement, offer targeting, SMS copy, journeys, A/B tests, and post-campaign analysis.

## Role in the Skill Pack

This skill translates market and event context into eligible, commercially sensible, RG-safe customer groups. It feeds offer mechanics, campaign briefs, SMS copy, journeys, tests, and analysis.

## When to Use

- A user needs a `[TARGET_SEGMENT]`.
- A campaign needs eligibility and exclusion logic.
- A campaign targets sport preference, bet type, stake level, churn risk, VIP status, or bonus behaviour.
- The CRM manager needs to compare segments for an offer.
- A post-campaign analysis needs segment-level interpretation.

## When Not to Use

- Do not design the offer mechanic alone; use `crm-sportsbook-offer-mechanics`.
- Do not write final SMS; use `crm-sportsbook-sms-copy`.
- Do not decide launch compliance alone; use `crm-sportsbook-rg-compliance-review`.
- Do not infer protected or sensitive traits.

## Required Inputs

### Minimum required inputs

- Campaign objective.
- `[TARGET_MARKET]`
- Available segment definition or customer data fields.

### Recommended inputs

- Lifecycle stage.
- Value band.
- Activity recency and frequency.
- `[TARGET_SPORT]` affinity.
- Bet type preference.
- Pre-match versus live tendency.
- Single versus accumulator tendency.
- VIP status.
- Bonus sensitivity.
- Churn risk.
- RG flags and self-exclusion status.
- Channel eligibility for `[TARGET_CHANNEL]`.

### Advanced optional inputs

- Sharp or arb sensitivity.
- Bonus abuse risk.
- Margin contribution.
- Deposit behaviour.
- Bonus history.
- Stake distribution.
- Event affinity score.
- Predicted incremental uplift.
- Frequency-cap status.

## Output

This skill produces a segment brief with target group, exclusions, rationale, offer suitability, channel suitability, RG risks, commercial risks, and measurement splits.

## Workflow

1. Load `crm-sportsbook-shared-principles` and market context.
2. List available customer fields and mark missing fields.
3. Define the target segment in positive eligibility terms.
4. Define mandatory suppressions and exclusions.
5. Evaluate lifecycle, value, activity, sport preference, event relevance, bet type, stake, VIP status, bonus sensitivity, churn risk, sharp or arb sensitivity, bonus abuse risk, and RG flags.
6. Score segment fit for activation, retention, reactivation, event activation, cross-sell, or VIP engagement.
7. Recommend suitable offer mechanics and unsuitable mechanics.
8. Recommend control group and measurement cuts.

## Decision Logic

- Exclude self-excluded users and active RG-risk users.
- Exclude users without valid consent for `[TARGET_CHANNEL]`.
- Exclude or down-weight bonus abuse risk users for rich offers.
- Avoid high-value offers for already active users unless incremental value is justified.
- Treat VIP segments with bespoke value, tighter review, and margin protection.
- Treat sharp or arb-sensitive users with constrained mechanics and risk review.
- Match sport and event campaigns to confirmed sport preference or event affinity.
- Match accumulator mechanics only to users with confirmed accumulator preference.
- Match bet builder mechanics only where product usage or suitability is confirmed.
- Use lower-friction mechanics for early lifecycle or reactivation segments.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, optionally `crm-sportsbook-event-opportunity`.
- Skills that should normally run after this one: `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel communication principles, and measurement principles.

## Sportsbook-Specific Considerations

Always consider sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume market-specific segment behaviour. Do not hardcode country, region, language, local league, local sport preference, local operator, local regulation, payment method, or geo-specific behaviour.

If local segment behaviour is needed, ask for it, label a provisional point `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt segment eligibility to `[TARGET_CHANNEL]`.

For SMS:

- Require SMS eligibility and frequency-cap checks.
- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules even if local notes are limited. Suppress self-excluded users, RG-risk users, recent heavy-loss selected users, and users whose behaviour suggests potential harm. Avoid targeting logic or copy that encourages chasing, emotional pressure, financial-solution claims, guaranteed wins, misleading risk-free claims, or hidden T&Cs.

## Commercial Guardrails

Protect margin and bonus cost by matching offer value to customer value, avoiding over-incentivising already active users, avoiding rich offers to bonus abusers, capping bonus exposure, using minimum odds, minimum stake, maximum bonus value, eligible markets, clear expiry, and objective fit.

## Brand & UX Guardrails

Be direct about why a segment is targeted using confirmed behavioural data only. Avoid fake personalisation, stereotypes, jargon, misleading terms, and certainty-of-winning claims.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Player Segment Brief

### Target Segment
- [CONFIRMED] [TARGET_SEGMENT]:

### Eligibility
- Include:
- Exclude:

### Segment Assessment
| Factor | Finding | Label |
|---|---|---|
| Lifecycle |  | [CONFIRMED] |
| Sport preference | [TARGET_SPORT] | [CONFIRMED] |
| Bonus sensitivity |  | [NEEDS CONFIRMATION] |
| RG status |  | [RISK] |

### Offer Fit
- [RECOMMENDATION] Suitable:
- [RECOMMENDATION] Avoid:

### Measurement Cuts
- [RECOMMENDATION] Analyse by lifecycle, stake band, sport affinity, bet type preference, bonus sensitivity, and channel eligibility.
```

## Example User Request

Define `[TARGET_SEGMENT]` for an event-led campaign in `[TARGET_MARKET]` using `[TARGET_CHANNEL]`.

## Example Output

```markdown
## Player Segment Brief

- [CONFIRMED] Segment: [TARGET_SEGMENT]
- [RECOMMENDATION] Include customers with confirmed [TARGET_SPORT] preference, relevant activity recency, and valid [TARGET_CHANNEL] consent.
- [RISK] Exclude self-excluded, RG-risk, bonus abuse risk, and frequency-capped users.
- [NEEDS CONFIRMATION] Stake bands, bonus sensitivity, sharp or arb sensitivity, and event affinity score.
```

