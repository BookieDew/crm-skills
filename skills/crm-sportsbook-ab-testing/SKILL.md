---
name: crm-sportsbook-ab-testing
description: Designs sportsbook CRM A/B or multivariate tests with hypothesis, variant logic, primary KPI, secondary KPIs, segment split, control group, measurement window, risk controls, and decision rule.
---

# CRM Sportsbook A/B Testing

## Purpose

Design A/B or multivariate tests for sportsbook CRM campaigns, offers, copy, journeys, and localisation choices with a clear hypothesis, variant logic, KPIs, segment split, control group, measurement window, risk controls, and decision rule.

## Role in the Skill Pack

This skill turns campaign briefs and journeys into measurable experiments. It feeds post-campaign analysis and future campaign improvement.

## When to Use

- A campaign has more than one offer, copy angle, timing, or journey option.
- A CRM manager wants to prove incrementality.
- A campaign needs a control group.
- A post-campaign analysis needs a decision framework.
- There is uncertainty about segment fit or offer value.

## When Not to Use

- Do not test unsafe or non-compliant variants.
- Do not create final SMS copy; use `crm-sportsbook-sms-copy`.
- Do not replace post-campaign analysis; use `crm-sportsbook-post-campaign-analysis`.
- Do not invent performance baselines or market facts.

## Required Inputs

### Minimum required inputs

- Campaign objective.
- `[TARGET_SEGMENT]`
- Testable element.
- Primary KPI.

### Recommended inputs

- Campaign brief.
- Journey plan.
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- Control-group rules.
- Segment size.
- Measurement window.
- Cost and margin constraints.

### Advanced optional inputs

- Historical conversion rate.
- Expected uplift.
- Minimum detectable effect.
- Randomisation rules.
- Holdout policy.
- Bonus-cost model.
- GGR and NGR attribution rules.
- RG monitoring rules.

## Output

This skill produces a test plan with hypothesis, variants, primary KPI, secondary KPIs, segment split, control group, measurement window, risk controls, decision rule, and analysis cuts.

## Workflow

1. Load `crm-sportsbook-shared-principles` and campaign brief.
2. Confirm what is being tested: offer, value, copy angle, timing, journey step, or localisation choice.
3. Define one primary hypothesis.
4. Define variants with only one major difference where possible.
5. Define primary KPI and secondary KPIs.
6. Define segment split, randomisation, and control group.
7. Define measurement window and attribution rules.
8. Add RG, compliance, UX, and commercial risk controls.
9. Define decision rule and next action.
10. Mark missing baselines or inputs.

## Decision Logic

- Do not test a variant that fails RG or compliance review.
- Prefer simple A/B tests before multivariate tests.
- Use a control group when measuring incrementality or bonus cost impact.
- Keep offer-value tests within approved cost and terms.
- Avoid changing both offer and copy in the same A/B test unless explicitly multivariate.
- Use segment-level cuts for lifecycle, value, sport preference, bet type, bonus sensitivity, VIP status, and churn risk.
- Include RG observations and opt-out monitoring as safety metrics.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, optionally `crm-sportsbook-journey-builder` and `crm-sportsbook-rg-compliance-review`.
- Skills that should normally run after this one: `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel principles, and measurement principles.

## Sportsbook-Specific Considerations

Design tests with sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk in mind.

## Market-Agnostic Design Rules

Never assume market benchmarks, local behaviours, local event calendars, local regulations, local operators, local payment methods, or geo-specific response rates.

If market-specific test inputs are needed, ask for them, label assumptions `[ASSUMPTION]`, mark items `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt test design to `[TARGET_CHANNEL]`.

For SMS:

- Keep variant differences easy to read.
- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules. Do not test urgency, pressure, loss references, financial-solution claims, guaranteed-win language, misleading risk-free claims unless approved, unclear T&Cs, offers based on recent heavy losses, or manipulative win-back messaging.

Suppress self-excluded users, RG-risk users, ineligible-channel users, opted-out users, and frequency-capped users from all variants and controls as required.

## Commercial Guardrails

Protect margin and bonus cost. Define cost per variant, avoid open-ended exposure, use minimum odds, minimum stake, maximum bonus value, eligible markets, clear expiry, and include NGR/GGR and bonus cost in evaluation.

## Brand & UX Guardrails

Test meaningful differences without confusing customers. Avoid jargon, misleading terms, fake personalisation, stereotypes, and implication of certainty of winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## A/B Test Plan

### Hypothesis
- [RECOMMENDATION]

### Variants
| Variant | What changes | What stays fixed | Risk control |
|---|---|---|---|
| A |  |  |  |
| B |  |  |  |

### KPIs
- Primary KPI:
- Secondary KPIs:
- Safety metrics:

### Split
- Segment:
- Allocation:
- Control group:

### Measurement
- Window:
- Attribution:
- Analysis cuts:

### Decision Rule
- [RECOMMENDATION]

### Open Items
- [NEEDS CONFIRMATION]
```

## Example User Request

Create an A/B test for `[TARGET_CHANNEL]` campaign variants for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` using `[OFFER_MECHANIC]`.

## Example Output

```markdown
## A/B Test Plan

- Hypothesis: [RECOMMENDATION] A clearer offer-led SMS will improve qualifying bet conversion versus an event-led SMS without increasing opt-outs or bonus cost per converter.
- Variant A: Offer-led copy with `[OFFER_VALUE]` and `[T&CS]`.
- Variant B: Event-led copy for `[TARGET_EVENT]` with the same `[OFFER_VALUE]` and `[T&CS]`.
- Primary KPI: Qualifying bet conversion.
- Secondary KPIs: Click rate, bonus redemption, GGR, NGR, bonus cost per converter, opt-outs, RG interactions.
- [NEEDS CONFIRMATION] Segment size, measurement window, and control-group allocation.
```

