---
name: crm-sportsbook-shared-principles
description: Light execution reference for shared market-agnostic sportsbook CRM principles, assumption labels, RG guardrails, suppression rules, commercial controls, channel principles, measurement standards, and quality checks.
---

# CRM Sportsbook Shared Principles Light

## Purpose
Use this as the compact baseline for every light sportsbook CRM skill. It does not create campaign output directly; it defines the rules that specialist skills must apply.

## Role in the Skill Pack
This skill feeds every specialist light skill. Apply it before routing, market context, event planning, segmentation, offers, briefs, SMS copy, localisation, RG/compliance review, journeys, A/B tests, and post-campaign analysis.

## When to Use
Use for:
- Baseline market-agnostic rules.
- Assumption labels.
- Responsible-gaming and suppression checks.
- Commercial exposure controls.
- Channel separation and SMS principles.
- Measurement and final quality checks.

## When Not to Use
Do not use this skill to create campaign briefs, offers, SMS copy, localised copy, journeys, tests, or analysis. Route to the relevant specialist skill.

## Minimum Required Inputs
- User request or workflow context.
- Any supplied runtime context such as [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], [TARGET_SEGMENT], [TARGET_SPORT], [TARGET_EVENT], [CAMPAIGN_OBJECTIVE], [OFFER_MECHANIC], [OFFER_VALUE], [BRAND_TONE], [REGULATORY_NOTES], [T&CS], and [T&CS_LINK].

## Core Workflow
1. Treat all market, language, channel, sport, event, offer, regulatory, and brand details as runtime inputs only.
2. Separate confirmed facts from assumptions.
3. Mark missing critical items with [NEEDS CONFIRMATION].
4. Apply responsible-gaming suppressions before any targeting, copy, journey, test, or rollout recommendation.
5. Apply commercial caps and exposure controls before recommending an offer.
6. Keep SMS separate from future email and push skills.
7. Define measurement and guardrails before launch.

## Core Decision Logic
- Do not invent market facts, current events, local language, local rules, local sports preferences, local behaviours, operators, regulators, payment methods, slang, or cultural assumptions.
- If market-specific detail is needed, ask the user, use supplied data, use confirmed research when available, or mark [NEEDS CONFIRMATION].
- Do not target self-excluded users, RG-risk users, users in cooling-off, or users without valid channel opt-in.
- Do not encourage chasing losses, loss recovery, financial-solution framing, guaranteed-win claims, unapproved risk-free wording, aggressive urgency, or manipulative reactivation.
- If suppression data is unavailable, do not treat missing data as approval to launch.
- Protect margin with capped value, clear qualification, minimum stake or odds where relevant, expiry, eligible markets, usage limits, and abuse controls.
- Do not claim incrementality without a control group or valid comparison.

## Dependencies
- Depends on: none.
- Feeds into: all light skills.

## Market-Agnostic Rules
- Use placeholders only in examples.
- Do not hardcode specific countries, regions, languages, leagues, tournaments, teams, operators, payment methods, regulators, laws, local slang, or cultural behaviour.
- Label unconfirmed details with [ASSUMPTION], [NEEDS CONFIRMATION], or [RISK].

## Responsible-Gaming Guardrails
Always suppress or require review for:
- Self-excluded users.
- Users with RG risk flags.
- Users in cooling-off.
- Users without channel opt-in.
- Users with account, compliance, AML, fraud, or bonus restrictions.
- Recently heavy-losing users where relevant to reactivation or incentives.

Never use:
- Chasing-losses or loss-recovery logic.
- Financial-pressure framing.
- Guaranteed-win claims.
- Unapproved risk-free or free-money claims.
- Excessive urgency or repeated pressure.
- Invasive personalisation based on sensitive behaviour.

## Commercial Guardrails
Require clear controls for:
- [OFFER_VALUE].
- Qualification action.
- Maximum reward or exposure.
- Minimum stake and minimum odds where relevant.
- Eligible markets or products.
- Expiry.
- Usage limits.
- Bonus abuse, sharp, arb-sensitive, and VIP exposure.
- GGR, NGR, bonus cost, and incrementality measurement where relevant.

## Brand/UX Guardrails
- Be clear, factual, and easy to act on.
- Make value, eligibility, CTA, and [T&CS] visible or linked.
- Avoid jargon, stereotypes, fake personalisation, certainty-of-winning language, and hidden restrictions.
- If [TARGET_CHANNEL] is SMS, use one short message, one offer, one CTA, and clear [T&CS_LINK] handling.

## Assumption Labels
- [CONFIRMED] - Information explicitly supplied by the user or source.
- [ASSUMPTION] - Reasonable but unconfirmed assumption.
- [NEEDS CONFIRMATION] - Required before launch or conclusion.
- [RISK] - Compliance, RG, commercial, UX, brand, data-quality, or operational risk.
- [RECOMMENDATION] - Proposed action.

## Output Template
```markdown
# Shared Principles Check

## 1. Confirmed Inputs
- [CONFIRMED]

## 2. Assumptions and Missing Items
- [ASSUMPTION]
- [NEEDS CONFIRMATION]

## 3. Mandatory Suppressions
- Self-exclusion:
- RG risk:
- Cooling-off:
- Channel opt-in:
- Compliance/account restrictions:

## 4. RG/Compliance Risks
- [RISK]

## 5. Commercial Controls
- Offer value:
- Exposure cap:
- Qualification:
- [T&CS] / [T&CS_LINK]:

## 6. Measurement Guardrails
- Primary metric:
- Commercial metrics:
- RG/UX guardrails:
- Control or comparison:

## 7. Recommended Next Skills
- [RECOMMENDATION]
```

## Recommended Next Skills
Use the relevant specialist skill: `crm-sportsbook-skill-router`, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, or `crm-sportsbook-post-campaign-analysis`.
