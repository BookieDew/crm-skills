---
name: crm-sportsbook-journey-builder
description: Light execution version for turning sportsbook CRM campaign strategy, offers, segments, SMS copy, localisation, and RG review into operational journey logic with triggers, steps, suppressions, exits, frequency caps, controls, measurement, and fallback rules.
---

# CRM Sportsbook Journey Builder Light

## Purpose
Create safe operational CRM journey logic for sportsbook campaigns: trigger, entry criteria, journey steps, timing, channel use, suppressions, exits, frequency caps, control group, measurement, and fallback logic.

## Role in the Skill Pack
Run after campaign brief, SMS copy where SMS is used, localisation where needed, and RG/compliance review before final approval. Feed A/B testing and post-campaign analysis.

## When to Use
Use for single-message campaigns, multi-step SMS journeys, event-led flows, activation, retention, reactivation, deposit/reload, VIP journeys, tournament or multi-stage journeys, product cross-sell, reminders, exits, suppressions, caps, controls, and operational CRM setup.

## When Not to Use
Do not create market context, raw audience segmentation, offer design, final SMS copy, localisation, final legal/compliance approval, unsafe journeys, journeys targeting excluded users, journeys encouraging chasing losses, or completed campaign analysis.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT] or segmentation output.
- [OFFER_MECHANIC] and [OFFER_VALUE], if promotional.
- Campaign brief output or sufficient campaign context.
- Suppression rules or instruction to use shared baseline suppressions.

## Core Workflow
1. Apply shared principles and read campaign brief, offer, segment, SMS copy, localisation, and RG review outputs.
2. Identify journey type, entry trigger, audience eligibility, suppressions, steps, timing, exits, frequency caps, control group, offer handling, measurement, and fallback logic.
3. Mark missing event timing, opt-in, self-exclusion, RG-risk, [T&CS_LINK], frequency caps, and [REGULATORY_NOTES] as [NEEDS CONFIRMATION] or [RISK].
4. Define suppression before entry, before every send, before reminder, before offer award, and before VIP outreach.
5. Define exits for conversion, offer redemption, expiry, opt-out, RG flag, self-exclusion, cooling-off, account restriction, event end/cancellation, ineligibility, or manual rejection.
6. Add measurement and analysis handoff.

## Core Decision Logic
- If [TARGET_SEGMENT], promotional offer, campaign brief, SMS copy, localisation, or RG review is missing, mark [NEEDS CONFIRMATION] and recommend the relevant skill.
- If the journey targets self-excluded, RG-risk, cooling-off, opted-out, or restricted users, mark Do Not Build / Do Not Launch.
- If [TARGET_CHANNEL] is SMS, keep journey short and prefer one message plus one justified neutral reminder at most.
- Repeated reminders must not escalate urgency or value without review.
- Reactivation journeys require conservative frequency, calm copy, strong suppressions, and no loss-recovery framing.
- Deposit/reload journeys require no financial-solution framing and stronger RG review.
- Event-led journeys require confirmed timing and fallback if event or product availability changes.
- VIP journeys require manual review, exposure caps, and owner accountability.
- If no exit criteria or frequency caps exist, mark [RISK].
- Customers must exit after conversion or if opt-out, RG flag, self-exclusion, cooling-off, account restriction, expiry, or ineligibility occurs.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy` when SMS exists, `crm-sportsbook-localisation` when localised copy exists, `crm-sportsbook-rg-compliance-review` before final launch.
- Normally after: `crm-sportsbook-rg-compliance-review` if final journey has not been reviewed, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Journey Types
- Single-message campaign: one entry trigger, one message, clear exit.
- Multi-step SMS journey: initial message plus limited neutral reminder.
- Event-led journey: pre-event, event-day, optional reminder, fallback.
- Activation journey: simple first action, no pressure.
- Retention journey: incrementality and fatigue controls.
- Reactivation journey: strong suppressions and calm wording.
- Deposit/reload journey: no financial pressure and clear bonus terms.
- VIP journey: manual review and exposure cap.
- Product cross-sell journey: simple, suitable, and low-risk.

## Market-Agnostic Rules
Do not assume local laws, channel rules, opt-in rules, send times, sports preferences, event schedules, language, payment methods, operators, or cultural tone.

## Responsible-Gaming Guardrails
Every journey must include suppression before entry and each send, exit on opt-out/RG flag/self-exclusion/cooling-off/account restriction, frequency caps, and RG/compliance review. Reject journeys using chasing losses, recent-loss triggers, financial pressure, shame, excessive urgency, aggressive deposit pressure, excessive betting frequency, or unsafe VIP pressure.

## Commercial Guardrails
Flag low incrementality, excessive frequency, bonus cost, uncapped rewards, bonus abuse, sharp/arb exposure, VIP over-costing, offer leakage, tracking gaps, poor control group design, and support burden.

## Brand/UX Guardrails
Journey should feel clear and useful, not pushy. Keep [OFFER_VALUE], CTA, and [T&CS_LINK] clear. Avoid invasive personalisation, stereotypes, and betting-is-necessary framing.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Journey Builder Output

## 1. Journey Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Journey type:

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Journey Summary
- Objective:
- Entry trigger:
- Number of steps:
- Main conversion action:
- Exit logic:
- Launch readiness:

## 6. Entry Criteria
- Inclusion:
- Channel eligibility:
- Offer eligibility:
- Product eligibility:
- Account eligibility:
- RG eligibility:
- Frequency cap eligibility:
- Control group assignment:

## 7. Exclusions & Suppressions
- Self-exclusion:
- RG risk:
- Cooling-off:
- Channel opt-out:
- Compliance/account restrictions:
- AML/fraud restrictions:
- Bonus abuse restrictions:
- Sharp/arb restrictions:
- VIP manual review:
- Recently heavy-losing users where relevant:

## 8. Journey Flow
| Step | Trigger | Timing | Audience condition | Channel | Purpose | Copy source | Suppression check | Exit check | Tracking | Risk notes |
|---|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |  |

## 9. Timing, Exit, and Offer Handling
- Launch timing:
- Reminder timing:
- Expiry handling:
- Exit criteria:
- Offer award:
- Redemption tracking:
- [T&CS] / [T&CS_LINK]:

## 10. RG, Compliance, Commercial, and Operational Review
- [REGULATORY_NOTES]:
- Required approvals:
- Bonus cost:
- Abuse/sharp/arb risk:
- Audience build:
- Offer setup:
- QA:
- Fallback setup:

## 11. Control Group and Measurement Plan
- Control group purpose:
- Primary KPI:
- Secondary KPIs:
- Commercial metrics:
- RG/UX guardrails:
- Journey-step tracking:
- Exit reason tracking:
- Post-campaign analysis inputs:

## 12. Fallback Logic
- Event unavailable:
- Offer unavailable:
- Product or market unavailable:
- Customer becomes ineligible:
- Link or T&C issue:
- Delivery or tracking issue:

## 13. Required Fixes Before Launch
| Issue | Risk type | Required fix | Owner | Blocking status |
|---|---|---|---|---|
|  |  |  |  |  |

## 14. Recommended Next Skills
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing
- crm-sportsbook-post-campaign-analysis

## 15. Final Recommendation
- Ready for RG/compliance review / Needs missing inputs / Needs copy/localisation / Needs offer approval / Needs specialist review / Not recommended:
- Rationale:
```

## Recommended Next Skills
Run RG/compliance review after final journey changes, A/B testing for journey variants or controls, and post-campaign analysis after completion.
