---
name: crm-sportsbook-player-segmentation
description: Light execution version for defining, evaluating, refining, and safely applying market-agnostic sportsbook CRM player segments.
---

# CRM Sportsbook Player Segmentation Light

## Purpose
Define who should receive a sportsbook CRM campaign, who must be excluded, and whether [TARGET_SEGMENT] fits [CAMPAIGN_OBJECTIVE], [TARGET_SPORT], [TARGET_EVENT], [TARGET_CHANNEL], and offer direction.

## Role in the Skill Pack
Run after market context and event opportunity when relevant. Feed targeting, eligibility, suppression, data-quality, RG, commercial, and channel-fit logic into offer mechanics, campaign brief, SMS copy, localisation, journey, A/B testing, RG review, and analysis.

## When to Use
Use for audience definition, segment validation, eligibility rules, suppression rules, SMS-eligible audience building, segment comparison, reactivation audience safety, VIP audience review, or A/B test split preparation.

## When Not to Use
Do not write final copy, design complete offers, build a full campaign brief, override suppressions, use sensitive or prohibited attributes, invent market facts, or provide final legal eligibility decisions.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL], if known.
- Proposed [TARGET_SEGMENT] or available customer data.

## Core Workflow
1. Apply shared principles, market context, and event context if relevant.
2. Identify [CAMPAIGN_OBJECTIVE] and proposed [TARGET_SEGMENT].
3. List confirmed customer and campaign inputs.
4. Mark missing lifecycle, value, behaviour, risk, opt-in, RG, and suppression data as [NEEDS CONFIRMATION].
5. Apply mandatory exclusions: self-exclusion, RG risk, cooling-off, channel opt-out, compliance/account restriction, AML/fraud restriction, bonus restrictions, and relevant heavy-loss suppressions.
6. Assess segment fit with objective, event/sport, channel, offer direction, and commercial logic.
7. Recommend target segment, exclusions, data-quality status, and next skills.

## Core Decision Logic
- If [TARGET_SEGMENT] is missing, propose a segmentation framework rather than a final audience.
- If [TARGET_CHANNEL] is SMS, require valid SMS opt-in or mark [NEEDS CONFIRMATION].
- If self-exclusion or RG-risk handling is unknown, mark [RISK] and do not mark launch-ready.
- Exclude self-excluded, RG-risk, cooling-off, opted-out, and restricted users.
- For reactivation, exclude recently heavy-losing or RG-risk users and avoid pressure.
- For retention, avoid over-incentivising highly active users without incrementality logic.
- For activation, prioritise simple first-action segments.
- For event-led campaigns, prioritise confirmed sport/event/bet-type interest.
- For VIP segments, require manual review and RG/compliance review.
- For bonus-sensitive, sharp, or arb-sensitive users, recommend exclusion, lower-value mechanics, or stricter controls.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led.
- Normally after: `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Market-Agnostic Rules
Do not assume local sport preferences, channel preferences, language, regulations, player value thresholds, local habits, or cultural tone.

## Responsible-Gaming Guardrails
Never recommend targeting based on losses, vulnerability, financial distress, loss recovery, or risky behaviour. Suppress self-excluded, RG-risk, cooling-off, channel opt-out, restricted, and relevant heavy-loss users.

## Commercial Guardrails
Flag bonus cost, low incrementality, bonus abuse, sharp or arb exposure, VIP cost, segment overlap, fatigue, frequency cap, and control group integrity risks.

## Brand/UX Guardrails
Avoid creepy personalisation, overly narrow targeting that feels invasive, broad irrelevant targeting, spammy frequency, or segment logic that cannot be explained safely.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Player Segmentation Output

## 1. Segmentation Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Proposed segment: [TARGET_SEGMENT]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Recommended Target Segment
- Segment name:
- Inclusion criteria:
- Exclusion criteria:
- Channel eligibility:
- RG/compliance eligibility:
- Commercial eligibility:

## 6. Segment Rationale
- Customer relevance:
- Sport/event relevance:
- Offer relevance:
- Channel relevance:
- Commercial rationale:

## 7. Secondary Segment Options
| Segment | Use case | Benefit | Risk | When to use |
|---|---|---|---|---|
|  |  |  |  |  |

## 8. Suppression Rules
- Self-exclusion:
- RG risk:
- Cooling-off:
- Channel opt-out:
- Compliance/account restrictions:
- Bonus abuse restrictions:
- Recently heavy-losing users where relevant:

## 9. Segment-to-Offer Fit
- Suitable offer directions:
- Offer directions to avoid:
- Constraints for offer mechanics:

## 10. RG, Compliance, Commercial, and Data Notes
- [REGULATORY_NOTES]:
- [RISK]
- [RECOMMENDATION]
- Data quality:

## 11. Recommended Next Skills
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 12. Launch Readiness
- Ready with assumptions / Needs segmentation data / Needs RG/compliance input / Not recommended
```

## Recommended Next Skills
Proceed to offer mechanics, campaign brief, RG/compliance review, journey builder, A/B testing, and post-campaign analysis feedback as needed.
