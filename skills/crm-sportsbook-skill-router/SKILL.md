---
name: crm-sportsbook-skill-router
description: Router and orchestration layer for a market-agnostic sportsbook CRM skill pack. Selects the right specialist skill or skill chain for CRM requests without creating full campaign outputs itself.
---

# CRM Sportsbook Skill Router

## Purpose

This skill selects the right sportsbook CRM skill or skill chain for a CRM manager's request.

Use it to interpret the user goal, identify the minimum useful sequence of skills, flag missing context, and recommend the next prompt or next workflow step.

This skill must not create full campaign outputs itself unless the user is only asking for routing guidance. For campaign briefs, offers, SMS copy, localisation, responsible-gaming review, journeys, tests, or analysis, route to the relevant specialist skill.

Always apply `crm-sportsbook-shared-principles` before routing decisions. The router must preserve market-agnostic design, responsible-gaming guardrails, suppression logic, commercial protection, and assumption labelling.

## When to Use

Use this skill when the user asks:

- Which skill should I use?
- Create a campaign from scratch.
- Improve an existing campaign.
- Create offer ideas.
- Write customer-facing copy.
- Localise campaign copy.
- Review compliance or RG safety.
- Build a campaign journey.
- Design an A/B test.
- Analyse campaign results.

## Required Inputs

The router can work with partial inputs. It should request or label missing context rather than blocking progress.

Inputs to check:

- User request.
- Available campaign context.
- Target channel if known: `[TARGET_CHANNEL]`.
- Campaign objective if known.
- Target market if known: `[TARGET_MARKET]`.
- Target segment if known: `[TARGET_SEGMENT]`.
- Target event if known: `[TARGET_EVENT]`.
- Target sport if known: `[TARGET_SPORT]`.
- Offer mechanic if known: `[OFFER_MECHANIC]`.
- Target language if known: `[TARGET_LANGUAGE]`.
- Existing campaign material if any.

## Router Skill Map

The router must understand and route between these skills:

- `crm-sportsbook-shared-principles`
- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`
- `crm-sportsbook-player-segmentation`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`
- `crm-sportsbook-localisation`
- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`
- `crm-sportsbook-post-campaign-analysis`

## Routing Logic

Start every chain with `crm-sportsbook-shared-principles` as the implicit foundation. Include it explicitly in the output when the user asks for a full chain or when the request has RG, compliance, commercial, or market-agnostic risk.

### Market understanding

If the user asks for market understanding, runtime market inputs, or what is known about `[TARGET_MARKET]`, use:

1. `crm-sportsbook-market-context`

### Event ideas

If the user asks for event ideas, sports calendar opportunities, campaign moments, or event-led CRM angles, use:

1. `crm-sportsbook-market-context`
2. `crm-sportsbook-event-opportunity`

If current event data is missing, route anyway and mark it `[NEEDS CONFIRMATION]`.

### Player targeting

If the user asks for player targeting, audience rules, segment evaluation, eligibility, exclusions, or who should receive a campaign, use:

1. `crm-sportsbook-player-segmentation`

Add `crm-sportsbook-market-context` first if `[TARGET_MARKET]` or `[TARGET_LANGUAGE]` affects eligibility, consent, localisation, or compliance notes.

### Offer ideas

If the user asks for offer ideas, incentive selection, offer constraints, or mechanic comparison, use:

1. `crm-sportsbook-player-segmentation`
2. `crm-sportsbook-offer-mechanics`
3. `crm-sportsbook-rg-compliance-review`

This chain protects against weak segment fit, uncapped bonus exposure, bonus abuse risk, sharp or arb-sensitive behaviour, and RG risk.

### Full campaign

If the user asks for a full campaign, campaign from scratch, end-to-end campaign plan, or campaign brief plus execution guidance, use:

1. `crm-sportsbook-market-context`
2. `crm-sportsbook-event-opportunity`
3. `crm-sportsbook-player-segmentation`
4. `crm-sportsbook-offer-mechanics`
5. `crm-sportsbook-campaign-brief`
6. `crm-sportsbook-sms-copy` if `[TARGET_CHANNEL]` is SMS
7. `crm-sportsbook-localisation`
8. `crm-sportsbook-rg-compliance-review`
9. `crm-sportsbook-ab-testing`

If `[TARGET_CHANNEL]` is not SMS and no channel-specific skill exists, route to `crm-sportsbook-campaign-brief`, `crm-sportsbook-localisation`, and `crm-sportsbook-rg-compliance-review`, then mark detailed channel execution `[NEEDS CONFIRMATION]`.

### SMS copy only

If the user asks for SMS copy only, SMS variants, or short customer-facing SMS wording, use:

1. `crm-sportsbook-sms-copy`
2. `crm-sportsbook-localisation`
3. `crm-sportsbook-rg-compliance-review`

Add `crm-sportsbook-offer-mechanics` first if `[OFFER_MECHANIC]` or offer constraints are unclear.

### Localisation

If the user asks for localisation, local adaptation, target-language adaptation, tone adaptation, or market style review, use:

1. `crm-sportsbook-localisation`
2. `crm-sportsbook-rg-compliance-review`

Add `crm-sportsbook-market-context` first if `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, or local guidance is missing.

### Compliance or RG review

If the user asks for compliance review, responsible-gaming safety, launch safety, risk review, or whether copy or an offer is safe to use, use:

1. `crm-sportsbook-rg-compliance-review`

Route fixes back to the skill that produced the risky item.

### Journey design

If the user asks for journey design, message sequence, reminders, exit criteria, frequency caps, or lifecycle journey logic, use:

1. `crm-sportsbook-campaign-brief`
2. `crm-sportsbook-journey-builder`
3. `crm-sportsbook-rg-compliance-review`

Add `crm-sportsbook-sms-copy` before journey review if the journey includes SMS text.

### Test design

If the user asks for A/B testing, test design, holdout logic, variant logic, hypothesis, KPIs, or decision rules, use:

1. `crm-sportsbook-ab-testing`

Add `crm-sportsbook-campaign-brief` first if the campaign objective, segment, offer, or channel plan is not clear. Add `crm-sportsbook-rg-compliance-review` if any test variant changes offer value, urgency, eligibility, or customer-facing wording.

### Campaign result analysis

If the user asks for campaign result analysis, performance readout, learnings, bonus cost impact, GGR, NGR, retention, or next campaign recommendations, use:

1. `crm-sportsbook-post-campaign-analysis`
2. `crm-sportsbook-ab-testing`

Use `crm-sportsbook-ab-testing` after analysis when the next step is to design a follow-up test or interpret test validity.

### Campaign improvement

If the user asks to improve an existing campaign, inspect the weak point and route narrowly:

- Weak market context: `crm-sportsbook-market-context`
- Weak event hook: `crm-sportsbook-event-opportunity`
- Weak targeting: `crm-sportsbook-player-segmentation`
- Weak offer: `crm-sportsbook-offer-mechanics`
- Weak brief: `crm-sportsbook-campaign-brief`
- Weak SMS copy: `crm-sportsbook-sms-copy`
- Weak localisation: `crm-sportsbook-localisation`
- Weak journey: `crm-sportsbook-journey-builder`
- Weak test plan: `crm-sportsbook-ab-testing`
- Weak performance interpretation: `crm-sportsbook-post-campaign-analysis`

Finish with `crm-sportsbook-rg-compliance-review` when the improvement affects offer value, eligibility, suppression, timing, copy, or customer pressure.

## Missing Context Handling

If key inputs are missing, the router should not block progress.

It should:

- Identify missing inputs.
- Use placeholders.
- Mark assumptions with `[ASSUMPTION]`.
- Mark critical missing items with `[NEEDS CONFIRMATION]`.
- Recommend the next best skill chain anyway.

Critical missing items usually include `[TARGET_MARKET]`, `[TARGET_CHANNEL]`, `[TARGET_SEGMENT]`, suppression status, offer constraints, customer-facing terms, and any runtime compliance notes. Missing current event data should also be marked `[NEEDS CONFIRMATION]`.

Do not invent local facts, current fixtures, local preferences, local requirements, or customer behaviour. If research tools are available and the task requires current information, recommend research as a step instead of inventing the detail.

## Market-Agnostic Guardrails

This router must never hardcode a specific country, region, language, league, operator, payment method, regulation, local sport preference, or geo-specific behaviour.

Use placeholders such as:

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[OFFER_MECHANIC]`

If a route depends on market-specific detail, label that dependency `[NEEDS CONFIRMATION]` and still recommend the safest next skill chain.

## Responsible-Gaming Routing Rules

Route to `crm-sportsbook-rg-compliance-review` whenever the request includes or changes:

- Customer-facing copy.
- Offer value or mechanic.
- Eligibility or exclusions.
- Reactivation logic.
- Reminder logic.
- Urgency or expiry language.
- VIP outreach.
- Any campaign aimed at churn risk or inactive customers.
- Any campaign where RG status, self-exclusion status, cooling-off status, opt-in status, or suppression logic is unclear.

Do not route directly to launch if self-exclusion, RG risk, cooling-off, opt-in, or suppression status is missing.

## Sportsbook-Specific Routing Considerations

Use sportsbook-specific context to choose the chain:

- Sport preference and event relevance usually require `crm-sportsbook-event-opportunity`.
- Lifecycle stage, customer value, VIP status, bonus sensitivity, churn risk, RG risk, and opt-in status usually require `crm-sportsbook-player-segmentation`.
- Bet type preference, pre-match versus live preference, single versus accumulator preference, stake level, and bonus history usually affect `crm-sportsbook-offer-mechanics`.
- Sharp, arb-sensitive, or bonus abuse concerns require `crm-sportsbook-offer-mechanics` plus `crm-sportsbook-rg-compliance-review`.
- Campaign performance, bonus cost, GGR, NGR, opt-outs, complaints, and post-campaign RG flags require `crm-sportsbook-post-campaign-analysis`.

## Output Template

```markdown
## Skill Routing Recommendation

### 1. Interpreted User Goal
- [CONFIRMED]

### 2. Recommended Skill Chain
1. [RECOMMENDATION] `crm-sportsbook-shared-principles`
2. [RECOMMENDATION] `skill-id`

### 3. Why This Chain
- [RECOMMENDATION]

### 4. Required Inputs
- User request:
- Available campaign context:
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Target event: [TARGET_EVENT]
- Target sport: [TARGET_SPORT]
- Offer mechanic: [OFFER_MECHANIC]

### 5. Missing Inputs
- [NEEDS CONFIRMATION]

### 6. Assumptions
- [ASSUMPTION]

### 7. Expected Final Output
- [RECOMMENDATION]

### 8. Recommended Next Prompt
- [RECOMMENDATION]
```

## Example User Request

Create an SMS campaign for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` around `[TARGET_EVENT]` for `[TARGET_SPORT]` using `[OFFER_MECHANIC]`. Use `[TARGET_LANGUAGE]`.

## Example Output

```markdown
## Skill Routing Recommendation

### 1. Interpreted User Goal
- [CONFIRMED] Create an SMS campaign using `[OFFER_MECHANIC]` for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`.

### 2. Recommended Skill Chain
1. [RECOMMENDATION] `crm-sportsbook-shared-principles`
2. [RECOMMENDATION] `crm-sportsbook-market-context`
3. [RECOMMENDATION] `crm-sportsbook-event-opportunity`
4. [RECOMMENDATION] `crm-sportsbook-player-segmentation`
5. [RECOMMENDATION] `crm-sportsbook-offer-mechanics`
6. [RECOMMENDATION] `crm-sportsbook-campaign-brief`
7. [RECOMMENDATION] `crm-sportsbook-sms-copy`
8. [RECOMMENDATION] `crm-sportsbook-localisation`
9. [RECOMMENDATION] `crm-sportsbook-rg-compliance-review`
10. [RECOMMENDATION] `crm-sportsbook-ab-testing`

### 3. Why This Chain
- [RECOMMENDATION] The request needs market context, event fit, segment logic, offer safety, campaign synthesis, SMS copy, localisation, RG/compliance review, and test planning.

### 4. Required Inputs
- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Target segment: `[TARGET_SEGMENT]`
- Target event: `[TARGET_EVENT]`
- Target sport: `[TARGET_SPORT]`
- Offer mechanic: `[OFFER_MECHANIC]`

### 5. Missing Inputs
- [NEEDS CONFIRMATION] Offer value, customer-facing terms, suppression status, launch timing, and success metrics.

### 6. Assumptions
- [ASSUMPTION] `[TARGET_CHANNEL]` is SMS because the request asks for an SMS campaign.

### 7. Expected Final Output
- [RECOMMENDATION] A market-agnostic SMS campaign workflow with a compliant brief, SMS variants, localisation notes, RG/compliance review, and A/B test plan.

### 8. Recommended Next Prompt
- [RECOMMENDATION] "Use this skill chain to create a campaign for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` using `[TARGET_CHANNEL]`, `[TARGET_EVENT]`, `[TARGET_SPORT]`, and `[OFFER_MECHANIC]`. Mark missing details with `[NEEDS CONFIRMATION]`."
```
