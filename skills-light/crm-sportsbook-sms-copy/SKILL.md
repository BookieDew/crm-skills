---
name: crm-sportsbook-sms-copy
description: Light execution version for creating short, clear, market-agnostic sportsbook SMS copy variants with character counts, T&C handling, RG safeguards, commercial notes, localisation readiness, and A/B test suggestions.
---

# CRM Sportsbook SMS Copy Light

## Purpose
Create SMS-specific sportsbook CRM copy variants that are short, clear, responsible-gaming-aware, commercially accurate, and ready for localisation and RG/compliance review.

## Role in the Skill Pack
This is the SMS channel execution skill. It usually runs after campaign brief, offer mechanics, and segmentation. It feeds localisation, RG/compliance review, journey builder, A/B testing, and post-campaign analysis.

## When to Use
Use for SMS variants, SMS rewrites, SMS A/B copy, short event-led copy, activation, retention, reactivation, offer communication, VIP SMS draft where approved, and SMS clarity or compliance review.

## When Not to Use
Do not write full email, push, landing page, or legal [T&CS]. Do not create campaign strategy, select audience from raw data, design complex offers from scratch, provide final approval, translate without localisation review, or invent market/event facts.

## Minimum Required Inputs
- [TARGET_CHANNEL] = SMS.
- [TARGET_MARKET]
- [TARGET_LANGUAGE] or instruction to keep source language.
- [CAMPAIGN_OBJECTIVE]
- [TARGET_SEGMENT]
- [COMMUNICATION_OPT_IN_STATUS] or SMS opt-in confirmation.
- [OFFER_MECHANIC]
- [OFFER_VALUE]
- CTA or action instruction.
- [T&CS_LINK] or [T&CS] handling instruction.

## Core Workflow
1. Confirm [TARGET_CHANNEL] is SMS.
2. Apply shared principles and read campaign brief, offer mechanics, segmentation, market context, and event context if available.
3. Confirm [CAMPAIGN_OBJECTIVE], [TARGET_SEGMENT], SMS opt-in status, [OFFER_MECHANIC], [OFFER_VALUE], CTA, [T&CS_LINK], and key offer constraints.
4. Mark missing copy-critical inputs as [NEEDS CONFIRMATION].
5. Decide whether the mechanic can be explained in SMS.
6. Write distinct SMS variants: value-led, event-led, simple CTA, reactivation-safe, expiry-led, or product-led as appropriate.
7. Provide character count for every variant.
8. Check RG, compliance, commercial clarity, brand/UX, localisation, and A/B test readiness.
9. Recommend next skills.

## Core Decision Logic
- If [TARGET_CHANNEL] is not SMS, do not write non-SMS copy.
- If [TARGET_LANGUAGE], [OFFER_MECHANIC], [TARGET_SEGMENT], SMS opt-in status, [T&CS_LINK], or [T&CS] handling is missing, mark [NEEDS CONFIRMATION].
- If the offer is too complex for SMS, simplify or recommend offer mechanics review.
- Use one message, one offer, one CTA, and visible [T&CS_LINK] or [T&CS] cue.
- Avoid jargon, aggressive urgency, excessive punctuation, unapproved emojis, hidden restrictions, and invasive personalisation.
- Reject or rewrite guaranteed-win, loss-recovery, free-money, unapproved risk-free, financial-pressure, or chasing-losses wording.
- For reactivation, keep tone calm and non-manipulative.
- For VIP, recommend manual review.
- For sharp, arb-sensitive, bonus-sensitive, or abuse-prone audiences, make eligibility and restrictions clear and recommend review.

## SMS Character Count Logic
- Count every visible character, including spaces and punctuation.
- State whether the count includes [T&CS_LINK], brand text, opt-out text, and personalisation tokens if present.
- If placeholders are used, say counts must be recalculated after runtime values, links, opt-out text, and tokens are expanded.
- Flag possible count changes from Unicode, emojis, special punctuation, non-Latin scripts, link replacement, and CRM platform handling.
- Prefer plain punctuation and no emojis unless explicitly approved.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-player-segmentation`, plus market/event context where relevant.
- Normally after: `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Market-Agnostic Rules
Do not assume local language, slang, tone, sport preference, event facts, regulations, operators, payment methods, or cultural behaviour. Examples must use placeholders only.

## Responsible-Gaming Guardrails
SMS must not target self-excluded, RG-risk, cooling-off, opted-out, users without valid SMS opt-in, or relevant heavy-loss users. It must not encourage chasing losses, recover losses, imply certainty, create financial pressure, hide restrictions, or make betting necessary to enjoy [TARGET_EVENT].

## Commercial Guardrails
Flag copy that overstates [OFFER_VALUE], omits important restrictions, weakens qualification, hides expiry, makes abuse easier, attracts sharp/arb exploitation, or creates support burden.

## Brand/UX Guardrails
SMS should be clear, human, scannable, aligned to [BRAND_TONE], not spammy, not stereotyped, not invasive, and easy to act on.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# SMS Copy Output

## 1. SMS Campaign Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target segment: [TARGET_SEGMENT]
- SMS opt-in status: [COMMUNICATION_OPT_IN_STATUS]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- CTA:
- T&Cs: [T&CS_LINK]
- Character limit:

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. SMS Variants
Provide 5-8 variants unless the user requests another number.

| Variant | Copy | Character count | Angle | Best use case | Offer clarity | CTA clarity | T&C handling | Risk notes |
|---|---|---:|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |

## 6. Character Count Notes
- Counts include:
- Counts exclude:
- Recount required after runtime expansion:
- Encoding or platform risks:

## 7. Recommended Variant
- Recommended variant:
- Why:
- RG safety:
- Commercial clarity:
- Channel fit:

## 8. Variants to Avoid or Rewrite
- Risky wording:
- Safer rewrite:

## 9. RG, Compliance, Commercial, and Localisation Notes
- Pressure risk:
- Loss-chasing risk:
- Misleading claim risk:
- [T&CS] risk:
- Abuse/sharp/arb risk:
- Localisation risks:
- Required review:

## 10. A/B Test Suggestion
- Hypothesis:
- Variant A:
- Variant B:
- Primary KPI:
- Guardrail metrics:
- Decision rule:

## 11. Recommended Next Skills
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 12. Launch Readiness
- Ready for localisation and RG/compliance review / Needs missing inputs / Needs offer simplification / Needs T&C confirmation / Not recommended:
- Rationale:
```

## Recommended Next Skills
Always route final SMS through localisation where needed and RG/compliance review before launch. Use journey builder for sends and A/B testing for variant measurement.
