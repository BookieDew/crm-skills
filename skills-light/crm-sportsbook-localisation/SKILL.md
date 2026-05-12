---
name: crm-sportsbook-localisation
description: Light execution version for adapting supplied sportsbook CRM campaign logic and copy to runtime-supplied market, language, channel, brand tone, approved terms, forbidden terms, and regulatory notes without inventing local facts.
---

# CRM Sportsbook Localisation Light

## Purpose
Localise or review supplied sportsbook CRM material for [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], [BRAND_TONE], offer clarity, [T&CS] handling, RG-safe language, and commercial accuracy.

## Role in the Skill Pack
Run after campaign brief, SMS copy, offer mechanics, and market context when copy or campaign logic needs target-language or tone adaptation. Feed RG/compliance review, journey builder, A/B testing, and analysis.

## When to Use
Use for localisation review, target-language adaptation, tone adaptation, SMS localisation, offer wording clarity, [T&CS_LINK] cue review, personalisation review, native-language QA preparation, and localisation-sensitive A/B test ideas.

## When Not to Use
Do not invent local language rules, slang, cultural behaviour, sports preferences, regulations, legal wording, market facts, or product terminology. Do not replace legal, compliance, RG, native-speaker QA, channel-specific copy skills, or full campaign strategy.

## Minimum Required Inputs
- [TARGET_MARKET]
- [TARGET_LANGUAGE]
- [TARGET_CHANNEL]
- Source copy or campaign material.
- [CAMPAIGN_OBJECTIVE]
- [OFFER_MECHANIC] and [OFFER_VALUE], if offer copy is involved.
- [BRAND_TONE] or instruction to preserve existing tone.

## Core Workflow
1. Apply shared principles and read source campaign/copy outputs.
2. Identify [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], source material, [BRAND_TONE], [OFFER_MECHANIC], [OFFER_VALUE], [T&CS], and [T&CS_LINK].
3. Separate confirmed localisation notes, approved terms, forbidden terms, and [REGULATORY_NOTES] from assumptions.
4. Choose mode: literal translation, adaptive localisation, clarity simplification, SMS localisation, RG-safe rewrite, or brand-tone adaptation.
5. Preserve offer meaning, eligibility, reward type, restrictions, [T&CS_LINK], and CTA meaning.
6. Do not add local facts, slang, humour, cultural references, or compliance claims unless supplied.
7. Provide localised variants and character counts if [TARGET_CHANNEL] is SMS.
8. Flag native-speaker, compliance, RG, and offer-term review needs.

## Core Decision Logic
- If [TARGET_LANGUAGE], [TARGET_MARKET], source copy, or [TARGET_CHANNEL] is missing, mark [NEEDS CONFIRMATION].
- If [TARGET_CHANNEL] is SMS, keep copy short and provide character counts.
- If local tone is unknown, use neutral clear wording and mark [NEEDS CONFIRMATION].
- If approved terms are supplied, use them. If forbidden terms are supplied, avoid them and flag source conflicts.
- If source copy has pressure, loss references, financial-pressure framing, guaranteed claims, unapproved risk-free/free-money wording, or hidden restrictions, rewrite safely.
- If translation changes offer meaning, mark [RISK] and require review.
- If language quality is uncertain, recommend native-speaker QA.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy` for SMS, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-market-context`, plus event/segmentation outputs where relevant.
- Normally after: `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.

## Market-Agnostic Rules
Do not assume local language norms, slang, dialect, sport preferences, betting habits, local legal wording, payment terminology, operator conventions, or cultural tone. Examples must use placeholders only.

## Responsible-Gaming Guardrails
Remove or flag chasing-losses, recent-loss, financial-pressure, guaranteed-profit, unapproved risk-free/free-money, excessive urgency, manipulative reactivation, hidden restriction, invasive personalisation, and excessive-play wording.

## Commercial Guardrails
Do not weaken or change [OFFER_VALUE], qualification, reward type, eligibility, caps, expiry, usage limits, [T&CS], or [T&CS_LINK]. Flag ambiguity that may create abuse, support burden, or broadening of eligibility.

## Brand/UX Guardrails
Localisation must be clear, human, consistent with [BRAND_TONE], non-spammy, not stereotyped, not slang-heavy unless supplied, not jargon-heavy, and easy to act on.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# Localisation Output

## 1. Localisation Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Brand tone: [BRAND_TONE]

## 2. Source Copy / Source Material
- Source copy:

## 3. Confirmed Inputs
- [CONFIRMED]

## 4. Working Assumptions
- [ASSUMPTION]

## 5. Needs Confirmation
- [NEEDS CONFIRMATION]

## 6. Localisation Strategy
- Mode:
- Reason:
- Supplied localisation notes:
- Approved terms:
- Forbidden terms:

## 7. Localised Copy Variants
Provide 3-6 variants unless the user requests another number.

| Variant | Localised copy | Character count if SMS | Approach | Offer clarity | CTA clarity | T&C handling | Tone notes | Risk notes |
|---|---|---:|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |

## 8. Recommended Variant
- Recommended:
- Clarity:
- Naturalness:
- Channel fit:
- Brand fit:
- RG safety:
- Commercial clarity:

## 9. Review Notes
- Meaning preserved:
- Phrasing adapted:
- Native-speaker QA:
- [T&CS] clarity:
- Personalisation risk:
- Encoding/character-count risk:

## 10. A/B Test Suggestion
- Hypothesis:
- Variant A:
- Variant B:
- Primary KPI:
- Guardrail metrics:
- Decision rule:

## 11. Recommended Next Skills
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing
- crm-sportsbook-post-campaign-analysis

## 12. Launch Readiness
- Ready for RG/compliance review / Needs native-language QA / Needs missing inputs / Needs offer clarification / Needs T&C confirmation / Not recommended:
- Rationale:
```

## Recommended Next Skills
Proceed to RG/compliance review before launch. Use journey builder for execution and A/B testing if comparing localised variants.
