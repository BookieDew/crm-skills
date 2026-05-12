---
name: crm-sportsbook-market-context
description: Builds market context for market-agnostic sportsbook CRM campaigns using runtime inputs only. Separates confirmed facts, assumptions, needs confirmation, risks, and recommendations before event, segment, offer, copy, localisation, and compliance work.
---

# CRM Sportsbook Market Context

## Purpose

This skill helps sportsbook CRM teams build market context before creating sportsbook CRM campaigns.

It helps the CRM team understand what must be known about `[TARGET_MARKET]` before selecting events, segments, offers, channels, copy, and localisation approach.

This skill does not create full campaign outputs. It creates the market context layer that other skills use.

## Role in the Skill Pack

This skill should normally run early in the campaign process, after `crm-sportsbook-shared-principles` and when routed by `crm-sportsbook-skill-router`.

It provides market context that informs:

- Event opportunity selection.
- Player segmentation.
- Offer mechanics.
- Campaign brief.
- Localisation.
- SMS copy.
- RG/compliance review.

It should not create full campaigns by itself. It should feed structured, labelled market context into:

- `crm-sportsbook-event-opportunity`
- `crm-sportsbook-player-segmentation`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-localisation`
- `crm-sportsbook-sms-copy`
- `crm-sportsbook-rg-compliance-review`

## When to Use

Use this skill when the CRM manager needs to:

- Plan a campaign for `[TARGET_MARKET]`.
- Enter or assess a new market.
- Understand market-specific assumptions.
- Choose relevant sports or events.
- Decide whether SMS, email, push, inbox, or another channel may be suitable.
- Adapt campaign tone.
- Prepare localisation guidance.
- Check whether local regulatory or responsible-gaming notes are missing.
- Identify what must be confirmed before campaign launch.

## When Not to Use

Do not use this skill to:

- Write final customer-facing SMS copy.
- Design the full offer mechanic.
- Build the full campaign brief.
- Analyse post-campaign performance.
- Draft legal terms and conditions.
- Make unsupported claims about a specific market.

Route those requests to the appropriate skills:

- SMS copy: `crm-sportsbook-sms-copy`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- Post-campaign analysis: `crm-sportsbook-post-campaign-analysis`.
- Legal, RG, or launch risk review: `crm-sportsbook-rg-compliance-review`.
- Routing uncertainty: `crm-sportsbook-skill-router`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[CAMPAIGN_OBJECTIVE]` if known.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_SEGMENT]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`

### Advanced optional inputs

- Internal market research.
- Local sports calendar.
- Local event calendar.
- Competitor campaign examples.
- Channel engagement data.
- Device usage data.
- Deposit or payment behaviour.
- Historical campaign performance.
- Local compliance notes.
- Local responsible-gaming requirements.
- Customer segment data.
- Brand localisation guidelines.

## Output

The skill should produce:

- Market context summary.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Market-specific CRM implications.
- Sport/event relevance considerations.
- Channel considerations.
- Localisation considerations.
- Compliance and RG uncertainty notes.
- Risks.
- Recommended next skills.

## Workflow

1. Identify `[TARGET_MARKET]` from the user's runtime input.
2. Load and apply `crm-sportsbook-shared-principles`.
3. If the request is ambiguous, use `crm-sportsbook-skill-router` routing logic to confirm this is the correct skill.
4. List all user-provided facts as `[CONFIRMED]`.
5. Separate confirmed facts from assumptions.
6. Identify missing market-specific information.
7. Mark important unknowns as `[NEEDS CONFIRMATION]`.
8. If the user provided market research, summarise it without overextending it.
9. If no market research is provided, do not invent hard facts.
10. Consider sportsbook CRM implications for:
    - Sport relevance.
    - Event relevance.
    - Channel suitability.
    - Language and tone.
    - Offer complexity.
    - Deposit or payment behaviour if provided.
    - Regulatory uncertainty.
    - Responsible-gaming considerations.
11. Recommend what the CRM team should confirm before launch.
12. Recommend the next skill or skill chain.

## Decision Logic

Apply these rules:

- If `[TARGET_MARKET]` is missing, ask for it or mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_LANGUAGE]` is missing, do not assume it. Mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is missing, provide neutral channel considerations rather than choosing one without context.
- If `[TARGET_SPORT]` or `[TARGET_EVENT]` is missing, recommend using `crm-sportsbook-event-opportunity` next.
- If local regulation is unknown, mark it as `[NEEDS CONFIRMATION]` and do not make compliance claims.
- If local sport preference is unknown, do not invent it. Suggest confirming with internal betting data or market research.
- If channel behaviour is unknown, suggest validating with internal delivery, engagement, and conversion data.
- If localisation tone is unknown, recommend using `crm-sportsbook-localisation`.
- If `[CAMPAIGN_OBJECTIVE]` is known, tailor the market implications to that objective.
- If `[CAMPAIGN_OBJECTIVE]` is unknown, provide general market-context questions and recommend clarifying the objective.
- If responsible-gaming, opt-in, cooling-off, or suppression handling is unclear, route to `crm-sportsbook-rg-compliance-review`.
- If the target channel is SMS, route downstream output through `crm-sportsbook-sms-copy` after campaign and offer logic are defined.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, and `crm-sportsbook-skill-router` when the user request is broad or ambiguous.
- Normally run after this skill: `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-localisation`, `crm-sportsbook-sms-copy`, and `crm-sportsbook-rg-compliance-review`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, channel communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Popular sports in `[TARGET_MARKET]`, if provided or researched.
- Relevant leagues or tournaments, if provided or researched.
- Local event timing.
- Pre-match vs live betting behaviour.
- Single bet vs accumulator preference.
- Bonus sensitivity.
- Average stake and deposit behaviour.
- VIP or high-value segment relevance.
- Recreational vs sharp behaviour.
- Channel engagement by segment.
- Risk of bonus abuse.
- Offer simplicity by channel.
- Margin protection.
- Local restrictions on offer wording, if provided.
- Local customer expectations around promotions, if provided.

## Market-Agnostic Design Rules

The skill must never assume:

- Country-specific laws.
- Local language.
- Local betting preferences.
- Local payment methods.
- Local sports popularity.
- Local leagues.
- Local operators.
- Local holidays.
- Local cultural behaviour.
- Local regulatory restrictions.

All market-specific details must come from:

- User-provided inputs.
- Internal documents.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts.

## Channel-Aware Design Rules

The skill should consider `[TARGET_CHANNEL]` if supplied.

For SMS:

- Recommend simple campaign mechanics.
- Recommend short and direct messaging.
- Flag complex mechanics as possible UX risk.
- Recommend clear CTA.
- Recommend accessible terms and conditions.
- Avoid assuming SMS is best unless supported by user input or data.

For email:

- Note that detailed email copy should be handled by a future email-specific skill.
- Use this skill only to flag market context, tone, term visibility, and channel suitability questions.

For push:

- Note that detailed push copy should be handled by a future push-specific skill.
- Use this skill only to flag market context, brevity, opt-in, and timing questions.

For inbox or onsite messaging:

- Consider whether the campaign needs more persistent, reviewable information than an outbound message.
- Confirm whether terms, eligibility, and offer status can be made visible.

For VIP outreach:

- Recommend careful personalisation and stronger RG/compliance checks.
- Confirm that personalisation is based on appropriate, confirmed customer context.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag if the market context is missing:

- Self-exclusion handling.
- RG-risk suppression rules.
- Channel opt-in requirements.
- Cooling-off rules.
- Promotional restrictions.
- Terms and conditions requirements.
- Age or identity verification requirements, where relevant.
- Local restrictions on bonus wording, where relevant.

The skill must never recommend campaigns that:

- Target self-excluded users.
- Target users with RG risk flags.
- Encourage chasing losses.
- Use financial pressure.
- Use misleading winning claims.
- Hide restrictions.
- Use aggressive urgency aimed at vulnerable users.

If any of these issues are present or cannot be checked, mark them `[RISK]` or `[NEEDS CONFIRMATION]` and recommend `crm-sportsbook-rg-compliance-review`.

## Commercial Guardrails

The skill should identify market-context factors that could affect:

- Bonus cost.
- Margin exposure.
- Bonus abuse risk.
- Segment size.
- Offer affordability.
- Deposit conversion.
- Bet conversion.
- Expected incremental value.
- Channel cost.
- Opt-out risk.
- VIP handling.
- Sharp or arb-sensitive exposure.

Do not estimate numbers unless the user provides data or explicitly asks for assumptions.

## Brand & UX Guardrails

The skill should help the CRM team understand:

- Whether the campaign tone needs localisation.
- Whether the offer can be explained clearly in `[TARGET_CHANNEL]`.
- Whether the campaign mechanic may be too complex.
- Whether the wording may feel too aggressive.
- Whether personalisation may feel invasive.
- Whether terms and conditions are likely to be too heavy for the selected channel.

Do not stereotype `[TARGET_MARKET]`. Do not claim customer expectations, language style, cultural fit, or promotion norms unless the user provides that context or it is confirmed through research.

## Assumption Labels

Use these labels consistently:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked before launch.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

Use this response format when the skill is activated:

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

## 6. Channel Considerations
- [TARGET_CHANNEL]:

## 7. Localisation Considerations
- [TARGET_LANGUAGE]:
- [BRAND_TONE]:

## 8. Compliance & RG Considerations
- [REGULATORY_NOTES]:
- [RISK]

## 9. Commercial Considerations
- [RISK]
- [RECOMMENDATION]

## 10. Recommended Next Skills
- crm-sportsbook-event-opportunity
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 11. Launch Readiness
- Ready to proceed with assumptions / Needs confirmation before campaign design / Needs compliance/RG input before campaign design
```

## Example User Request

"Create market context for a sportsbook campaign in `[TARGET_MARKET]`. The campaign objective is `[CAMPAIGN_OBJECTIVE]`, the channel is `[TARGET_CHANNEL]`, and the target segment is `[TARGET_SEGMENT]`."

## Example Output

```markdown
# Market Context Output

## 1. Target Market
- Market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Target segment: [TARGET_SEGMENT]

## 3. Working Assumptions
- [ASSUMPTION] No local sport preference is assumed until internal betting data, market research, or confirmed research is provided.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_EVENT]
- [NEEDS CONFIRMATION] [BRAND_TONE]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]
- [NEEDS CONFIRMATION] Channel opt-in, self-exclusion handling, RG-risk suppression, cooling-off handling, and terms and conditions requirements.

## 5. Sportsbook CRM Implications
- Sport/event relevance: [NEEDS CONFIRMATION] Use `crm-sportsbook-event-opportunity` to assess [TARGET_SPORT] and [TARGET_EVENT] once runtime data is supplied.
- Segment implications: [RECOMMENDATION] Use `crm-sportsbook-player-segmentation` to validate [TARGET_SEGMENT], channel eligibility, RG exclusions, value bands, bonus sensitivity, and churn risk.
- Offer implications: [RECOMMENDATION] Use `crm-sportsbook-offer-mechanics` after segment and event context are confirmed.
- Channel implications: [RECOMMENDATION] Validate whether [TARGET_CHANNEL] has enough engagement and conversion evidence for [TARGET_SEGMENT].
- Timing implications: [NEEDS CONFIRMATION] Confirm event timing, campaign window, expiry, and frequency-cap rules.

## 6. Channel Considerations
- [TARGET_CHANNEL]: [RECOMMENDATION] Keep the campaign mechanic simple if the selected channel has limited space or fast interaction behaviour.

## 7. Localisation Considerations
- [TARGET_LANGUAGE]: [NEEDS CONFIRMATION] Do not assume language or tone.
- [BRAND_TONE]: [NEEDS CONFIRMATION] Confirm approved style before copy development.

## 8. Compliance & RG Considerations
- [REGULATORY_NOTES]: [NEEDS CONFIRMATION] Local notes are required before launch claims or final customer-facing copy.
- [RISK] Do not proceed to launch without confirmed self-exclusion, RG-risk, cooling-off, opt-in, and promotional restriction handling.

## 9. Commercial Considerations
- [RISK] Bonus cost, margin exposure, bonus abuse risk, and sharp or arb-sensitive exposure cannot be assessed without segment and offer data.
- [RECOMMENDATION] Confirm expected incremental value before selecting a rich offer.

## 10. Recommended Next Skills
- crm-sportsbook-event-opportunity
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 11. Launch Readiness
- Needs confirmation before campaign design.
```
