---
name: crm-sportsbook-market-context
description: Light execution version for structuring runtime market, language, channel, regulatory, brand, and operational context without inventing market facts.
---

# CRM Sportsbook Market Context Light

## Purpose
Create the market-context layer for sportsbook CRM planning using runtime inputs only. This skill clarifies what is confirmed, assumed, missing, risky, and ready to feed downstream skills.

## Role in the Skill Pack
Run early after shared principles and router when market, language, channel, regulatory, brand, or operational context affects event, segment, offer, copy, localisation, or RG review decisions.

## When to Use
Use for planning in [TARGET_MARKET], preparing localisation, checking missing regulatory notes, assessing channel suitability, or identifying market-context questions before campaign design.

## When Not to Use
Do not use for final SMS copy, offer design, full campaign brief, legal terms, final approval, or post-campaign analysis. Route to specialist skills.

## Minimum Required Inputs
- [TARGET_MARKET]
- [CAMPAIGN_OBJECTIVE], if known.

## Core Workflow
1. Apply shared principles.
2. List confirmed runtime inputs.
3. Mark missing [TARGET_LANGUAGE], [TARGET_CHANNEL], [TARGET_SEGMENT], [TARGET_SPORT], [TARGET_EVENT], [BRAND_TONE], [REGULATORY_NOTES], [T&CS], and [T&CS_LINK].
4. Do not invent local facts. Use supplied data or mark [NEEDS CONFIRMATION].
5. Identify CRM implications for sport/event relevance, segment fit, offer complexity, channel use, localisation, RG, compliance, commercial exposure, and measurement.
6. Recommend the next skill chain.

## Core Decision Logic
- If [TARGET_MARKET] is missing, mark [NEEDS CONFIRMATION].
- If [TARGET_LANGUAGE] is missing, do not assume it.
- If [TARGET_CHANNEL] is missing, give neutral channel considerations.
- If [TARGET_SPORT] or [TARGET_EVENT] is missing, recommend event opportunity if event-led planning is needed.
- If [REGULATORY_NOTES] are missing, do not claim compliance.
- If suppression, opt-in, cooling-off, or RG handling is unclear, route to RG/compliance review.
- If [TARGET_CHANNEL] is SMS, prefer simple mechanics and clear [T&CS_LINK] handling downstream.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router`.
- Normally after: `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-localisation`, `crm-sportsbook-sms-copy`, `crm-sportsbook-rg-compliance-review`.

## Market-Agnostic Rules
Do not assume local laws, language, sports preferences, channel habits, payment methods, holidays, operators, regulators, slang, or cultural behaviour. Examples must use placeholders only.

## Responsible-Gaming Guardrails
Flag missing self-exclusion, RG-risk suppression, cooling-off, opt-in, account restriction, [T&CS], and [REGULATORY_NOTES] handling. Never recommend targeting restricted or vulnerable users.

## Commercial Guardrails
Identify possible bonus cost, margin, bonus abuse, VIP, sharp, arb-sensitive, opt-out, and low-incrementality risks. Do not estimate numbers without supplied data.

## Brand/UX Guardrails
Flag unclear tone, complex mechanics, invasive personalisation, missing [T&CS_LINK], or channel mismatch. Do not stereotype [TARGET_MARKET].

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Market Context Output

## 1. Target Market
- Market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Sportsbook CRM Implications
- Sport/event relevance:
- Segment implications:
- Offer implications:
- Channel implications:
- Timing implications:

## 6. Localisation and Brand Considerations
- [TARGET_LANGUAGE]:
- [BRAND_TONE]:

## 7. RG, Compliance, and Commercial Considerations
- [REGULATORY_NOTES]:
- [T&CS] / [T&CS_LINK]:
- [RISK]
- [RECOMMENDATION]

## 8. Recommended Next Skills
- crm-sportsbook-event-opportunity
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 9. Launch Readiness
- Ready to proceed with assumptions / Needs confirmation before campaign design / Needs compliance/RG input before campaign design
```

## Recommended Next Skills
Use event opportunity for event-led planning, segmentation for audience logic, offer mechanics for incentive design, campaign brief for synthesis, localisation for language/tone, SMS copy for SMS execution, and RG/compliance review before launch.
