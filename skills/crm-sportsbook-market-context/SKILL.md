---
name: crm-sportsbook-market-context
description: Analyses runtime-supplied sportsbook CRM market context while separating confirmed inputs, assumptions, needs confirmation, risks, and recommendations without hardcoding market facts.
---

# CRM Sportsbook Market Context

## Purpose

Structure the runtime market context for sportsbook CRM work. This skill captures what is known, what is missing, what is risky, and what must be confirmed before campaign, offer, copy, journey, localisation, or analysis work proceeds.

## Role in the Skill Pack

This skill runs after `crm-sportsbook-shared-principles` and before event, segmentation, offer, campaign brief, localisation, and compliance work.

## When to Use

- A target market is named at runtime.
- A campaign needs local terms, language, style, channel, timing, or regulatory input.
- The user gives partial market notes and wants them structured.
- The AI needs to distinguish confirmed market facts from assumptions.
- Localisation or compliance review needs runtime market context.

## When Not to Use

- Do not use this skill to generate campaign copy; use `crm-sportsbook-sms-copy` for SMS.
- Do not use this skill to invent fixtures, regulations, payment methods, or cultural facts.
- Do not use this skill as final compliance sign-off; use `crm-sportsbook-rg-compliance-review`.
- Do not use this skill to select offers alone; use `crm-sportsbook-offer-mechanics`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- Campaign objective or intended use.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- `[T&CS]`
- Local calendar details supplied by the user.
- Product availability supplied by the user.

### Advanced optional inputs

- Channel consent rules.
- Local style guide supplied at runtime.
- Approved claims list.
- Prohibited terms list.
- Bonus policy.
- Frequency caps.
- Market-specific suppression rules supplied by the user.

## Output

This skill produces a market-context brief with confirmed runtime inputs, assumptions, needs confirmation, risks, recommendations, and implications for event selection, segmentation, offers, copy, localisation, and compliance review.

## Workflow

1. Load `crm-sportsbook-shared-principles`.
2. Capture every supplied market detail as `[CONFIRMED]`.
3. Identify missing market, language, channel, regulatory, terms, consent, and product details.
4. Mark missing details `[NEEDS CONFIRMATION]`.
5. If a pragmatic interim assumption is unavoidable, label it `[ASSUMPTION]`.
6. Identify RG, compliance, commercial, brand, and UX risks.
7. Recommend how downstream skills should use or avoid the market details.
8. State whether research is required if current or local facts are needed and tools are available.

## Decision Logic

- If `[TARGET_MARKET]` is not supplied, do not produce market-specific recommendations.
- If `[TARGET_LANGUAGE]` is missing, provide structure only and mark copy or localisation `[NEEDS CONFIRMATION]`.
- If `[REGULATORY_NOTES]` are missing, use baseline RG rules and mark local compliance `[NEEDS CONFIRMATION]`.
- If `[T&CS]` are missing, do not finalise offer copy.
- If local event timing is missing, do not invent fixtures or calendar moments.
- If product availability is unclear, avoid recommending mechanics that depend on unavailable bet types.
- If channel consent or eligibility is unclear, mark launch readiness `[RISK]`.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`.
- Skills that should normally run after this one: `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline, suppression rules, commercial protection, channel communication principles, and measurement principles.

## Sportsbook-Specific Considerations

Capture runtime information relevant to sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market. Never hardcode country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If market-specific knowledge is needed, ask for the missing detail, label an interim point `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt market context to `[TARGET_CHANNEL]`.

For SMS:

- Confirm whether SMS consent and frequency caps are supplied.
- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push are future channel-specific skills and must not be blended into SMS guidance.

## Responsible Gaming & Compliance Guardrails

Apply baseline responsible-gaming rules even if the user says the market has no strict rules. Flag any missing suppression or local compliance input as `[RISK]` or `[NEEDS CONFIRMATION]`.

Avoid targeting self-excluded users, RG risk users, users selected due to recent heavy losses, or users with no valid channel eligibility. Avoid chasing-loss language, financial-solution claims, guaranteed-win language, misleading risk-free claims unless approved, aggressive urgency, hidden T&Cs, emotional pressure, and manipulative win-back language.

## Commercial Guardrails

Protect margin and bonus cost by identifying market-supplied constraints on offer value, minimum odds, minimum stake, maximum bonus value, eligible markets, expiry, and objective fit. If constraints are absent, mark them `[NEEDS CONFIRMATION]`.

## Brand & UX Guardrails

Ensure market context supports clear communication: direct wording, no jargon, obvious next action, no misleading terms, no fake personalisation, no stereotypes, and no implication of certain winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Market Context Brief

### Confirmed
- [CONFIRMED] [TARGET_MARKET]:
- [CONFIRMED] [TARGET_LANGUAGE]:
- [CONFIRMED] [TARGET_CHANNEL]:

### Assumptions
- [ASSUMPTION]

### Needs Confirmation
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]:
- [NEEDS CONFIRMATION] [T&CS]:
- [NEEDS CONFIRMATION] Channel eligibility:

### Risks
- [RISK] RG:
- [RISK] Compliance:
- [RISK] Commercial:

### Recommendations
- [RECOMMENDATION] Downstream skill guidance:
```

## Example User Request

Use `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, `[BRAND_TONE]`, and `[REGULATORY_NOTES]` to prepare context for a sportsbook CRM campaign.

## Example Output

```markdown
## Market Context Brief

- [CONFIRMED] Market: [TARGET_MARKET]
- [CONFIRMED] Language: [TARGET_LANGUAGE]
- [CONFIRMED] Channel: [TARGET_CHANNEL]
- [NEEDS CONFIRMATION] Approved [T&CS] for [OFFER_MECHANIC].
- [RISK] Local compliance detail is incomplete until [REGULATORY_NOTES] are supplied.
- [RECOMMENDATION] Proceed with generic sportsbook structure only; final copy and offer terms require confirmation.
```

