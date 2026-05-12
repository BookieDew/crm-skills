---
name: crm-sportsbook-rg-compliance-review
description: Light execution version for structured pre-launch review of sportsbook CRM campaigns, offers, segments, copy, journeys, localisation, suppressions, T&Cs, commercial exposure, UX, brand, and operational risks.
---

# CRM Sportsbook Responsible Gaming & Compliance Review Light

## Purpose
Review sportsbook CRM material for responsible-gaming, compliance, suppression, offer, copy, [T&CS], localisation, channel, commercial, brand, UX, and operational risk before launch.

## Role in the Skill Pack
This is the final safety and quality gate before launch. It usually runs after campaign brief, offer mechanics, SMS copy, and localisation. It feeds journey builder, A/B testing, and post-campaign analysis.

## When to Use
Use for launch readiness, RG/compliance pre-review, copy risk detection, offer risk review, suppression review, T&C visibility, localisation review, journey risk review, safer rewrites, and required approvals.

## When Not to Use
Do not provide final legal advice, invent local regulation, draft full legal [T&CS], replace human compliance/RG/legal approval, approve campaigns with missing critical compliance inputs, or override suppressions.

## Minimum Required Inputs
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [CAMPAIGN_OBJECTIVE]
- [TARGET_SEGMENT] or segmentation output.
- [OFFER_MECHANIC] and [OFFER_VALUE], if reviewing an offer.
- Campaign material to review.
- Suppression rules or instruction to use shared baseline suppressions.

## Core Workflow
1. Identify material reviewed: brief, offer, segment, SMS copy, localisation, journey, or full package.
2. Apply shared principles and read relevant prior outputs.
3. List confirmed facts, assumptions, and missing review-critical items.
4. Review mandatory suppressions.
5. Review RG, compliance, segment, offer, copy/claims, [T&CS], channel, localisation, commercial, operational, brand, and UX risks.
6. Assign verdict and risk level.
7. List blocking fixes, safer rewrites, required approvals, final recommendation, and next skills.

## Verdict Logic
Use exactly one:
- Pass: no major risks; suppressions, channel eligibility, [T&CS], claims, and critical inputs are clear.
- Needs Revision: fixable copy, offer, targeting, [T&CS], channel, localisation, or clarity issues.
- Requires Specialist Review: legal, compliance, RG, risk, trading, product, BI, VIP, or market-owner interpretation is needed.
- Do Not Launch: campaign targets self-excluded/RG-risk/cooling-off users, encourages chasing losses, is based on recent heavy losses, uses guaranteed-win claims, materially misleads, omits key [T&CS], or has critical compliance blockers.

## Core Decision Logic
- If [REGULATORY_NOTES], [T&CS], opt-in, self-exclusion, RG-risk, cooling-off, or suppression handling is missing, Pass is not allowed.
- If self-excluded, active RG-restricted, or cooling-off users are targeted, verdict must be Do Not Launch.
- If recently heavy-losing users are targeted with incentives, verdict should be Do Not Launch or Requires Specialist Review.
- If copy encourages chasing losses, verdict must be Do Not Launch until rewritten.
- If copy references losses, debt, recovery, financial pressure, guaranteed win, or unapproved risk-free/free-money claims, require revision or do not launch.
- If [T&CS_LINK] or material restrictions are missing, verdict cannot be Pass.
- If offer exposure is uncapped, require cap or revision.
- If [TARGET_CHANNEL] is SMS and terms are too complex, require simplification or support surface.
- If VIP, deposit/reload, reactivation, reminder, or high-value incentive logic exists, require stronger review.
- If critical unknowns remain, use Needs Revision or Requires Specialist Review.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, plus segmentation/market/event/journey outputs where relevant.
- Normally after: `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Market-Agnostic Rules
Do not assume local laws, opt-in rules, approval requirements, language, legal wording, sport preferences, payment methods, operator conventions, regulators, or cultural tone.

## Responsible-Gaming Guardrails
Reject or require revision for chasing-losses, recent-loss triggers, financial-solution framing, shame/guilt, excessive urgency, excessive betting frequency, excessive accumulator complexity, vulnerable targeting, unsafe VIP personalisation, or continued contact after opt-out/RG flag/self-exclusion/cooling-off.

## Compliance Guardrails
Flag missing [REGULATORY_NOTES], [T&CS], [T&CS_LINK], opt-in, opt-out text where required, eligibility, expiry, account restrictions, approved/forbidden terms, and approval workflow. Do not claim compliance unless supplied inputs support it.

## Commercial Guardrails
Flag open exposure, missing caps, bonus abuse, sharp/arb exposure, low incrementality, VIP over-costing, unsupported product availability, settlement complexity, support burden, and overly broad eligibility.

## Brand/UX Guardrails
Flag spammy tone, confusing mechanics, jargon, hidden conditions, unclear CTA, invasive personalisation, stereotypes, [BRAND_TONE] mismatch, and certainty-of-winning implications.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# RG & Compliance Review Output

## 1. Review Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Material reviewed:

## 2. Review Verdict
- Verdict: Pass / Needs Revision / Requires Specialist Review / Do Not Launch
- Overall risk level: Low / Medium / High / Critical
- Reason:

## 3. Confirmed Inputs
- [CONFIRMED]

## 4. Working Assumptions
- [ASSUMPTION]

## 5. Needs Confirmation
- [NEEDS CONFIRMATION]

## 6. Responsible-Gaming Review
- Self-exclusion:
- RG-risk suppression:
- Cooling-off:
- Heavy-loss targeting:
- Loss-chasing language:
- Financial pressure:
- Urgency pressure:
- Reactivation sensitivity:
- Personalisation:
- Verdict:

## 7. Compliance and Suppression Review
- [REGULATORY_NOTES]:
- Opt-in:
- Opt-out:
- [T&CS] / [T&CS_LINK]:
- Eligibility:
- Required approvals:
- Verdict:

## 8. Offer, Copy, T&C, Channel, and Localisation Review
- Offer suitability:
- Qualification/reward clarity:
- Exposure cap:
- Claims risk:
- CTA clarity:
- T&C visibility:
- SMS length/complexity if applicable:
- Meaning preservation:
- Verdict:

## 9. Commercial and Operational Review
- Bonus cost:
- Abuse risk:
- Sharp/arb risk:
- Low incrementality:
- VIP cost:
- Audience build:
- Offer setup:
- Tracking:
- QA:
- Verdict:

## 10. Required Fixes
| Issue | Risk type | Required fix | Owner | Blocking status |
|---|---|---|---|---|
|  |  |  |  |  |

## 11. Safer Rewrites
- Risky wording:
- Risk:
- Safer rewrite:
- Why safer:

## 12. Required Approvals
- Compliance:
- Legal:
- Responsible gaming:
- Risk/trading:
- BI:
- Product:
- VIP owner:
- Market owner:

## 13. Final Recommendation
- Approved for next step / Revise and resubmit / Send to specialist review / Do not launch:
- Rationale:

## 14. Recommended Next Skills
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-player-segmentation
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing
- crm-sportsbook-post-campaign-analysis
```

## Recommended Next Skills
Route fixes back to the skill that produced the risky item. Proceed to journey builder or A/B testing only after blocking fixes are resolved.
