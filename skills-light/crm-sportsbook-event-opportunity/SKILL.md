---
name: crm-sportsbook-event-opportunity
description: Light execution version for identifying and evaluating sportsbook CRM opportunities around runtime-supplied sports, events, calendar moments, lifecycle moments, and betting moments without inventing event facts.
---

# CRM Sportsbook Event Opportunity Light

## Purpose
Evaluate whether a supplied [TARGET_SPORT], [TARGET_EVENT], calendar moment, lifecycle moment, or betting moment is suitable for sportsbook CRM activation.

## Role in the Skill Pack
Run after market context when the campaign is event-led or timing-led. Feed event rationale, opportunity priority, segment fit, offer direction, timing caution, and risk notes into segmentation, offer mechanics, campaign brief, SMS copy, journey, A/B testing, and RG/compliance review.

## When to Use
Use when assessing an event-led campaign idea, comparing event opportunities, planning a campaign calendar, checking segment-event fit, or deciding whether [TARGET_CHANNEL] can support the event angle.

## When Not to Use
Do not invent current fixtures, schedules, teams, odds, event dates, local sports preferences, or market facts. Do not write final copy, final offers, legal terms, journeys, tests, or performance analysis.

## Minimum Required Inputs
- [TARGET_MARKET]
- [CAMPAIGN_OBJECTIVE], if known.
- At least one supplied event input: [TARGET_SPORT], [TARGET_EVENT], or event calendar data supplied at runtime.

## Core Workflow
1. Apply shared principles and market context.
2. Identify supplied sport, event, or timing context.
3. Separate confirmed event facts from assumptions.
4. Mark missing timing, product availability, eligible markets, event relevance, and compliance notes as [NEEDS CONFIRMATION].
5. Assess relevance to [CAMPAIGN_OBJECTIVE], [TARGET_SEGMENT], [TARGET_CHANNEL], and offer direction.
6. Identify timing options: pre-event, event-day, live/in-play, post-event, or multi-step journey.
7. Flag RG, commercial, UX, operational, and T&C risks.
8. Prioritise the opportunity and recommend downstream skills.

## Core Decision Logic
- If [TARGET_EVENT] or event timing is missing, mark [NEEDS CONFIRMATION].
- If current event data is required, do not invent it; request data or use confirmed research when available.
- If [TARGET_CHANNEL] is SMS, prefer one simple event angle and one simple offer.
- If event relevance to [TARGET_SEGMENT] is weak, recommend a different segment or event.
- If live/in-play timing is involved, flag operational, availability, and pressure risks.
- If reactivation is the objective, avoid emotional pressure and loss-recovery framing.
- If retention is the objective, avoid over-incentivising likely natural activity.
- If VIP engagement is involved, require manual review and exposure controls.
- If the event angle implies betting is necessary to enjoy [TARGET_EVENT], rewrite or reject it.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, and router if ambiguous.
- Normally after: `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`.

## Market-Agnostic Rules
Do not assume schedules, local popularity, local teams, leagues, tournaments, language, regulations, operators, holidays, or cultural behaviour. Use placeholders only in examples.

## Responsible-Gaming Guardrails
Flag or reject opportunities that target self-excluded users, RG-risk users, users in cooling-off, recently heavy-losing users, or users selected because of losses. Avoid pressure around event timing, guaranteed-profit claims, and chasing-losses logic.

## Commercial Guardrails
Check bonus cost, margin exposure, offer uptake risk, bonus abuse, sharp or arb exposure, VIP cost, product availability, market availability, settlement complexity, frequency caps, and opt-out risk.

## Brand/UX Guardrails
Keep event relevance clear, avoid forced or invasive personalisation, ensure [T&CS_LINK] can carry material restrictions, and avoid urgency that feels pressuring.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Event Opportunity Output

## 1. Opportunity Context
- Target market: [TARGET_MARKET]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Event Relevance Assessment
- Audience relevance:
- Segment relevance:
- Timing relevance:
- Channel relevance:
- Product relevance:

## 6. Campaign Opportunity Angles
| Angle | Description | Best-fit segment | Channel fit | Offer direction | Main risk |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## 7. Segment Fit and Offer Direction
- Recommended segment logic:
- Offer directions to consider:
- Offer directions to avoid:

## 8. Timing Plan
- Pre-event:
- Event-day:
- Live/in-play caution:
- Reminder logic:
- Post-event caution:

## 9. RG, Compliance, and Commercial Considerations
- [REGULATORY_NOTES]:
- [T&CS] / [T&CS_LINK]:
- [RISK]
- [RECOMMENDATION]

## 10. Opportunity Priority
- High / Medium / Low / Not recommended without more data:
- Rationale:

## 11. Recommended Next Skills
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 12. Launch Readiness
- Ready to proceed with assumptions / Needs event confirmation / Needs market context / Needs RG/compliance input / Not recommended
```

## Recommended Next Skills
Proceed to segmentation, offer mechanics, campaign brief, and RG/compliance review. Use journey builder and A/B testing when timing, reminders, or measurement design are needed.
