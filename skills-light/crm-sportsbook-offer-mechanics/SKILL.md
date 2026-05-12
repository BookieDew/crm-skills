---
name: crm-sportsbook-offer-mechanics
description: Light execution version for designing and evaluating sportsbook offer mechanics with segment fit, channel suitability, commercial exposure controls, and responsible-gaming safeguards.
---

# CRM Sportsbook Offer Mechanics Light

## Purpose
Design or review a sportsbook offer mechanic that fits [CAMPAIGN_OBJECTIVE], [TARGET_SEGMENT], [TARGET_SPORT], [TARGET_EVENT], [TARGET_CHANNEL], commercial controls, and RG guardrails.

## Role in the Skill Pack
Run after market context, event opportunity when relevant, and segmentation. Feed offer structure, constraints, risks, and alternatives into campaign brief, SMS copy, localisation, RG/compliance review, journey builder, A/B testing, and analysis.

## When to Use
Use to choose or improve an [OFFER_MECHANIC], compare mechanics, define qualification and reward rules, simplify an offer for SMS, reduce bonus abuse or margin risk, or create safer alternatives.

## When Not to Use
Do not write final SMS copy, build the full brief, create market context, define the audience from scratch, approve compliance, analyse results, override suppressions, invent market facts, or create loss-chasing offers.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT] or segmentation output.
- [OFFER_MECHANIC] if selected, or request for recommendation.

## Core Workflow
1. Apply shared principles and use upstream market/event/segment outputs.
2. Identify [CAMPAIGN_OBJECTIVE], [TARGET_SEGMENT], [TARGET_CHANNEL], and [OFFER_MECHANIC].
3. Confirm or request [OFFER_VALUE], qualification action, reward type, expiry, caps, eligible markets, usage limits, [T&CS], and [T&CS_LINK].
4. If no mechanic is selected, recommend one based on objective, segment fit, channel clarity, commercial exposure, abuse risk, and RG safety.
5. Check whether the offer is simple enough for [TARGET_CHANNEL], especially SMS.
6. Add lower-cost and higher-impact alternatives with risk tradeoffs.
7. Recommend downstream skills.

## Core Decision Logic
- If [TARGET_SEGMENT] is missing, run segmentation first.
- If [TARGET_CHANNEL] is SMS, prefer mechanics explainable in one short message.
- Reject or redesign chasing-losses, recent-loss, financial-pressure, guaranteed-win, unapproved risk-free, and hidden-restriction mechanics.
- For activation, prefer simple first-action mechanics.
- For retention, avoid over-incentivising natural activity.
- For reactivation, keep value capped and language low pressure; suppress risky users.
- For VIP, require manual review, exposure cap, and RG/compliance review.
- For bonus-sensitive, sharp, or arb-sensitive exposure, use exclusion, lower value, stricter eligible markets, manual approval, or low-exposure mechanics.
- If exposure is open-ended, require a cap.
- If [T&CS] are too complex for SMS, simplify the offer or use a support surface plus [T&CS_LINK].

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`.
- Normally after: `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Core Offer Menu
Use only where product availability, permissions, and [T&CS] are confirmed:
- Free bet: capped value, clear expiry, usage limit.
- Bet-and-get: clear qualifying action and reward.
- Odds boost: margin and sharp/arb controls.
- Accumulator insurance: clear refund conditions and cap; no safety implication.
- Cashback: never loss-recovery framed.
- Bet builder boost: product availability and complexity checks.
- Deposit or reload offer: no financial-solution framing; strong RG review.
- Mission or challenge: low action count; no excessive play pressure.
- Loyalty points: clear value and redemption if relevant.
- VIP bespoke offer: manual review and exposure cap.
- Event-specific voucher: confirmed event and product availability.
- Personalised stake-back: capped, not risk-free, no loss framing.

## Market-Agnostic Rules
Do not assume local offer rules, product availability, local language, sport preferences, regulations, payment methods, operator norms, or event schedules.

## Responsible-Gaming Guardrails
Reject mechanics that target self-excluded, RG-risk, cooling-off, recent heavy-loss, or vulnerable users; encourage chasing losses; imply guaranteed profit; hide restrictions; or push excessive frequency or accumulator complexity.

## Commercial Guardrails
Require capped exposure, qualification clarity, reward clarity, expiry, usage limits, eligible markets, minimum stake/odds where relevant, abuse controls, sharp/arb controls, VIP approvals, and incrementality measurement.

## Brand/UX Guardrails
Offer must be understandable, fair, easy to explain, not misleading, not invasive, and supported by visible [T&CS] or [T&CS_LINK].

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Offer Mechanics Output

## 1. Offer Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Proposed mechanic: [OFFER_MECHANIC]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Recommended Offer Mechanic
- Mechanic:
- Why it fits:
- Segment fit:
- Channel fit:
- Customer value:
- Commercial rationale:

## 6. Offer Structure
- Qualification action:
- Reward: [OFFER_VALUE]
- Exposure cap:
- Eligibility:
- Usage limits:
- Expiry:
- Key restrictions:
- [T&CS] / [T&CS_LINK]:

## 7. Alternatives
- Lower-cost option:
- Higher-impact option:
- Tradeoffs:

## 8. RG, Compliance, Commercial, and UX Review
- [REGULATORY_NOTES]:
- RG risks:
- Commercial risks:
- UX clarity:
- Required controls:

## 9. Recommended Next Skills
- crm-sportsbook-campaign-brief
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 10. Launch Readiness
- Ready with assumptions / Needs constraints / Needs commercial approval / Needs RG/compliance input / Not recommended
```

## Recommended Next Skills
Use campaign brief for synthesis, SMS copy for SMS wording, localisation for language/tone, RG/compliance review before launch, journey builder for execution, and A/B testing when comparing mechanics or value.
