---
name: crm-sportsbook-skill-router
description: Light router for selecting the shortest safe market-agnostic sportsbook CRM skill chain without creating specialist campaign output itself.
---

# CRM Sportsbook Skill Router Light

## Purpose
Route a CRM request to the right light skill or skill chain. Use it to interpret the goal, identify missing context, and recommend the next workflow step.

## Role in the Skill Pack
The router sits after `crm-sportsbook-shared-principles` and before specialist skills. It does not replace campaign brief, offer, copy, localisation, RG review, journey, test, or analysis skills.

## When to Use
Use when the user asks which skill to use, requests an end-to-end campaign, asks for offer ideas, SMS copy, localisation, RG/compliance review, journey design, A/B testing, analysis, or improvement of existing campaign material.

## When Not to Use
Do not use to create full specialist outputs. Route to the relevant skill when execution output is required.

## Minimum Required Inputs
- User request.
- Any known [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], [TARGET_SEGMENT], [TARGET_SPORT], [TARGET_EVENT], [CAMPAIGN_OBJECTIVE], [OFFER_MECHANIC], [OFFER_VALUE], [BRAND_TONE], [REGULATORY_NOTES], [T&CS], or [T&CS_LINK].

## Core Workflow
1. Apply `crm-sportsbook-shared-principles`.
2. Interpret the user goal.
3. Identify the shortest safe skill chain.
4. Flag missing critical context.
5. Add RG/compliance review whenever copy, offers, eligibility, suppressions, reminders, urgency, VIP handling, or reactivation are involved.
6. Recommend the next prompt or skill output needed.

## Core Decision Logic
- Market context: use `crm-sportsbook-market-context`.
- Event ideas or event-led planning: market context -> `crm-sportsbook-event-opportunity`.
- Player targeting or eligibility: `crm-sportsbook-player-segmentation`.
- Offer ideas or constraints: segmentation -> `crm-sportsbook-offer-mechanics` -> `crm-sportsbook-rg-compliance-review`.
- Full campaign: market context -> event opportunity -> segmentation -> offer mechanics -> campaign brief -> SMS copy if [TARGET_CHANNEL] is SMS -> localisation -> RG/compliance review -> A/B testing.
- SMS copy only: SMS copy -> localisation -> RG/compliance review. Add offer mechanics first if offer constraints are unclear.
- Localisation: localisation -> RG/compliance review. Add market context if [TARGET_MARKET] or [TARGET_LANGUAGE] is missing.
- Journey: campaign brief -> journey builder -> RG/compliance review. Add SMS copy if messages are not drafted.
- A/B testing: campaign brief if context is weak -> RG/compliance review if variants affect risk -> A/B testing.
- Results analysis: post-campaign analysis -> A/B testing for follow-up design.
- If [TARGET_CHANNEL] is not SMS and no channel-specific skill exists, route to campaign brief, localisation, and RG/compliance review, and mark detailed channel execution [NEEDS CONFIRMATION].

## Dependencies
- Depends on: `crm-sportsbook-shared-principles`.
- Feeds into: all specialist light skills.

## Market-Agnostic Rules
Do not invent market, event, language, sport, regulatory, operator, payment, or cultural details. Use placeholders and labels.

## Responsible-Gaming Guardrails
Do not route directly to launch when self-exclusion, RG-risk, cooling-off, channel opt-in, suppression, T&C, or regulatory handling is unclear. Route to `crm-sportsbook-rg-compliance-review`.

## Commercial Guardrails
Offer or testing routes must consider capped exposure, bonus cost, abuse risk, sharp or arb exposure, VIP manual review, and incrementality.

## Brand/UX Guardrails
Route complex mechanics away from SMS-only execution unless the offer can be explained briefly with clear [T&CS_LINK].

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

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
- [TARGET_MARKET]:
- [TARGET_LANGUAGE]:
- [TARGET_CHANNEL]:
- [TARGET_SEGMENT]:
- [TARGET_SPORT]:
- [TARGET_EVENT]:
- [CAMPAIGN_OBJECTIVE]:
- [OFFER_MECHANIC]:
- [OFFER_VALUE]:
- [T&CS] / [T&CS_LINK]:

### 5. Missing Inputs
- [NEEDS CONFIRMATION]

### 6. Assumptions
- [ASSUMPTION]

### 7. Expected Final Output
- [RECOMMENDATION]

### 8. Recommended Next Prompt
- [RECOMMENDATION]
```

## Recommended Next Skills
Recommend the shortest specialist chain needed. Include `crm-sportsbook-rg-compliance-review` whenever launch safety is affected.
