---
name: crm-sportsbook-localisation
description: Localises market-agnostic sportsbook CRM campaign logic, offer framing, and customer-facing copy for runtime-supplied target market, target language, channel, brand tone, localisation notes, approved terms, forbidden terms, and regulatory notes without inventing local facts.
---

# CRM Sportsbook Localisation

## Purpose

This skill localises sportsbook CRM campaigns, offers, and copy for the supplied `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, and `[BRAND_TONE]`.

It helps CRM teams adapt:

- Message clarity.
- Tone.
- Cultural fit.
- Offer explanation.
- `[CTA]` wording.
- `[T&CS]` handling.
- Personalisation style.
- Channel suitability.
- Responsible-gaming-sensitive language.

The skill supports both:

- Localisation review of existing campaign material.
- Localised rewriting of customer-facing copy when enough inputs are provided.

The skill must not invent local facts, slang, legal requirements, sport preferences, cultural norms, local communication styles, or local product terminology.

## Role in the Skill Pack

This skill usually runs after:

- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`, when SMS copy exists.
- `crm-sportsbook-offer-mechanics`, when offer wording needs localisation.
- `crm-sportsbook-market-context`, when market context exists.

It may also use context from:

- `crm-sportsbook-event-opportunity`
- `crm-sportsbook-player-segmentation`

It may be selected by `crm-sportsbook-skill-router` when the user asks for localisation, translation, tone adaptation, market-fit review, target-language adaptation, or localised SMS variants.

It feeds:

- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`
- `crm-sportsbook-post-campaign-analysis`

It should not replace:

- Market research.
- Final legal review.
- Responsible-gaming review.
- Final compliance approval.
- Translation QA by a native speaker where required.
- Channel-specific copy skills.

It adapts the campaign for local clarity and tone using only runtime inputs and confirmed context.

## When to Use

Use this skill when the CRM manager needs to:

- Localise SMS copy.
- Review whether copy fits `[TARGET_MARKET]`.
- Translate or adapt copy into `[TARGET_LANGUAGE]`.
- Adjust tone for `[BRAND_TONE]`.
- Make offer copy clearer for local users.
- Check whether the copy relies on idioms or unclear phrases.
- Identify localisation risks.
- Adapt `[CTA]` wording.
- Adapt `[T&CS]` wording cues.
- Check whether personalisation feels natural or invasive.
- Compare literal translation vs adapted localisation.
- Produce multiple localised variants.
- Prepare copy for native-speaker or compliance review.
- Localise event-led campaign messaging.
- Localise reactivation, retention, activation, VIP, or event campaigns.

## When Not to Use

Do not use this skill to:

- Invent local language rules.
- Invent local slang.
- Invent local sports preferences.
- Invent local cultural behaviour.
- Invent local legal or regulatory requirements.
- Create full campaign strategy from scratch.
- Design `[OFFER_MECHANIC]` from scratch.
- Select target audiences from raw data.
- Write long-form email campaigns.
- Write push notifications as the primary output.
- Draft legal `[T&CS]`.
- Provide final legal approval.
- Provide final responsible-gaming approval.
- Replace human native-language QA where required.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- SMS copy: `crm-sportsbook-sms-copy`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- Source campaign text or copy to localise.
- `[CAMPAIGN_OBJECTIVE]`
- `[OFFER_MECHANIC]` and `[OFFER_VALUE]`, if offer copy is involved.
- `[BRAND_TONE]` or instruction to preserve existing tone.

### Recommended inputs

- `[SOURCE_LANGUAGE]`
- Campaign brief output.
- SMS copy output, if SMS localisation is needed.
- Offer mechanics output.
- Market context output.
- `[TARGET_SEGMENT]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[CTA]`
- `[T&CS_LINK]`
- `[T&CS]`
- `[REGULATORY_NOTES]`
- `[LOCALISATION_NOTES]`
- `[APPROVED_TERMS]`
- `[FORBIDDEN_TERMS]`
- `[OPT_OUT_TEXT]`

### Advanced optional inputs

- Brand voice guide.
- Existing approved local copy examples.
- Native-speaker notes.
- Compliance-approved terms.
- Responsible-gaming-approved wording.
- Required disclaimers.
- Local legal wording requirements supplied at runtime.
- CRM platform character limits.
- SMS encoding restrictions.
- Link length.
- `[PERSONALISATION_TOKEN]`
- Previous campaign performance by language.
- Previous opt-out rate by tone.
- Previous complaints or customer support issues.
- Glossary of betting terms.
- Glossary of offer terms.
- Glossary of product terms.
- Forbidden slang or sensitive phrases.
- Formality preference.
- Reading-level preference.
- Regional dialect preference, if supplied by the user.

## Output

The skill should produce:

- Localisation context summary.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Localisation strategy.
- Localised copy variants.
- Literal vs adapted wording notes, where relevant.
- Character counts, if SMS.
- Tone review.
- Clarity review.
- Offer understanding review.
- `[CTA]` review.
- `[T&CS]` handling review.
- Personalisation review.
- RG/compliance language risks.
- Commercial clarity risks.
- Recommended localised variant.
- Native-speaker/compliance review notes.
- Recommended next skills.

## Workflow

1. Identify `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, and `[TARGET_CHANNEL]`.
2. Load and apply `crm-sportsbook-shared-principles`.
3. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
4. Read `crm-sportsbook-campaign-brief` output if available.
5. Read `crm-sportsbook-sms-copy` output if available.
6. Read `crm-sportsbook-market-context` output if available.
7. Read `crm-sportsbook-event-opportunity`, `crm-sportsbook-player-segmentation`, and `crm-sportsbook-offer-mechanics` outputs if relevant.
8. Identify source copy and `[SOURCE_LANGUAGE]`.
9. Identify `[BRAND_TONE]`.
10. List all confirmed inputs as `[CONFIRMED]`.
11. Separate confirmed facts from assumptions.
12. Mark missing localisation-critical inputs as `[NEEDS CONFIRMATION]`.
13. Check whether local facts, language rules, or cultural notes were supplied.
14. Do not invent local facts, slang, or cultural assumptions.
15. Determine localisation goal:
    - Translate closely.
    - Adapt for clarity.
    - Adapt for tone.
    - Simplify.
    - Make more compliant/RG-safe.
    - Make more SMS-friendly.
16. Check offer clarity in `[TARGET_LANGUAGE]`.
17. Check `[CTA]` clarity.
18. Check `[T&CS]` cue or `[T&CS_LINK]` clarity.
19. Check whether any phrase may be misleading or aggressive.
20. Check whether any personalisation may feel invasive.
21. Produce localised variants using only confirmed inputs and safe assumptions.
22. Provide character counts if `[TARGET_CHANNEL]` is SMS.
23. Flag translation/localisation uncertainties.
24. Recommend native-speaker, legal, RG, or compliance review where needed.
25. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[TARGET_LANGUAGE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is missing, provide general localisation guidance and mark channel handling as `[NEEDS CONFIRMATION]`.
- If no source copy is provided, ask for copy or recommend running the relevant copy skill first.
- If `[TARGET_CHANNEL]` is SMS, preserve brevity and include character counts.
- If the copy is too long for SMS, produce shorter alternatives.
- If `[OFFER_MECHANIC]` cannot be explained clearly after localisation, flag it as `[RISK]`.
- If `[APPROVED_TERMS]` are supplied, use them consistently.
- If `[FORBIDDEN_TERMS]` are supplied, avoid them and flag any source-copy conflict.
- If `[REGULATORY_NOTES]` are missing, do not make compliance claims.
- If legal or RG wording is required but missing, mark it as `[NEEDS CONFIRMATION]`.
- If copy includes idioms, slang, humour, or wordplay, flag translation risk.
- If the copy uses aggressive urgency, rewrite more neutrally.
- If the copy uses "guaranteed", "risk-free", "free money", or similar risky claims, flag and rewrite unless explicitly approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- If the copy references losses, recovery, debt, financial stress, or pressure, reject or rewrite.
- If personalisation feels invasive, replace it with safer relevance-based wording.
- If local tone is unknown, use neutral clear wording and mark tone as `[NEEDS CONFIRMATION]`.
- If exact translation would be unclear, provide an adapted version and explain the reason.
- If the skill is uncertain about language quality, mark it as `[NEEDS CONFIRMATION]` and recommend native-speaker QA.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, and `crm-sportsbook-sms-copy` when SMS copy exists.
- Normally run after this skill: `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Whether sportsbook terms translate clearly.
- Whether bet type names are understandable.
- Whether `[OFFER_MECHANIC]` needs explanation.
- Whether odds boost wording may imply guaranteed profit.
- Whether cashback wording may sound like loss recovery.
- Whether accumulator insurance wording may be misunderstood.
- Whether bet builder wording depends on product naming.
- Whether free bet wording could imply cash.
- Whether deposit bonus wording could imply financial benefit beyond betting.
- Whether event-led wording depends on confirmed event details.
- Whether live betting wording creates timing or availability risk.
- Whether VIP wording feels personal but not intrusive.
- Whether reactivation wording feels calm and non-manipulative.
- Whether `[T&CS]` cues preserve material restrictions.
- Whether `[CTA]` remains obvious after localisation.

## Localisation Modes

Support the following modes.

### Literal Translation

Use when the user asks for a close translation and the source wording is already clear, compliant, and channel-suitable.

Output should:

- Preserve meaning.
- Preserve offer terms.
- Avoid adding new claims.
- Flag any phrase that may not translate naturally.

### Adaptive Localisation

Use when the source copy needs to feel natural in `[TARGET_LANGUAGE]` or `[TARGET_MARKET]`.

Output should:

- Preserve offer meaning.
- Adapt sentence structure.
- Improve clarity.
- Avoid unsupported local slang.
- Respect `[BRAND_TONE]`.
- Flag uncertain cultural choices.

### Clarity Simplification

Use when the source copy is too complex.

Output should:

- Simplify offer wording.
- Clarify qualification.
- Clarify reward.
- Clarify `[CTA]`.
- Preserve `[T&CS]`.
- Avoid removing material restrictions.

### SMS Localisation

Use when `[TARGET_CHANNEL]` is SMS.

Output should:

- Keep copy short.
- Include character counts.
- Avoid complex grammar.
- Avoid idioms.
- Avoid unnecessary emojis.
- Avoid special characters unless approved.
- Preserve `[CTA]` and `[T&CS]` cue.
- Flag Unicode or non-Latin script character-count risks where relevant.

### RG-Safe Localisation

Use when source copy contains pressure, risky claims, or reactivation sensitivity.

Output should:

- Remove loss-chasing language.
- Remove financial-solution framing.
- Remove manipulative urgency.
- Remove guaranteed-win claims.
- Replace aggressive copy with neutral value framing.

### Brand-Tone Localisation

Use when `[BRAND_TONE]` is supplied.

Output should:

- Match the supplied tone.
- Avoid stereotypes.
- Avoid unsupported local slang.
- Preserve clarity.
- Preserve offer truthfulness.

## Offer Term Localisation Guidance

### Free Bet

Ensure the localised wording does not imply:

- Cash gift.
- Guaranteed profit.
- No conditions.

Flag if stake-return rules or expiry need clearer treatment.

### Bet-and-Get

Ensure the action and reward are clear.

Avoid overloading SMS copy with every condition.

### Odds Boost

Ensure the wording does not imply improved chance of winning or guaranteed profit.

### Accumulator Insurance

Ensure the wording does not hide conditions such as number of legs, minimum odds, or refund cap where these materially affect understanding.

### Cashback

Avoid wording that sounds like recovering losses.

Prefer neutral value wording.

### Bet Builder Boost

Ensure product name and mechanic are understood in `[TARGET_LANGUAGE]`.

Mark product naming as `[NEEDS CONFIRMATION]` if unclear.

### Deposit Bonus

Avoid wording that frames deposit as financial gain or solution.

Make conditions visible or linked.

### Reload Offer

Avoid aggressive deposit pressure.

### Mission or Challenge

Avoid wording that creates grind pressure or excessive play pressure.

### Loyalty Points

Clarify whether points have monetary value only if confirmed.

### VIP Bespoke Offer

Use careful tone.

Avoid implying special treatment based on risky spend or losses.

## Market-Agnostic Design Rules

The skill must never assume:

- Local language norms.
- Local slang.
- Local dialect.
- Local sports preferences.
- Local betting habits.
- Local cultural tone.
- Local humour.
- Local legal wording.
- Local payment terminology.
- Local operator conventions.
- Local competitor style.
- Local responsible-gaming requirements.

All localisation details must come from:

- User-provided inputs.
- Existing skill outputs.
- Internal documents.
- `[APPROVED_TERMS]`.
- `[FORBIDDEN_TERMS]`.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts.

## Channel-Aware Design Rules

The skill should adapt to `[TARGET_CHANNEL]`.

For SMS:

- Keep the message short.
- Include character counts.
- Keep one offer only.
- Preserve `[CTA]`.
- Preserve or link to `[T&CS]`.
- Avoid complex mechanics.
- Avoid slang unless approved.
- Avoid emojis unless approved.
- Flag Unicode and `[PERSONALISATION_TOKEN]` expansion risks.
- Recommend `crm-sportsbook-rg-compliance-review` before launch.

For email:

- Do not create full email campaign copy unless explicitly requested.
- Note that detailed email execution should be handled by a future email-specific skill.
- Localisation may review subject line, headline, body tone, `[CTA]`, and `[T&CS]` clarity if provided.

For push:

- Do not create full push copy unless explicitly requested.
- Note that detailed push execution should be handled by a future push-specific skill.
- Keep wording short and non-manipulative.

For onsite/inbox:

- Consider whether more explanation is needed than SMS allows.

For VIP outreach:

- Recommend manual review.
- Avoid mass tone.
- Avoid invasive behavioural references.
- Use calm, clear, personal-but-safe wording.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag or rewrite localised copy that:

- Encourages chasing losses.
- Refers to previous losses.
- Suggests betting solves financial problems.
- Suggests guaranteed profit.
- Uses "risk-free" unless approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Uses "free money" or equivalent misleading phrasing.
- Uses aggressive urgency.
- Uses emotional pressure.
- Uses manipulative reactivation wording.
- Hides material restrictions.
- Makes betting sound necessary to enjoy an event.
- Uses invasive personalisation.
- Encourages excessive bet frequency.
- Encourages excessive accumulator leg counts without controls.
- Misrepresents bonus or reward conditions.

The skill must recommend `crm-sportsbook-rg-compliance-review` before launch.

## Commercial Guardrails

The skill should flag if localisation:

- Overstates `[OFFER_VALUE]`.
- Weakens qualification wording.
- Removes important restrictions.
- Makes reward rules ambiguous.
- Makes expiry ambiguous.
- Makes bonus abuse easier.
- Creates unrealistic expectations.
- Creates customer support risk.
- Makes the campaign look broader than intended.
- Changes the meaning of odds, reward, refund, cashback, or bonus terms.
- Makes a capped offer sound uncapped.
- Makes a bonus sound like withdrawable cash when it is not.

The localised copy should preserve:

- `[OFFER_VALUE]`.
- Qualification.
- Reward type.
- Expiry.
- Minimum stake.
- Minimum odds.
- Max bonus or reward.
- `[T&CS_LINK]` or cue.
- `[T&CS]` restrictions.
- Usage limits.
- Eligibility scope.

## Brand & UX Guardrails

The skill should ensure localisation:

- Feels clear and human.
- Matches `[BRAND_TONE]`.
- Preserves the original intent.
- Does not sound spammy unless brand-approved.
- Does not stereotype `[TARGET_MARKET]`.
- Does not use unsupported local slang.
- Does not overuse betting jargon.
- Does not imply certainty of winning.
- Does not make personalisation feel invasive.
- Does not hide important restrictions.
- Has a clear next action.
- Is understandable to `[TARGET_SEGMENT]`.

## Translation Quality Rules

The skill should:

- Preserve meaning over literal phrasing when needed.
- Avoid adding unsupported claims.
- Avoid removing restrictions.
- Keep offer terms consistent.
- Use `[APPROVED_TERMS]` when provided.
- Avoid `[FORBIDDEN_TERMS]` when provided.
- Flag uncertain product terms.
- Flag awkward literal translations.
- Flag culturally risky humour or idioms.
- Recommend native-speaker QA where confidence is low.
- Recommend compliance review where offer wording changes materially.

## Personalisation Rules

The skill may localise `[PERSONALISATION_TOKEN]` only when supplied.

Safe personalisation may include:

- First name, if brand-approved.
- `[OFFER_VALUE]`.
- `[TARGET_EVENT]`, if supplied.
- `[TARGET_SPORT]`, if supplied.
- Expiry, if confirmed in source copy or runtime notes.

Avoid personalisation that implies:

- Loss monitoring.
- Financial stress.
- High spend surveillance.
- Dormancy shaming.
- Risky gambling behaviour.
- Sensitive profiling.
- Excessive familiarity.

## A/B Testing Localisation Guidance

The skill should suggest localisation-sensitive A/B tests when useful.

Possible tests:

- Literal translation vs adaptive localisation.
- Value-led vs event-led wording.
- Formal vs neutral tone, if supplied as brand-acceptable.
- `[CTA]` wording A vs `[CTA]` wording B.
- Short SMS vs clearer slightly longer SMS.
- `[PERSONALISATION_TOKEN]` vs no personalisation.
- `[T&CS]` cue style A vs `[T&CS]` cue style B.

Each test should include:

- Hypothesis.
- Variant A.
- Variant B.
- Primary KPI.
- Guardrail metric.
- Decision rule.

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
# Localisation Output

## 1. Localisation Context
- Target market: [TARGET_MARKET]
- Source language: [SOURCE_LANGUAGE]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Brand name: [BRAND_NAME]
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
- Localisation notes used: [LOCALISATION_NOTES]
- Approved terms used: [APPROVED_TERMS]
- Forbidden terms avoided: [FORBIDDEN_TERMS]

## 7. Localised Copy Variants
Provide 3-6 variants unless the user requests a different number.

| Variant name | Localised copy | Character count if SMS | Localisation approach | Copy angle | Offer clarity | CTA clarity | T&C handling | Tone notes | Risk notes |
|---|---|---:|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |

## 8. Recommended Variant
- Recommended variant:
- Clarity:
- Naturalness:
- Channel fit:
- Offer understanding:
- Brand fit:
- RG safety:
- Commercial clarity:

## 9. Literal vs Adapted Notes
- Meaning preserved:
- Phrasing adapted:
- Native-speaker check:

## 10. Tone Review
- Brand tone fit:
- Local tone uncertainty:
- Formality:
- Slang/idiom risk:
- Spamminess risk:

## 11. Offer & CTA Clarity Review
- Offer value clarity:
- Qualification clarity:
- Reward clarity:
- Expiry clarity:
- CTA clarity:
- T&C clarity:

## 12. RG & Compliance Language Notes
- Pressure risk:
- Loss-chasing risk:
- Misleading claim risk:
- T&C risk:
- Personalisation risk:
- Required review:

## 13. Commercial Notes
- Bonus value accuracy:
- Restriction accuracy:
- Abuse risk:
- Ambiguity risk:
- Support burden risk:

## 14. Localisation QA Notes
- Terms to confirm:
- Native-speaker review items:
- Compliance review items:
- Character-count risks:
- Personalisation-token risks:
- Encoding risks:

## 15. A/B Test Suggestion
- Hypothesis:
- Variant A:
- Variant B:
- Primary KPI:
- Guardrail metric:
- Decision rule:

## 16. Recommended Next Skills
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing
- crm-sportsbook-post-campaign-analysis

## 17. Launch Readiness
- Ready for RG/compliance review / Needs native-language QA before RG/compliance review / Needs missing inputs before localisation finalisation / Needs offer clarification before localisation finalisation / Needs T&C confirmation before localisation finalisation / Not recommended based on current information:
- Rationale:
```

## Example User Request

"Localise this SMS copy for `[TARGET_MARKET]` in `[TARGET_LANGUAGE]`. The target channel is `[TARGET_CHANNEL]`, the brand tone is `[BRAND_TONE]`, and the offer is `[OFFER_VALUE]` via `[OFFER_MECHANIC]`. Source copy: source copy supplied by the user."

## Example Output

```markdown
# Localisation Output

## 1. Localisation Context
- Target market: [TARGET_MARKET]
- Source language: [SOURCE_LANGUAGE]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Brand name: [BRAND_NAME]
- Brand tone: [BRAND_TONE]

## 2. Source Copy / Source Material
- Source copy: Source copy supplied by the user.

## 3. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Target language: [TARGET_LANGUAGE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Brand tone: [BRAND_TONE]
- [CONFIRMED] Offer mechanic: [OFFER_MECHANIC]
- [CONFIRMED] Offer value: [OFFER_VALUE]

## 4. Working Assumptions
- [ASSUMPTION] No local slang, language norm, regulatory requirement, sport preference, or cultural tone is assumed unless supplied in [LOCALISATION_NOTES], [REGULATORY_NOTES], [APPROVED_TERMS], or confirmed research.

## 5. Needs Confirmation
- [NEEDS CONFIRMATION] [SOURCE_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SEGMENT]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_EVENT]
- [NEEDS CONFIRMATION] [TARGET_TOURNAMENT]
- [NEEDS CONFIRMATION] [TARGET_FIXTURE]
- [NEEDS CONFIRMATION] [CTA]
- [NEEDS CONFIRMATION] [T&CS]
- [NEEDS CONFIRMATION] [T&CS_LINK]
- [NEEDS CONFIRMATION] [BRAND_NAME]
- [NEEDS CONFIRMATION] [LOCALISATION_NOTES]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]
- [NEEDS CONFIRMATION] [APPROVED_TERMS]
- [NEEDS CONFIRMATION] [FORBIDDEN_TERMS]
- [NEEDS CONFIRMATION] [OPT_OUT_TEXT]

## 6. Localisation Strategy
- Mode: Adaptive localisation with clarity simplification.
- Reason: Preserve offer meaning while keeping copy clear for [TARGET_CHANNEL].
- Localisation notes used: [LOCALISATION_NOTES]
- Approved terms used: [APPROVED_TERMS]
- Forbidden terms avoided: [FORBIDDEN_TERMS]

## 7. Localised Copy Variants
| Variant name | Localised copy | Character count if SMS | Localisation approach | Copy angle | Offer clarity | CTA clarity | T&C handling | Tone notes | Risk notes |
|---|---|---:|---|---|---|---|---|---|---|
| Clear value | [OFFER_VALUE] with [OFFER_MECHANIC]. [CTA]. T&Cs: [T&CS_LINK] | 61 | Clarity simplification | Value-led | Clear if [T&CS] are approved | Clear if [CTA] is approved | Link included | Neutral [BRAND_TONE] | Recount after runtime values expand |
| Event relevance | [TARGET_EVENT]: use [OFFER_VALUE] with [OFFER_MECHANIC]. [CTA]. T&Cs: [T&CS_LINK] | 81 | Adaptive localisation | Event-led | Clear if event is confirmed | Clear if [CTA] is approved | Link included | Neutral [BRAND_TONE] | Event relevance needs confirmation |
| Soft reactivation | A [BRAND_NAME] offer is available: [OFFER_VALUE]. Details: [T&CS_LINK] | 70 | RG-safe rewrite | Soft value | Clear if offer terms are approved | Indirect | Details link included | Calm | Requires suppression review |

## 8. Recommended Variant
- Recommended variant: Clear value.
- Clarity: Strong.
- Naturalness: [NEEDS CONFIRMATION] Native-language QA recommended.
- Channel fit: Strong for SMS if final runtime values stay short.
- Offer understanding: Clear if [OFFER_VALUE], [OFFER_MECHANIC], and [T&CS_LINK] are approved.
- Brand fit: [NEEDS CONFIRMATION] [BRAND_TONE] guidance required.
- RG safety: Low pressure and no loss framing.
- Commercial clarity: Needs final [T&CS] confirmation.

## 9. Literal vs Adapted Notes
- Meaning preserved: Offer value, mechanic, CTA, and T&C cue.
- Phrasing adapted: Shorter sentence structure for [TARGET_CHANNEL].
- Native-speaker check: [RECOMMENDATION] Required before launch if language quality is uncertain.

## 10. Tone Review
- Brand tone fit: [NEEDS CONFIRMATION] [BRAND_TONE]
- Local tone uncertainty: [NEEDS CONFIRMATION] [LOCALISATION_NOTES]
- Formality: Neutral.
- Slang/idiom risk: Low because none was added.
- Spamminess risk: Low if frequency caps and opt-out handling are confirmed.

## 11. Offer & CTA Clarity Review
- Offer value clarity: [OFFER_VALUE]
- Qualification clarity: [NEEDS CONFIRMATION] [T&CS]
- Reward clarity: [RECOMMENDATION] Keep reward wording consistent with [APPROVED_TERMS].
- Expiry clarity: [NEEDS CONFIRMATION] Confirm if expiry must be included.
- CTA clarity: [CTA]
- T&C clarity: [T&CS_LINK]

## 12. RG & Compliance Language Notes
- Pressure risk: Low in recommended variant.
- Loss-chasing risk: Avoid all loss or recovery wording.
- Misleading claim risk: Avoid guaranteed, risk-free, and free money wording unless approved.
- T&C risk: [NEEDS CONFIRMATION] [T&CS]
- Personalisation risk: Use [PERSONALISATION_TOKEN] only if approved.
- Required review: crm-sportsbook-rg-compliance-review.

## 13. Commercial Notes
- Bonus value accuracy: [NEEDS CONFIRMATION] [OFFER_VALUE]
- Restriction accuracy: [NEEDS CONFIRMATION] [T&CS]
- Abuse risk: [RISK] Do not broaden eligibility through wording.
- Ambiguity risk: [RISK] Confirm offer terms and approved terminology.
- Support burden risk: [RISK] Increases if qualification is unclear.

## 14. Localisation QA Notes
- Terms to confirm: [APPROVED_TERMS], [FORBIDDEN_TERMS], [OFFER_MECHANIC], [CTA]
- Native-speaker review items: Naturalness, clarity, tone, and product terminology.
- Compliance review items: [REGULATORY_NOTES], [T&CS], [OPT_OUT_TEXT]
- Character-count risks: Runtime values and links may expand.
- Personalisation-token risks: [PERSONALISATION_TOKEN] may expand or feel invasive.
- Encoding risks: Confirm SMS encoding after final [TARGET_LANGUAGE] copy.

## 15. A/B Test Suggestion
- Hypothesis: A clear value-led localisation will outperform an event-led localisation when event affinity is unconfirmed.
- Variant A: Clear value.
- Variant B: Event relevance.
- Primary KPI: Click or eligible action conversion.
- Guardrail metric: Opt-out rate, complaint rate, and post-campaign RG flags.
- Decision rule: Use the variant with better incremental conversion and no material guardrail deterioration.

## 16. Recommended Next Skills
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing
- crm-sportsbook-post-campaign-analysis

## 17. Launch Readiness
- Needs native-language QA before RG/compliance review.
- Rationale: [TARGET_LANGUAGE] quality, [APPROVED_TERMS], [FORBIDDEN_TERMS], [T&CS], [REGULATORY_NOTES], and [OPT_OUT_TEXT] require confirmation before launch.
```
