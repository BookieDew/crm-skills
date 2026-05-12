---
name: crm-sportsbook-sms-copy
description: Creates short, clear, market-agnostic sportsbook CRM SMS copy variants with character counts, offer clarity checks, CTA checks, T&C handling, responsible-gaming safeguards, commercial notes, localisation readiness, and A/B test suggestions.
---

# CRM Sportsbook SMS Copy

## Purpose

This skill creates short, clear, responsible-gaming-aware SMS copy for sportsbook CRM campaigns.

It helps CRM teams turn an approved or draft campaign brief into customer-facing SMS variants that are:

- Clear.
- Short.
- Segment-relevant.
- Offer-focused.
- Channel-appropriate.
- Responsible-gaming-aware.
- Commercially sensible.
- Ready for localisation and compliance review.

This skill supports both:

- Strategic SMS copy direction.
- Final SMS copy variants.

It must stay SMS-specific. It must not become an email, push, onsite, inbox, or generic copywriting skill.

## Role in the Skill Pack

This is the first fully developed channel-specific execution skill.

It usually runs after:

- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-player-segmentation`

It may also use context from:

- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`

It may be selected by `crm-sportsbook-skill-router` when the user asks for SMS copy, SMS variants, SMS rewriting, copy review, or SMS A/B test copy.

It feeds:

- `crm-sportsbook-localisation`
- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`
- `crm-sportsbook-post-campaign-analysis`

It should not replace:

- Full campaign strategy.
- Offer mechanics design.
- Localisation review.
- Final compliance approval.
- Legal `[T&CS]` drafting.
- Email copy skill.
- Push copy skill.

It turns campaign logic into SMS-ready copy.

## When to Use

Use this skill when the CRM manager needs:

- SMS copy for a sportsbook CRM campaign.
- SMS copy variants for A/B testing.
- Short event-led sportsbook SMS.
- Activation SMS.
- Retention SMS.
- Reactivation SMS.
- Deposit or reload offer SMS.
- Free bet SMS.
- Bet-and-get SMS.
- Odds boost SMS.
- Accumulator insurance SMS.
- Bet builder boost SMS.
- Cashback SMS.
- Loyalty or mission SMS.
- VIP SMS draft, if SMS is an approved VIP channel.
- SMS copy rewrite for clarity, tone, or compliance.
- SMS copy review for responsible-gaming risk.
- SMS copy with character count.
- SMS copy using placeholders or `[PERSONALISATION_TOKEN]`.

## When Not to Use

Do not use this skill to:

- Write full email campaigns.
- Write push notifications as the primary output.
- Write landing page copy.
- Draft full legal `[T&CS]`.
- Create the campaign strategy from scratch.
- Select target audience from raw data.
- Design complex offer mechanics from scratch.
- Perform final legal approval.
- Perform final responsible-gaming approval.
- Translate or localise into a specific language without localisation review.
- Invent local market facts.
- Invent event dates, fixtures, odds, regulations, or local preferences.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- Localisation: `crm-sportsbook-localisation`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[TARGET_CHANNEL]` = SMS.
- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]` or instruction to keep output in the source language.
- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_SEGMENT]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- `[CTA]`
- `[T&CS_LINK]` or `[T&CS]` handling instruction.

### Recommended inputs

- Campaign brief output.
- Offer mechanics output.
- Player segmentation output.
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[EXPIRY]`
- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- `[ELIGIBLE_MARKETS]`
- `[BRAND_NAME]`
- `[BRAND_TONE]`
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[REGULATORY_NOTES]`
- `[OPT_OUT_TEXT]`
- Required character limit supplied at runtime.

### Advanced optional inputs

- Approved SMS tone examples.
- Forbidden words or phrases.
- Approved compliance wording.
- Required legal disclaimer.
- Required responsible-gaming wording.
- `[PERSONALISATION_TOKEN]`
- Sender name.
- Previous SMS performance.
- Segment-level SMS engagement.
- Opt-out rate history.
- Delivery restrictions.
- Unicode or GSM character requirements.
- Link length.
- Short-link format.
- CRM platform character handling rules.
- Market-specific language rules, if provided.
- Localisation guidance.
- A/B testing plan.
- Frequency cap rules.
- Journey step number.
- Reminder logic.
- Control group requirement.

## Output

The skill should produce:

- SMS campaign context summary.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- SMS copy variants.
- Character count for each variant.
- Copy angle for each variant.
- Segment fit notes.
- Offer clarity check.
- CTA clarity check.
- `[T&CS]` handling note.
- RG/compliance risk notes.
- Commercial risk notes.
- Localisation notes.
- Recommended variant.
- A/B test suggestion.
- Recommended next skills.

## Workflow

1. Confirm that `[TARGET_CHANNEL]` is SMS.
2. Load and apply `crm-sportsbook-shared-principles`.
3. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
4. Read the `crm-sportsbook-campaign-brief` output if available.
5. Read the `crm-sportsbook-offer-mechanics` output if available.
6. Read the `crm-sportsbook-player-segmentation` output if available.
7. Use `crm-sportsbook-market-context` and `crm-sportsbook-event-opportunity` output when available.
8. Identify `[CAMPAIGN_OBJECTIVE]`.
9. Identify `[TARGET_SEGMENT]`.
10. Identify `[OFFER_MECHANIC]` and `[OFFER_VALUE]`.
11. Identify required offer constraints:
    - `[MINIMUM_STAKE]`
    - `[MINIMUM_ODDS]`
    - `[MAX_BONUS_VALUE]`
    - `[EXPIRY]`
    - `[ELIGIBLE_MARKETS]`
    - `[T&CS_LINK]`
12. List all confirmed inputs as `[CONFIRMED]`.
13. Separate confirmed facts from assumptions.
14. Mark missing copy-critical inputs as `[NEEDS CONFIRMATION]`.
15. Decide whether the offer can be explained clearly in SMS.
16. Simplify the copy angle if the mechanic is complex.
17. Write multiple SMS variants with distinct angles.
18. Count characters for each variant.
19. Check whether character count includes spaces and punctuation.
20. Flag if character count may be affected by Unicode, emojis, special characters, link replacement, or token expansion.
21. Check copy for misleading claims, pressure, or RG risk.
22. Check copy for commercial clarity:
    - Reward.
    - Qualification.
    - `[EXPIRY]`.
    - Key restrictions.
    - `[CTA]`.
23. Check copy for brand and UX clarity.
24. Recommend the strongest variant.
25. Suggest an A/B test if useful.
26. Recommend localisation and RG/compliance review before launch.

## Decision Logic

Apply these rules:

- If `[TARGET_CHANNEL]` is not SMS, recommend the appropriate future channel-specific skill and do not write non-SMS copy.
- If `[TARGET_LANGUAGE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[OFFER_MECHANIC]` is missing, recommend running `crm-sportsbook-offer-mechanics`.
- If `[TARGET_SEGMENT]` is missing, recommend running `crm-sportsbook-player-segmentation`.
- If campaign brief is missing, the skill may still write copy using available inputs, but must label assumptions.
- If the offer cannot be explained clearly in SMS, flag it as `[RISK]` and recommend simplification.
- If `[T&CS_LINK]` or `[T&CS]` handling is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[EXPIRY]` is missing and the offer is time-limited, mark it as `[NEEDS CONFIRMATION]`.
- If legal disclaimer or `[OPT_OUT_TEXT]` is required but missing, mark it as `[NEEDS CONFIRMATION]`.
- If a character limit is supplied, respect it.
- If no character limit is supplied, aim for short SMS copy and provide character counts.
- If emojis or special characters are used, flag possible SMS encoding impact.
- If `[CAMPAIGN_OBJECTIVE]` is reactivation, avoid emotional pressure and loss-recovery framing.
- If `[CAMPAIGN_OBJECTIVE]` is retention, avoid implying the user must act urgently.
- If `[CAMPAIGN_OBJECTIVE]` is activation, keep the action simple and clear.
- If the campaign is event-led, use `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, or `[TARGET_FIXTURE]` only if supplied by the user or prior skill output.
- If `[TARGET_SEGMENT]` is VIP, avoid mass-market tone and recommend manual review.
- If `[TARGET_SEGMENT]` is bonus-sensitive, make qualification and restrictions clear.
- If `[TARGET_SEGMENT]` is sharp or arb-sensitive, avoid exploitable value framing and recommend review.
- If "risk-free" wording appears, flag it as `[RISK]` unless explicitly approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- If "guaranteed win" or equivalent wording appears, reject or rewrite.
- If the copy references losses, debt, financial stress, or recovery, reject or rewrite.
- If personalisation feels invasive, rewrite using safer generic relevance.
- If copy hides key restrictions, flag it as `[RISK]`.
- If copy overstates value, rewrite with clearer terms.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context` when market or language context matters, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, and `crm-sportsbook-campaign-brief`.
- Normally run after this skill: `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, SMS communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Sport preference, if supplied.
- Event relevance, if supplied.
- Fixture or tournament relevance, if supplied.
- Bet type preference.
- Pre-match versus live betting.
- Single versus accumulator preference.
- Odds boost suitability.
- Free bet suitability.
- Cashback suitability.
- Bet builder suitability.
- Deposit or reload suitability.
- Bonus sensitivity.
- VIP status.
- Recreational versus sharp behaviour.
- Arb-sensitive users.
- Churn risk.
- Stake level.
- Margin protection.
- Event timing.
- Bonus abuse risk.
- Product availability.
- Market availability.
- SMS opt-in and frequency caps.
- Character limits and link length.
- Post-campaign RG monitoring.

## SMS Writing Rules

The SMS should:

- Communicate one offer only.
- Make `[OFFER_VALUE]` clear early.
- Use one simple `[CTA]`.
- Avoid complex mechanics.
- Avoid jargon.
- Avoid misleading certainty.
- Avoid aggressive pressure.
- Avoid emotional manipulation.
- Avoid loss-recovery framing.
- Avoid invasive personalisation.
- Avoid excessive punctuation.
- Avoid unnecessary emojis unless brand-approved.
- Include or reference `[T&CS]` or `[T&CS_LINK]` clearly.
- Mention `[EXPIRY]` only if relevant and confirmed.
- Mention key restrictions if they materially affect understanding.
- Use simple words.
- Keep the message easy to scan.

## SMS Character Counting Rules

The skill must:

- Provide character count for every SMS variant.
- Count spaces and punctuation.
- State whether the count includes `[T&CS_LINK]`, `[BRAND_NAME]`, and `[OPT_OUT_TEXT]` if those are placeholders.
- Flag that final CRM platform character count may differ if:
  - Short links are replaced.
  - `[PERSONALISATION_TOKEN]` expands.
  - Unicode characters are used.
  - Emojis are used.
  - Special punctuation is used.
  - Non-Latin scripts are used.
- Prefer plain punctuation where character limits are strict.
- Avoid emojis unless requested or brand-approved.

When character counts are based on placeholder copy, state that the count uses visible placeholder characters and must be recalculated after runtime values, links, opt-out text, or personalisation tokens are expanded.

## Copy Variant Types

Produce useful variant types depending on the campaign.

### Value-Led Variant

Focuses on `[OFFER_VALUE]`.

Example structure:

`[OFFER_VALUE]` is available for your next `[TARGET_SPORT]` bet. `[CTA]`. T&Cs: `[T&CS_LINK]`

### Event-Led Variant

Focuses on `[TARGET_EVENT]` or `[TARGET_FIXTURE]`.

Example structure:

`[TARGET_EVENT]` is coming. Use `[OFFER_VALUE]` with `[OFFER_MECHANIC]`. `[CTA]`. T&Cs: `[T&CS_LINK]`

### Simple CTA Variant

Focuses on immediate clarity.

Example structure:

Your `[BRAND_NAME]` offer is ready: `[OFFER_VALUE]`. `[CTA]`. T&Cs: `[T&CS_LINK]`

### Reactivation-Safe Variant

Uses a soft return angle without emotional pressure.

Example structure:

A `[BRAND_NAME]` offer is available: `[OFFER_VALUE]` on `[TARGET_SPORT]`. Details: `[T&CS_LINK]`

### Expiry-Led Variant

Uses time information without manipulative urgency.

Example structure:

Use `[OFFER_VALUE]` on `[TARGET_SPORT]` before `[EXPIRY]`. `[CTA]`. T&Cs: `[T&CS_LINK]`

### Product-Led Variant

Focuses on a sportsbook product such as accumulator, bet builder, live betting, or odds boost.

Example structure:

Try `[OFFER_MECHANIC]` on `[TARGET_EVENT]` with `[OFFER_VALUE]`. `[CTA]`. T&Cs: `[T&CS_LINK]`

## Offer Mechanic Copy Guidance

### Free Bet

Copy should clearly say:

- Free bet value.
- Qualification if needed.
- `[EXPIRY]` if relevant.
- `[T&CS_LINK]`.

Avoid:

- "Free money".
- "Guaranteed win".
- Hiding material stake or settlement rules if required.

### Bet-and-Get

Copy should clearly say:

- Required action.
- Reward.
- Time window.
- `[T&CS_LINK]`.

Avoid:

- Overloading the SMS with too many conditions.

### Odds Boost

Copy should clearly say:

- Boost availability.
- Event or market if confirmed.
- `[CTA]`.
- `[T&CS_LINK]`.

Avoid:

- Implying boosted odds guarantee profit.

### Accumulator Insurance

Copy should clearly say:

- Accumulator requirement if short enough.
- Refund or reward type.
- `[T&CS_LINK]`.

Avoid:

- Complex leg or odds explanations unless essential.
- Language that implies the bet is safe.

### Cashback

Copy should clearly say:

- Cashback percentage or value.
- Cap if required.
- Time window.
- `[T&CS_LINK]`.

Avoid:

- "Recover your losses".
- Loss-chasing framing.

### Bet Builder Boost

Copy should clearly say:

- Bet builder relevance.
- Boost or reward.
- Eligible event if confirmed.
- `[T&CS_LINK]`.

Avoid:

- Complex combinability explanations in SMS.

### Deposit Bonus

Copy should clearly say:

- Deposit action.
- Bonus value.
- `[MAX_BONUS_VALUE]` if relevant.
- `[T&CS_LINK]`.

Avoid:

- Implying deposit solves financial needs.
- Excessive pressure.

### Reload Offer

Copy should clearly say:

- Reload value.
- Time window.
- `[CTA]`.
- `[T&CS_LINK]`.

Avoid:

- Over-targeting frequent depositors.
- Aggressive urgency.

### Mission or Challenge

Copy should clearly say:

- Main action.
- Reward.
- Where to view details.

Avoid:

- Complex multi-step mission explanation in SMS.
- Repeat-action pressure.

### Loyalty Points

Copy should clearly say:

- Point reward or multiplier.
- Eligible action.
- `[T&CS_LINK]`.

Avoid:

- Unclear point value if that matters to customer understanding.

### VIP Bespoke Offer

Copy should be:

- Personal but not invasive.
- Calm.
- Clear.
- Suitable for manual review.

Avoid:

- Overly rich value claims.
- Automated mass-market language.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag or rewrite SMS copy that:

- Targets self-excluded users.
- Targets users with RG risk flags.
- Targets users in cooling-off periods.
- Encourages chasing losses.
- Refers to previous losses.
- Suggests betting solves financial problems.
- Suggests guaranteed profit.
- Uses "risk-free" unless approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Uses aggressive urgency.
- Uses emotional pressure.
- Uses manipulative reactivation wording.
- Hides material restrictions.
- Uses over-personalised behavioural triggers in a creepy way.
- Encourages excessive bet frequency.
- Encourages excessive accumulator leg counts without controls.
- Makes betting sound necessary to enjoy an event.

The skill must recommend `crm-sportsbook-rg-compliance-review` before launch.

## Commercial Guardrails

The skill should flag if SMS copy:

- Overstates `[OFFER_VALUE]`.
- Omits important restrictions.
- Makes bonus abuse easier.
- Attracts sharp or arb-sensitive exploitation.
- Creates unrealistic expectations.
- Makes qualification unclear.
- Makes reward unclear.
- Makes `[EXPIRY]` unclear.
- Creates support burden.
- Creates opt-out risk.
- Makes the campaign look like a broad giveaway when it is segment-restricted.

The copy should support:

- `[MINIMUM_STAKE]` clarity where required.
- `[MINIMUM_ODDS]` clarity where required.
- `[MAX_BONUS_VALUE]` clarity where required.
- `[ELIGIBLE_MARKETS]` clarity where required.
- `[EXPIRY]` clarity where required.
- Usage limit clarity where required.
- `[T&CS]` visibility.

## Brand & UX Guardrails

The skill should ensure SMS copy:

- Feels clear and human.
- Matches `[BRAND_TONE]`.
- Is not spammy unless the brand explicitly wants a high-energy tone.
- Does not stereotype `[TARGET_MARKET]`.
- Does not overuse slang.
- Does not use unclear betting jargon.
- Does not imply certainty of winning.
- Does not make personalisation feel invasive.
- Does not hide important restrictions.
- Has a clear next action.

## Localisation Rules

The skill must not invent local language, slang, cultural references, or tone.

If localisation is needed:

- Use `[TARGET_LANGUAGE]` if provided.
- Keep phrasing simple for translation.
- Avoid idioms unless supplied by the user.
- Avoid humour that may not translate.
- Mark uncertain localisation points as `[NEEDS CONFIRMATION]`.
- Recommend `crm-sportsbook-localisation` after SMS copy creation.

If the user asks for copy in a specific language, produce it only if `[TARGET_LANGUAGE]` is supplied at runtime.

## Personalisation Rules

The skill may use `[PERSONALISATION_TOKEN]` only when supplied.

Examples of runtime personalisation values may include first name, preferred sport, preferred event, offer value, expiry, or brand name. Represent any such value with `[PERSONALISATION_TOKEN]` unless the user supplies the exact CRM token syntax.

Safe personalisation:

- First name, if brand-approved.
- Preferred sport, if not overly sensitive.
- Eligible `[OFFER_VALUE]`.
- Event interest, if based on appropriate data.

Avoid:

- "Because you lost..."
- "You have not deposited..."
- "We saw you stopped betting..."
- "You usually bet high..."
- "You need this offer..."
- Anything that exposes sensitive behavioural profiling.

## A/B Testing Guidance

The skill should suggest one simple SMS A/B test when useful.

Possible tests:

- Value-led vs event-led.
- Simple `[CTA]` vs expiry-led.
- `[OFFER_VALUE]` framing vs product framing.
- Short copy vs slightly more explanatory copy.
- `[PERSONALISATION_TOKEN]` vs no personalisation.
- `[T&CS]` wording clarity test.

Each test should include:

- Hypothesis.
- Variant A.
- Variant B.
- Primary KPI.
- Guardrail metric.
- Decision rule.

## Market-Agnostic Design Rules

The skill must never assume:

- Local sport preferences.
- Local betting habits.
- Local channel preferences.
- Local language.
- Local slang.
- Local payment methods.
- Local regulations.
- Local cultural tone.
- Local competitor behaviour.
- Local event popularity.
- Local fixture schedule.
- Local operator conventions.

All copy-specific and market-specific details must come from:

- User-provided inputs.
- Existing skill outputs.
- Internal data.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts.

## Channel-Aware Design Rules

This skill is for SMS only.

For SMS:

- One message, one offer.
- Short and direct.
- Clear `[CTA]`.
- `[T&CS]` visible or linked.
- Low complexity.
- No aggressive pressure.
- No hidden conditions.
- No final launch without RG/compliance review.

For email:

- Do not write full email copy here.
- Recommend a future email-specific skill.

For push:

- Do not write push copy here.
- Recommend a future push-specific skill.

For onsite/inbox:

- Do not write full onsite/inbox copy here.
- Mention if supporting explanation may be needed.

For VIP outreach:

- SMS can be drafted only if SMS is an approved VIP channel.
- Recommend manual review.

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
# SMS Copy Output

## 1. SMS Campaign Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target segment: [TARGET_SEGMENT]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- CTA: [CTA]
- T&Cs: [T&CS_LINK]
- Character limit: required character limit supplied at runtime

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. SMS Variants
Provide 5-8 SMS variants unless the user requests a different number.

| Variant name | Copy | Character count | Copy angle | Best use case | Segment fit | Offer clarity | CTA clarity | T&C handling | Risk notes |
|---|---|---:|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |

## 6. Recommended Variant
- Recommended variant:
- Why this is strongest:
- Clarity:
- Channel fit:
- Segment fit:
- Offer understanding:
- RG safety:
- Commercial clarity:

## 7. Variants to Avoid or Rewrite
- Risky wording pattern:
- Safer rewrite:

## 8. RG & Compliance Notes
- Pressure risk:
- Loss-chasing risk:
- Misleading claim risk:
- T&C risk:
- Personalisation risk:
- Required review:

## 9. Commercial Notes
- Bonus cost clarity:
- Abuse risk:
- Sharp/arb risk:
- Qualification clarity:
- Reward clarity:
- Expiry clarity:

## 10. Localisation Notes
- Language confirmation:
- Tone confirmation:
- Translation risks:
- Slang/idiom risks:
- Recommended localisation review:

## 11. A/B Test Suggestion
- Hypothesis:
- Variant A:
- Variant B:
- Primary KPI:
- Guardrail metric:
- Decision rule:

## 12. Recommended Next Skills
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 13. Launch Readiness
- Ready for localisation and RG/compliance review / Needs missing inputs before copy finalisation / Needs offer simplification before copy finalisation / Needs T&C confirmation before copy finalisation / Not recommended based on current information:
- Rationale:
```

## Example User Request

"Write SMS copy for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`. The offer is `[OFFER_VALUE]` via `[OFFER_MECHANIC]` for `[TARGET_EVENT]`. CTA is `[CTA]`. T&Cs link is `[T&CS_LINK]`."

## Example Output

```markdown
# SMS Copy Output

## 1. SMS Campaign Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target segment: [TARGET_SEGMENT]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- CTA: [CTA]
- T&Cs: [T&CS_LINK]
- Character limit: required character limit supplied at runtime

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Target language: [TARGET_LANGUAGE]
- [CONFIRMED] Target segment: [TARGET_SEGMENT]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Offer mechanic: [OFFER_MECHANIC]
- [CONFIRMED] Offer value: [OFFER_VALUE]
- [CONFIRMED] CTA: [CTA]
- [CONFIRMED] T&Cs link: [T&CS_LINK]

## 3. Working Assumptions
- [ASSUMPTION] Character counts use visible placeholder characters and must be recalculated after runtime values, links, opt-out text, and personalisation tokens are expanded.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_EVENT]
- [NEEDS CONFIRMATION] [TARGET_TOURNAMENT]
- [NEEDS CONFIRMATION] [TARGET_FIXTURE]
- [NEEDS CONFIRMATION] [CUSTOMER_LIFECYCLE_STAGE]
- [NEEDS CONFIRMATION] [MINIMUM_STAKE]
- [NEEDS CONFIRMATION] [MINIMUM_ODDS]
- [NEEDS CONFIRMATION] [MAX_BONUS_VALUE]
- [NEEDS CONFIRMATION] [EXPIRY]
- [NEEDS CONFIRMATION] [ELIGIBLE_MARKETS]
- [NEEDS CONFIRMATION] [T&CS]
- [NEEDS CONFIRMATION] [BRAND_NAME]
- [NEEDS CONFIRMATION] [BRAND_TONE]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]
- [NEEDS CONFIRMATION] [OPT_OUT_TEXT]

## 5. SMS Variants
| Variant name | Copy | Character count | Copy angle | Best use case | Segment fit | Offer clarity | CTA clarity | T&C handling | Risk notes |
|---|---|---:|---|---|---|---|---|---|---|
| Value-led | [OFFER_VALUE] is available with [OFFER_MECHANIC]. [CTA]. T&Cs: [T&CS_LINK] | 74 | Value-led | Simple offer communication | Fits if [TARGET_SEGMENT] is eligible | Clear with confirmed [T&CS] | Clear | Link included | Recount after token expansion |
| Event-led | Use [OFFER_VALUE] with [OFFER_MECHANIC] for [TARGET_EVENT]. [CTA]. T&Cs: [T&CS_LINK] | 84 | Event-led | Event-relevant audience | Fits if event interest is confirmed | Clear with confirmed event | Clear | Link included | Event relevance needs confirmation |
| Expiry-led | Use [OFFER_VALUE] before [EXPIRY]. [CTA]. T&Cs: [T&CS_LINK] | 59 | Expiry-led | Time-limited offer | Fits if expiry is confirmed | Clear if expiry is real | Clear | Link included | Avoid urgent wording |
| Reactivation-safe | A [BRAND_NAME] offer is available: [OFFER_VALUE] with [OFFER_MECHANIC]. Details: [T&CS_LINK] | 92 | Soft return | Reactivation with safe profile | Neutral and low-pressure | Clear with details link | Indirect but acceptable | Link included | Requires RG suppressions |
| Product-led | Try [OFFER_MECHANIC] on [TARGET_SPORT] with [OFFER_VALUE]. [CTA]. T&Cs: [T&CS_LINK] | 83 | Product-led | Product trial or cross-sell | Fits if product relevance is confirmed | Clear if product is familiar | Clear | Link included | Product availability needs confirmation |

## 6. Recommended Variant
- Recommended variant: Value-led.
- Why this is strongest: It is short, clear, offer-focused, and does not depend on unconfirmed event relevance.
- Clarity: Strong.
- Channel fit: Strong for SMS.
- Segment fit: [NEEDS CONFIRMATION] Requires eligibility and opt-in confirmation.
- Offer understanding: Clear if [OFFER_VALUE], [OFFER_MECHANIC], and [T&CS_LINK] are approved.
- RG safety: Low-pressure and no loss framing.
- Commercial clarity: Needs final constraints in [T&CS].

## 7. Variants to Avoid or Rewrite
- Risky wording pattern: "Do not miss your chance to win back with [OFFER_VALUE]."
- Safer rewrite: "[OFFER_VALUE] is available with [OFFER_MECHANIC]. [CTA]. T&Cs: [T&CS_LINK]"

## 8. RG & Compliance Notes
- Pressure risk: Low in recommended variant.
- Loss-chasing risk: Avoid all loss or recovery references.
- Misleading claim risk: Do not use guaranteed profit or risk-free wording.
- T&C risk: [NEEDS CONFIRMATION] [T&CS] and [T&CS_LINK].
- Personalisation risk: Use [PERSONALISATION_TOKEN] only if approved.
- Required review: crm-sportsbook-rg-compliance-review before launch.

## 9. Commercial Notes
- Bonus cost clarity: [NEEDS CONFIRMATION] [MAX_BONUS_VALUE].
- Abuse risk: [NEEDS CONFIRMATION] Check segment restrictions.
- Sharp/arb risk: [NEEDS CONFIRMATION] Review if [OFFER_MECHANIC] is exploitable.
- Qualification clarity: [NEEDS CONFIRMATION] [MINIMUM_STAKE], [MINIMUM_ODDS], and [ELIGIBLE_MARKETS].
- Reward clarity: [CONFIRMED] [OFFER_VALUE], subject to approval.
- Expiry clarity: [NEEDS CONFIRMATION] [EXPIRY].

## 10. Localisation Notes
- Language confirmation: [TARGET_LANGUAGE]
- Tone confirmation: [BRAND_TONE]
- Translation risks: Keep sentence structure simple.
- Slang/idiom risks: Avoid unless supplied by the user.
- Recommended localisation review: crm-sportsbook-localisation.

## 11. A/B Test Suggestion
- Hypothesis: A shorter value-led SMS will produce clearer action than an event-led SMS when event affinity is not confirmed.
- Variant A: Value-led.
- Variant B: Event-led.
- Primary KPI: Click or eligible action conversion.
- Guardrail metric: Opt-out rate, complaint rate, and post-campaign RG flags.
- Decision rule: Choose the variant with better incremental conversion and no material guardrail deterioration.

## 12. Recommended Next Skills
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 13. Launch Readiness
- Needs T&C confirmation before copy finalisation.
- Rationale: [T&CS], [T&CS_LINK], [OPT_OUT_TEXT], suppression logic, and final character count need confirmation before launch.
```
