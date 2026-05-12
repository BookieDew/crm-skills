---
name: crm-sportsbook-campaign-brief
description: Light execution version for creating a sportsbook CRM campaign blueprint from market context, event opportunity, segmentation, offer mechanics, channel logic, guardrails, testing, and measurement.
---

# CRM Sportsbook Campaign Brief Light

## Purpose
Create a compact execution-ready sportsbook CRM campaign blueprint that can feed copy, localisation, RG/compliance review, journey design, A/B testing, and post-campaign analysis.

## Role in the Skill Pack
This is the central synthesis skill. It combines market, event, segment, offer, channel, commercial, RG, compliance, operational, and measurement logic without replacing specialist skills.

## When to Use
Use for full campaign planning, approval handoff, campaign improvement, event-led campaigns, activation, retention, reactivation, VIP engagement, cross-sell within sportsbook, exclusions, measurement, and A/B test direction.

## When Not to Use
Do not create market research from scratch, choose raw-data segments, design complex offers without offer input, draft legal [T&CS], provide final compliance approval, analyse results, invent fixtures or local facts, or override suppressions.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT] or segmentation output.
- [OFFER_MECHANIC] or offer mechanics output.

## Core Workflow
1. Apply shared principles and read upstream market, event, segmentation, and offer outputs.
2. Identify confirmed inputs, assumptions, and missing launch-critical details.
3. Define objective, target audience, suppressions, customer insight, event rationale, offer summary, commercial rationale, customer proposition, channel plan, copy direction, personalisation, [T&CS] handling, operations, metrics, and test direction.
4. Check offer fit with [TARGET_SEGMENT], [TARGET_CHANNEL], and [CAMPAIGN_OBJECTIVE].
5. Flag RG, compliance, commercial, UX, brand, data, and operational risks.
6. Recommend next skills.

## Core Decision Logic
- If market context, event context, segment logic, or offer mechanics are missing, mark [NEEDS CONFIRMATION] and recommend the relevant upstream skill.
- If [TARGET_CHANNEL] is SMS, keep one offer, one CTA, clear value, and clear [T&CS_LINK].
- If the offer is too complex for SMS, simplify or use supporting explanation.
- For reactivation, suppress RG-risk and relevant heavy-loss users; avoid emotional pressure.
- For retention, justify incrementality and avoid over-incentivising natural activity.
- For activation, keep first action simple.
- For VIP, require manual review, cap exposure, and RG/compliance review.
- If [REGULATORY_NOTES] or [T&CS] are missing, do not claim launch readiness.
- If measurement is missing, add KPI, commercial, guardrail, control, and analysis handoff recommendations without inventing targets.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`.
- Normally after: `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Sportsbook-Specific Logic
Consider sport/event relevance, pre-match vs live timing, single vs accumulator behaviour, bet builder, odds boost, free bet, cashback, deposit/reload sensitivity, VIP review, bonus sensitivity, sharp or arb exposure, margin protection, bonus cost, product availability, frequency caps, GGR/NGR, and post-campaign RG monitoring.

## Market-Agnostic Rules
Do not assume local language, laws, sport preferences, betting habits, channel rules, event schedules, operators, payment methods, holidays, regulators, or cultural tone.

## Responsible-Gaming Guardrails
Reject or route for revision if the brief targets self-excluded, RG-risk, cooling-off, opted-out, or relevant heavy-loss users; encourages chasing losses; uses loss recovery; frames betting as financial help; implies guaranteed profit; hides restrictions; or uses manipulative urgency.

## Commercial Guardrails
Require capped value, qualification clarity, expiry, eligible markets, minimum stake/odds where relevant, usage limits, bonus abuse controls, sharp/arb controls, VIP exposure review, control group where useful, GGR/NGR/bonus cost tracking, and incrementality caution.

## Brand/UX Guardrails
Ensure campaign is clear, fair, not spammy, not misleading, not invasive, aligned with [BRAND_TONE], and supported by accessible [T&CS] / [T&CS_LINK].

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Campaign Brief

## 1. Campaign Summary
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Launch readiness:

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Customer Insight and Segment Logic
- Insight:
- Inclusion:
- Exclusion:
- Suppressions:
- Segment rationale:

## 6. Event / Sport Rationale
- Relevance:
- Timing:
- Product fit:
- Risks:

## 7. Offer Design and Customer Proposition
- Mechanic:
- Qualification:
- Reward:
- Exposure cap:
- Usage limits:
- [T&CS] / [T&CS_LINK]:
- Customer-friendly explanation:

## 8. Commercial Rationale
- Expected behaviour change:
- Incrementality logic:
- Cost control:
- Margin protection:
- Abuse controls:

## 9. Channel and Copy Direction
- Channel role:
- CTA direction:
- SMS suitability if applicable:
- Tone: [BRAND_TONE]
- Claims to avoid:

## 10. RG, Compliance, and Operational Notes
- [REGULATORY_NOTES]:
- Required suppressions:
- Offer/copy risks:
- Operational setup:
- QA:

## 11. Measurement and A/B Test Direction
- Primary KPI:
- Secondary KPIs:
- Commercial metrics:
- RG/UX guardrails:
- Control group:
- Test hypothesis:

## 12. Launch Checklist
- Market context checked:
- Segment logic checked:
- Suppressions applied:
- Offer configured:
- [T&CS] approved:
- Copy reviewed:
- RG/compliance reviewed:
- Tracking ready:
- Reporting ready:

## 13. Recommended Next Skills
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 14. Final Recommendation
- Ready with assumptions / Needs missing inputs / Needs offer approval / Needs RG/compliance input / Not recommended:
- Rationale:
```

## Recommended Next Skills
Proceed to SMS copy when [TARGET_CHANNEL] is SMS, localisation, RG/compliance review, journey builder, A/B testing, and post-campaign analysis setup.
