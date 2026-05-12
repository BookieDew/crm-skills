---
name: crm-sportsbook-localisation
description: Adapts sportsbook CRM campaign logic and copy to runtime-supplied target market, target language, brand tone, local style, and regulatory notes while flagging uncertain localisation points.
---

# CRM Sportsbook Localisation

## Purpose

Adapt campaign logic and copy to `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[BRAND_TONE]`, runtime local style, and `[REGULATORY_NOTES]` without inventing local cultural, regulatory, language, event, or product facts.

## Role in the Skill Pack

This skill runs after market context and campaign brief or SMS copy. It refines language, tone, clarity, local fit, and compliance-sensitive wording before RG/compliance review.

## When to Use

- A campaign must be adapted to `[TARGET_LANGUAGE]`.
- A user supplies local style, terms, or regulation notes.
- SMS copy needs market-specific review.
- The CRM manager asks for localisation guidance.
- The campaign uses event, sport, offer, or CTA language that may not travel cleanly.

## When Not to Use

- Do not invent local culture, language conventions, regulation, sports preferences, or current events.
- Do not translate into a named language unless `[TARGET_LANGUAGE]` is supplied.
- Do not finalise legal approval; use `crm-sportsbook-rg-compliance-review`.
- Do not write non-SMS channel copy; future channel-specific skills should do that.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- Text or campaign logic to localise.

### Recommended inputs

- `[BRAND_TONE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[TARGET_EVENT]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- `[T&CS]`
- `[REGULATORY_NOTES]`
- Runtime local style notes.

### Advanced optional inputs

- Approved terminology.
- Prohibited terminology.
- Local tone examples supplied by the user.
- Character limits.
- Compliance disclaimers supplied at runtime.
- Local date, time, currency, or number formatting rules supplied at runtime.

## Output

This skill produces localisation guidance, adapted copy or copy notes, confirmed inputs, assumptions, uncertain points, risks, and recommendations for compliance review.

## Workflow

1. Load `crm-sportsbook-shared-principles` and market context.
2. Confirm `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, `[BRAND_TONE]`, `[T&CS]`, and `[REGULATORY_NOTES]`.
3. Preserve the approved offer value, mechanics, constraints, and RG guardrails.
4. Adapt tone and wording only using runtime-supplied style rules.
5. Mark uncertain localisation points `[NEEDS CONFIRMATION]`.
6. Flag words, claims, idioms, urgency, or unclear terms that could create risk.
7. Provide a revised version or localisation notes.
8. Route to RG/compliance review before launch.

## Decision Logic

- If `[TARGET_LANGUAGE]` is missing, do not localise text; request it.
- If local style guidance is missing, produce neutral copy and label tone assumptions.
- If regulation notes are missing, preserve baseline RG rules and mark local compliance `[NEEDS CONFIRMATION]`.
- If SMS copy gets longer or harder to understand, prioritise clarity over stylistic nuance.
- If a phrase relies on cultural knowledge not supplied by the user, remove it or mark it `[NEEDS CONFIRMATION]`.
- If terms or opt-out wording are required but missing, do not finalise.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-campaign-brief`, optionally `crm-sportsbook-sms-copy`.
- Skills that should normally run after this one: `crm-sportsbook-sms-copy` if localised copy is still needed, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel principles, and measurement principles.

## Sportsbook-Specific Considerations

Localisation must preserve sport preference accuracy, event relevance, bet type clarity, pre-match versus live distinction, single versus accumulator wording, odds boost suitability, free bet suitability, cashback suitability, bet builder clarity, deposit behaviour sensitivity, bonus history relevance, bonus sensitivity, VIP tone, recreational versus sharp behaviour risk, arb-sensitive exclusions, churn-risk care, stake-level fit, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market. Do not hardcode country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If market-specific localisation knowledge is needed, ask for it, label it `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt localisation to `[TARGET_CHANNEL]`.

For SMS:

- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.
- Preserve character-count discipline after localisation.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules even if local notes are minimal. Do not localise into stronger urgency, emotional pressure, chasing-loss language, financial-solution claims, guaranteed-win claims, misleading risk-free claims unless approved, hidden T&Cs, or manipulative win-back wording.

## Commercial Guardrails

Do not localise in a way that expands `[OFFER_VALUE]`, removes caps, removes minimum odds, removes minimum stake, removes max bonus value, broadens eligible markets, hides expiry, or weakens objective fit.

## Brand & UX Guardrails

Be direct, clear, and aligned with `[BRAND_TONE]`. Avoid jargon, misleading terms, fake personalisation, stereotypes, and certainty-of-winning claims. Do not use idioms or cultural references unless supplied and approved at runtime.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Localisation Review

### Confirmed Runtime Inputs
- [CONFIRMED] [TARGET_MARKET]:
- [CONFIRMED] [TARGET_LANGUAGE]:
- [CONFIRMED] [BRAND_TONE]:

### Localised Version or Guidance
- Copy:
- Notes:

### Localisation Risks
- [RISK]

### Needs Confirmation
- [NEEDS CONFIRMATION]

### Recommendations
- [RECOMMENDATION]
```

## Example User Request

Localise this SMS for `[TARGET_MARKET]` in `[TARGET_LANGUAGE]` using `[BRAND_TONE]`: `[SMS_COPY]`. The offer is `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`; `[T&CS]` apply.

## Example Output

```markdown
## Localisation Review

- [CONFIRMED] Market: [TARGET_MARKET]
- [CONFIRMED] Language: [TARGET_LANGUAGE]
- [RECOMMENDATION] Keep the SMS direct and preserve `[OFFER_VALUE]`, `[OFFER_MECHANIC]`, CTA, and `[T&CS]` reference.
- [NEEDS CONFIRMATION] Local opt-out wording, approved terminology, and any required `[REGULATORY_NOTES]`.
- [RISK] Do not add idioms, urgency, or cultural claims not supplied at runtime.
```

