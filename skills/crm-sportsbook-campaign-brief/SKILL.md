---
name: crm-sportsbook-campaign-brief
description: Creates a complete market-agnostic sportsbook CRM campaign brief by synthesising market context, event opportunity, player segmentation, offer mechanics, channel logic, responsible-gaming guardrails, commercial rationale, testing, and measurement planning.
---

# CRM Sportsbook Campaign Brief

## Purpose

This skill creates a complete sportsbook CRM campaign brief.

It helps the CRM team turn inputs from market context, event opportunity, player segmentation, and offer mechanics into a structured campaign plan that can be reviewed, approved, executed, localised, tested, and measured.

The campaign brief should be practical enough for CRM execution and clear enough for product, compliance, trading, risk, BI, and management stakeholders.

This skill creates the campaign blueprint. It does not replace specialist skills for market context, segmentation, offer mechanics, final SMS copy, localisation, responsible-gaming review, journey design, A/B testing, or post-campaign analysis.

## Role in the Skill Pack

This is the central synthesis skill in the CRM sportsbook skill pack.

It usually runs after:

- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`, if the campaign is event-led.
- `crm-sportsbook-player-segmentation`
- `crm-sportsbook-offer-mechanics`

It may be selected by `crm-sportsbook-skill-router` when the user asks for a full campaign, execution-ready brief, campaign improvement, approval pack, or cross-functional campaign handoff.

It feeds:

- SMS copy.
- Localisation.
- RG/compliance review.
- Journey builder.
- A/B testing.
- Post-campaign analysis.

It should not replace specialist skills.

It should not:

- Invent missing market facts.
- Write final channel copy unless explicitly requested.
- Act as final compliance approval.
- Replace detailed offer mechanics review.
- Replace post-campaign analysis.

It creates the campaign blueprint that downstream skills and teams can use.

## When to Use

Use this skill when the CRM manager needs to:

- Create a full sportsbook CRM campaign brief.
- Turn a campaign idea into an execution-ready plan.
- Prepare a campaign for approval.
- Combine segment, event, offer, and channel logic.
- Plan an event-led campaign.
- Plan a reactivation campaign.
- Plan a retention campaign.
- Plan an activation campaign.
- Plan a VIP campaign.
- Plan a cross-sell campaign within sportsbook.
- Prepare copy direction for SMS or another future channel skill.
- Define exclusions and suppressions.
- Define `[SUCCESS_METRICS]`.
- Prepare A/B test direction.
- Prepare a campaign handoff to CRM operations, BI, product, trading, risk, or compliance.

## When Not to Use

Do not use this skill to:

- Create detailed market research from scratch.
- Select the full target audience from raw data without segmentation input.
- Design complex offer mechanics without offer mechanics input.
- Write final SMS copy unless explicitly requested.
- Draft legal `[T&CS]`.
- Give final compliance approval.
- Analyse campaign performance after launch.
- Override responsible-gaming suppressions.
- Invent fixture dates, market data, regulatory rules, or local preferences.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- SMS copy: `crm-sportsbook-sms-copy`.
- Localisation: `crm-sportsbook-localisation`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]` or segmentation output.
- `[OFFER_MECHANIC]` or offer mechanics output.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[CUSTOMER_VALUE_SEGMENT]`
- `[PREFERRED_BET_TYPE]`
- `[PRE_MATCH_OR_LIVE_PREFERENCE]`
- `[SINGLE_OR_ACCUMULATOR_PREFERENCE]`
- `[VIP_STATUS]`
- `[BONUS_SENSITIVITY]`
- `[SHARP_OR_ARB_RISK]`
- `[CHURN_RISK]`
- `[OFFER_VALUE]`
- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- `[EXPIRY]`
- `[ELIGIBLE_MARKETS]`
- `[T&CS]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- `[SUCCESS_METRICS]`

### Advanced optional inputs

- Market context output.
- Event opportunity output.
- Player segmentation output.
- Offer mechanics output.
- Historical campaign performance.
- Segment size.
- Expected uptake.
- Expected incremental revenue.
- Bonus cost limit.
- GGR target.
- NGR target.
- Turnover target.
- Margin by sport or market.
- Product availability.
- Trading restrictions.
- Risk restrictions.
- VIP approval rules.
- Bonus abuse restrictions.
- Channel frequency caps.
- Customer communication calendar.
- Control group requirement.
- BI measurement framework.
- Runtime compliance sign-off process.
- Creative or brand guidelines.
- Landing page or inbox support.
- Campaign launch date and time.
- Campaign end date and time.
- Reminder rules.
- Exclusion rules.
- Suppression list logic.

## Output

The skill should produce:

- Campaign summary.
- Campaign objective.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Target audience definition.
- Exclusion and suppression logic.
- Customer insight.
- Sport/event rationale.
- Offer design summary.
- Commercial rationale.
- Customer value proposition.
- Channel plan.
- Copy direction.
- Personalisation logic.
- `[T&CS]` summary.
- Responsible-gaming and compliance notes.
- Commercial risk notes.
- Operational requirements.
- A/B test recommendation.
- `[SUCCESS_METRICS]`.
- Launch checklist.
- Recommended next skills.

## Workflow

1. Identify `[CAMPAIGN_OBJECTIVE]`.
2. Identify `[TARGET_MARKET]` as runtime context only.
3. Identify `[TARGET_CHANNEL]`.
4. Load and apply `crm-sportsbook-shared-principles`.
5. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
6. Review available `crm-sportsbook-market-context` output.
7. Review available `crm-sportsbook-event-opportunity` output, if relevant.
8. Review available `crm-sportsbook-player-segmentation` output.
9. Review available `crm-sportsbook-offer-mechanics` output.
10. List all confirmed inputs as `[CONFIRMED]`.
11. Separate confirmed inputs from assumptions.
12. Mark missing critical information as `[NEEDS CONFIRMATION]`.
13. Define the campaign objective in operational CRM terms.
14. Define the target segment and suppression rules.
15. Define the customer insight.
16. Define the sport/event rationale if applicable.
17. Summarise `[OFFER_MECHANIC]` and required constraints.
18. Check that the offer fits `[TARGET_SEGMENT]`, `[TARGET_CHANNEL]`, and `[CAMPAIGN_OBJECTIVE]`.
19. Define the customer value proposition.
20. Define the channel approach.
21. Define copy direction, not final copy unless explicitly requested.
22. Define personalisation logic.
23. Define `[T&CS]` handling.
24. Identify responsible-gaming and compliance risks.
25. Identify commercial and operational risks.
26. Define `[SUCCESS_METRICS]` and measurement window.
27. Recommend A/B test direction.
28. Produce a launch checklist.
29. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[CAMPAIGN_OBJECTIVE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If market context is missing, recommend running `crm-sportsbook-market-context`.
- If the campaign is event-led but event context is missing, recommend running `crm-sportsbook-event-opportunity`.
- If `[TARGET_SEGMENT]` is missing or weakly defined, recommend running `crm-sportsbook-player-segmentation`.
- If `[OFFER_MECHANIC]` is missing or unclear, recommend running `crm-sportsbook-offer-mechanics`.
- If `[TARGET_CHANNEL]` is SMS, keep the campaign concept simple enough to explain in one short message.
- If the offer mechanic is too complex for SMS, flag it as `[RISK]` and recommend simplification or supporting landing page or `[T&CS]`.
- If `[CAMPAIGN_OBJECTIVE]` is activation, focus on a clear first action.
- If `[CAMPAIGN_OBJECTIVE]` is retention, avoid over-incentivising customers who would likely bet anyway.
- If `[CAMPAIGN_OBJECTIVE]` is reactivation, avoid emotional pressure and exclude RG-risk or recently heavy-losing users.
- If the campaign is event-led, make sure `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, `[TARGET_FIXTURE]`, or `[TARGET_SPORT]` is relevant to `[TARGET_SEGMENT]`.
- If `[CAMPAIGN_OBJECTIVE]` is VIP engagement, require manual review, exposure controls, and RG/compliance review.
- If `[BONUS_SENSITIVITY]` is high, require stricter offer constraints.
- If `[SHARP_OR_ARB_RISK]` is present, recommend exclusion, manual review, or low-exposure mechanics.
- If the offer has open-ended exposure, require `[MAX_BONUS_VALUE]` or equivalent cap.
- If `[T&CS]` are unclear, mark them as `[NEEDS CONFIRMATION]`.
- If `[REGULATORY_NOTES]` are missing, do not make compliance claims.
- If `[SUCCESS_METRICS]` are missing, recommend a default KPI framework without inventing targets.
- If the campaign uses personalisation, make sure it does not feel invasive or imply sensitive profiling.
- If the campaign creates RG, compliance, or commercial risk, recommend `crm-sportsbook-rg-compliance-review`.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, and `crm-sportsbook-offer-mechanics`.
- Normally run after this skill: `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, measurement principles, and final campaign quality checklist.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Sport relevance.
- Event relevance.
- League, tournament, team, or fixture relevance if provided.
- Pre-match vs live betting behaviour.
- Single bet vs accumulator behaviour.
- Bet builder relevance.
- Odds boost suitability.
- Free bet suitability.
- Cashback suitability.
- Accumulator insurance suitability.
- Deposit or reload suitability.
- VIP suitability.
- Bonus sensitivity.
- Sharp or arb-sensitive exposure.
- Recreational user relevance.
- Churn risk.
- Lifecycle stage.
- Average stake.
- Deposit behaviour.
- Bonus history.
- Product availability.
- Market availability.
- Timing and settlement risks.
- Trading restrictions.
- Margin protection.
- Bonus cost.
- Incrementality.
- Frequency caps.
- Channel opt-in.
- Campaign fatigue.
- Post-campaign RG monitoring.

## Campaign Objective Types

Support the following campaign objectives.

### Activation

Use for:

- Registered but not deposited.
- Deposited but not bet.
- First sport or product engagement.
- First bet builder or live bet trial.

Campaign brief should focus on:

- Simple first action.
- Low-friction offer.
- Clear CTA.
- Clear eligibility.
- No aggressive pressure.

### Retention

Use for:

- Active customers.
- Declining activity.
- Event-relevant customers.
- Recreational customers with safe engagement profile.

Campaign brief should focus on:

- Incrementality.
- Avoiding over-incentivising natural activity.
- Relevant event or product angle.
- Controlled reward value.

### Reactivation

Use for:

- Dormant customers.
- Previously active customers with safe profile.
- Customers past a defined inactivity threshold.

Campaign brief should focus on:

- Soft return message.
- Clear value.
- No emotional manipulation.
- No loss recovery framing.
- Strong suppression logic.

### Event Activation

Use for:

- Major event.
- Fixture-specific activation.
- Tournament journey.
- Product-event tie-in.

Campaign brief should focus on:

- Event relevance.
- Segment-event fit.
- Timing.
- Product availability.
- Offer simplicity.
- Frequency caps.

### Cross-Sell Within Sportsbook

Use for:

- Moving single bettors to accumulators.
- Moving pre-match users to live betting.
- Moving sport users to another sport.
- Introducing bet builder.
- Introducing loyalty mechanics.

Campaign brief should focus on:

- Education if needed.
- Simple mechanic.
- Low-risk trial.
- Relevance to existing behaviour.

### VIP Engagement

Use for:

- Approved VIP engagement.
- High-value event activation.
- Bespoke rewards.

Campaign brief should focus on:

- Manual review.
- Exposure cap.
- Safe engagement profile.
- Personal but not invasive tone.
- RG/compliance review.

## Campaign Brief Components

The skill must include these components in the output.

### Campaign Name

Create a practical internal campaign name using placeholders.

Avoid real market or event names unless supplied by the user.

### Campaign Objective

Explain the business goal and customer action.

### Target Segment

Summarise:

- Inclusion rules.
- Exclusion rules.
- Suppression rules.
- Segment rationale.

### Customer Insight

Explain why `[TARGET_SEGMENT]` should care.

The insight must be based on confirmed inputs or clearly labelled assumptions.

### Event or Sport Rationale

If event-led, explain why `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, `[TARGET_FIXTURE]`, or `[TARGET_SPORT]` matters.

Do not invent event facts.

### Offer Design Summary

Summarise:

- `[OFFER_MECHANIC]`
- Qualification.
- Reward.
- `[EXPIRY]`
- `[ELIGIBLE_MARKETS]`
- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- Usage limits.
- Key restrictions.

### Commercial Rationale

Explain:

- Expected behaviour change.
- Why this is likely incremental.
- How cost is controlled.
- How abuse risk is controlled.
- How margin is protected.

Do not invent forecasts unless data is provided.

### Customer Value Proposition

Explain the offer in simple customer language.

Do not write final SMS unless requested.

### Channel Plan

Explain how `[TARGET_CHANNEL]` should be used.

For SMS:

- One message, one offer.
- Simple CTA.
- Short explanation.
- `[T&CS]` link or short cue.
- Avoid complex mechanics.
- Avoid aggressive urgency.

### Copy Direction

Provide:

- Main message angle.
- Secondary angle.
- Words or phrases to avoid.
- Tone notes.
- CTA direction.

### Personalisation Logic

Explain:

- Which fields may be personalised.
- Which personalisation is safe.
- Which personalisation may feel invasive.
- Which personalisation should be avoided.

### Exclusions and Suppressions

Include:

- Self-exclusion.
- RG risk flags.
- Cooling-off.
- Channel opt-out.
- Compliance/account restrictions.
- Fraud/AML restrictions.
- Bonus abuse restrictions where relevant.
- Recently heavy-losing users where relevant.
- Frequency cap exclusions.

### RG and Compliance Notes

Flag:

- Missing `[REGULATORY_NOTES]`.
- Risky wording.
- Risky mechanic.
- Targeting risks.
- `[T&CS]` risks.
- Required review.

### Operational Requirements

Include:

- Audience build.
- Offer configuration.
- Promo code or token setup if relevant.
- `[T&CS]` page or support article.
- Tracking links.
- Control group.
- QA.
- Launch timing.
- `[EXPIRY]` handling.
- Reporting setup.

### Measurement Plan

Include:

- Primary KPI.
- Secondary KPIs.
- Guardrail metrics.
- Measurement window.
- Control group recommendation.
- Incrementality notes.

### A/B Test Direction

Recommend one practical test.

Examples:

- `[OFFER_VALUE]` test.
- CTA test.
- `[TARGET_EVENT]` angle vs value angle.
- `[EXPIRY]` framing test.
- Segment split test.
- `[OFFER_MECHANIC]` test.

### Launch Checklist

Create a practical checklist for launch readiness.

## Market-Agnostic Design Rules

The skill must never assume:

- Local sport preferences.
- Local betting habits.
- Local channel preferences.
- Local language.
- Local payment methods.
- Local regulations.
- Local cultural tone.
- Local competitor behaviour.
- Local player value thresholds.
- Local event popularity.
- Local fixture schedule.
- Local holidays.

All campaign-specific and market-specific details must come from:

- User-provided inputs.
- Internal data.
- Existing skill outputs.
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

- Keep the campaign simple.
- Recommend one offer only.
- Avoid multi-step mechanics unless extremely simple.
- Require clear CTA.
- Require `[T&CS]` handling.
- Flag mechanics that cannot be explained clearly.
- Avoid aggressive urgency.
- Feed into `crm-sportsbook-sms-copy`.

For email:

- Note that detailed email execution should be handled by a future email-specific skill.
- Campaign brief may include email direction, but not final email copy unless explicitly requested.

For push:

- Note that detailed push execution should be handled by a future push-specific skill.
- Push direction should remain short, immediate, and non-manipulative.

For onsite/inbox:

- Consider whether the campaign needs supporting creative, landing page, or inbox explanation.

For VIP outreach:

- Require manual review, careful tone, exposure cap, and RG/compliance review.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag or reject campaign briefs that:

- Target self-excluded users.
- Target users with RG risk flags.
- Target users in cooling-off periods.
- Encourage chasing losses.
- Use recent losses as the reason for the incentive.
- Frame betting as a financial solution.
- Imply guaranteed profit.
- Use "risk-free" unless explicitly approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Hide key restrictions.
- Use aggressive urgency.
- Use emotionally manipulative reactivation language.
- Encourage excessive bet frequency.
- Encourage excessive accumulator leg counts without controls.
- Use personalisation that feels invasive or sensitive.

The skill must always recommend `crm-sportsbook-rg-compliance-review` before campaign launch.

## Commercial Guardrails

The skill should protect against:

- Excessive bonus cost.
- Open-ended exposure.
- Low incrementality.
- Over-incentivising natural activity.
- Bonus abuse.
- Arbitrage exploitation.
- Sharp-player exposure.
- VIP over-costing.
- Unclear qualification rules.
- Unclear reward rules.
- Complex `[T&CS]`.
- Product unavailability.
- Trading restrictions.
- Operational failure.
- Poor measurement design.

The skill should recommend controls such as:

- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- Maximum qualifying stake supplied at runtime.
- Eligible sports.
- `[ELIGIBLE_MARKETS]`
- `[EXPIRY]`
- One use per customer.
- Frequency caps.
- Segment restrictions.
- Exclusion logic.
- Manual review.
- Control group.

Do not estimate commercial impact unless data is provided or the user explicitly asks for assumptions.

## Brand & UX Guardrails

The skill should ensure:

- Campaign is easy to explain.
- Customer value is obvious.
- Offer is not misleading.
- Copy angle is not too aggressive.
- `[T&CS]` are accessible.
- CTA is clear.
- Personalisation is not creepy.
- Tone respects `[BRAND_TONE]`.
- The campaign does not stereotype `[TARGET_MARKET]`.
- The campaign does not imply certainty of winning.
- The campaign does not feel spammy or casino-like unless brand-approved.

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
# Campaign Brief

## 1. Campaign Summary
- Campaign name:
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Campaign timing:
- Launch readiness:

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Customer Insight
- Insight:
- Evidence:
- Confidence:

## 6. Target Segment
- Inclusion criteria:
- Exclusion criteria:
- Suppression rules:
- Segment rationale:

## 7. Event / Sport Rationale
- Why this sport/event matters:
- Why it fits the segment:
- Why timing matters:
- What needs confirmation:

## 8. Offer Design
- Offer mechanic: [OFFER_MECHANIC]
- Customer-facing value: [OFFER_VALUE]
- Qualification:
- Reward:
- Minimum stake: [MINIMUM_STAKE]
- Minimum odds: [MINIMUM_ODDS]
- Eligible sports/markets: [TARGET_SPORT] / [ELIGIBLE_MARKETS]
- Expiry: [EXPIRY]
- Max bonus/reward: [MAX_BONUS_VALUE]
- Usage limits:
- Key restrictions:
- T&C notes: [T&CS]

## 9. Commercial Rationale
- Expected behaviour change:
- Incrementality logic:
- Cost-control logic:
- Margin protection:
- Abuse prevention:
- Main commercial risk:

## 10. Customer Value Proposition
- Simple customer-friendly explanation:

## 11. Channel Plan
- Channel: [TARGET_CHANNEL]
- Channel role:
- Timing:
- CTA direction:
- T&C handling:
- SMS suitability if applicable:
- Complexity risk:

## 12. Copy Direction
- Main copy angle:
- Alternative copy angle:
- Tone: [BRAND_TONE]
- Words/claims to avoid:
- CTA guidance:

## 13. Personalisation Logic
- Safe personalisation:
- Personalisation to avoid:
- Required data fields:
- Privacy/UX risks:

## 14. RG & Compliance Notes
- RG suppression requirements:
- Compliance unknowns: [REGULATORY_NOTES]
- Copy risks:
- Offer risks:
- Targeting risks:
- T&C risks: [T&CS]
- Required review:

## 15. Commercial Risk Review
- Bonus cost risk:
- Margin risk:
- Bonus abuse risk: [BONUS_SENSITIVITY]
- Sharp/arb risk: [SHARP_OR_ARB_RISK]
- Low incrementality risk:
- Operational risk:

## 16. Operational Requirements
- Audience build:
- Offer setup:
- Tracking:
- T&C page/support:
- QA:
- Launch timing:
- Expiry handling: [EXPIRY]
- Reporting setup:
- Owner dependencies:

## 17. A/B Test Recommendation
- Hypothesis:
- Variant A:
- Variant B:
- Primary KPI:
- Guardrail metrics:
- Measurement window:
- Decision rule:

## 18. Success Metrics
- Primary KPI: [SUCCESS_METRICS]
- Secondary KPIs:
- Commercial KPIs:
- RG/UX guardrail metrics:
- Measurement window:
- Control group recommendation:

## 19. Launch Checklist
- Market context checked:
- Event details checked:
- Segment logic checked:
- Suppressions applied:
- Offer configured:
- T&Cs approved:
- Copy reviewed:
- RG/compliance reviewed:
- Tracking ready:
- Control group ready:
- QA complete:
- Reporting ready:

## 20. Recommended Next Skills
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 21. Final Recommendation
- Ready to proceed with assumptions / Needs missing inputs before copy creation / Needs offer/commercial approval before copy creation / Needs RG/compliance input before campaign design / Not recommended based on current information:
- Rationale:
```

## Example User Request

"Create a campaign brief for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`, the channel is `[TARGET_CHANNEL]`, and the offer mechanic is `[OFFER_MECHANIC]`. The campaign is linked to `[TARGET_EVENT]`."

## Example Output

```markdown
# Campaign Brief

## 1. Campaign Summary
- Campaign name: [TARGET_MARKET] [CAMPAIGN_OBJECTIVE] [TARGET_CHANNEL] brief for [TARGET_SEGMENT].
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Offer mechanic: [OFFER_MECHANIC]
- Campaign timing: [NEEDS CONFIRMATION]
- Launch readiness: Needs missing inputs before copy creation.

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Target segment: [TARGET_SEGMENT]
- [CONFIRMED] Offer mechanic: [OFFER_MECHANIC]
- [CONFIRMED] Event context: [TARGET_EVENT]

## 3. Working Assumptions
- [ASSUMPTION] No local sport preference, local event popularity, fixture timing, product availability, or regulatory rule is assumed unless supplied by the user or confirmed through approved research.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_TOURNAMENT]
- [NEEDS CONFIRMATION] [TARGET_FIXTURE]
- [NEEDS CONFIRMATION] [CUSTOMER_LIFECYCLE_STAGE]
- [NEEDS CONFIRMATION] [CUSTOMER_VALUE_SEGMENT]
- [NEEDS CONFIRMATION] [PREFERRED_BET_TYPE]
- [NEEDS CONFIRMATION] [PRE_MATCH_OR_LIVE_PREFERENCE]
- [NEEDS CONFIRMATION] [SINGLE_OR_ACCUMULATOR_PREFERENCE]
- [NEEDS CONFIRMATION] [VIP_STATUS]
- [NEEDS CONFIRMATION] [BONUS_SENSITIVITY]
- [NEEDS CONFIRMATION] [SHARP_OR_ARB_RISK]
- [NEEDS CONFIRMATION] [CHURN_RISK]
- [NEEDS CONFIRMATION] [OFFER_VALUE]
- [NEEDS CONFIRMATION] [MINIMUM_STAKE]
- [NEEDS CONFIRMATION] [MINIMUM_ODDS]
- [NEEDS CONFIRMATION] [MAX_BONUS_VALUE]
- [NEEDS CONFIRMATION] [EXPIRY]
- [NEEDS CONFIRMATION] [ELIGIBLE_MARKETS]
- [NEEDS CONFIRMATION] [T&CS]
- [NEEDS CONFIRMATION] [BRAND_TONE]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]
- [NEEDS CONFIRMATION] [SUCCESS_METRICS]

## 5. Customer Insight
- Insight: [TARGET_SEGMENT] may respond when [OFFER_MECHANIC] is relevant to [CAMPAIGN_OBJECTIVE] and tied clearly to [TARGET_EVENT].
- Evidence: [NEEDS CONFIRMATION] Requires segmentation, sport/event affinity, and historical campaign data.
- Confidence: Provisional.

## 6. Target Segment
- Inclusion criteria: Customers in [TARGET_SEGMENT] with valid [TARGET_CHANNEL] eligibility, confirmed relevance to [TARGET_EVENT] or [TARGET_SPORT], and no suppression flags.
- Exclusion criteria: Self-excluded users, RG-risk users, cooling-off users, opted-out users, compliance-restricted users, bonus-abuse risk users where relevant, and sharp or arb-sensitive users where the mechanic is exploitable.
- Suppression rules: Apply shared suppression rules and any [REGULATORY_NOTES].
- Segment rationale: [RECOMMENDATION] Validate with crm-sportsbook-player-segmentation before launch.

## 7. Event / Sport Rationale
- Why this sport/event matters: [NEEDS CONFIRMATION] Requires confirmed event relevance.
- Why it fits the segment: [NEEDS CONFIRMATION] Confirm sport, event, bet type, or product affinity.
- Why timing matters: [NEEDS CONFIRMATION] Confirm event timing and campaign window.
- What needs confirmation: Product availability, market availability, and event details.

## 8. Offer Design
- Offer mechanic: [OFFER_MECHANIC]
- Customer-facing value: [OFFER_VALUE]
- Qualification: Eligible customers complete the approved qualifying action.
- Reward: [OFFER_VALUE]
- Minimum stake: [MINIMUM_STAKE]
- Minimum odds: [MINIMUM_ODDS]
- Eligible sports/markets: [TARGET_SPORT] / [ELIGIBLE_MARKETS]
- Expiry: [EXPIRY]
- Max bonus/reward: [MAX_BONUS_VALUE]
- Usage limits: One use per eligible customer unless confirmed otherwise.
- Key restrictions: Suppression rules, product availability, and eligibility rules.
- T&C notes: [T&CS]

## 9. Commercial Rationale
- Expected behaviour change: [RECOMMENDATION] Encourage the campaign action linked to [CAMPAIGN_OBJECTIVE].
- Incrementality logic: [NEEDS CONFIRMATION] Use a control group and compare against expected natural activity.
- Cost-control logic: [RECOMMENDATION] Use [MAX_BONUS_VALUE], [MINIMUM_STAKE], [MINIMUM_ODDS], [ELIGIBLE_MARKETS], and [EXPIRY].
- Margin protection: [NEEDS CONFIRMATION] Confirm market and product constraints.
- Abuse prevention: [RISK] Review [BONUS_SENSITIVITY] and [SHARP_OR_ARB_RISK].
- Main commercial risk: Bonus cost or low incrementality if segment fit is weak.

## 10. Customer Value Proposition
- Simple customer-friendly explanation: Eligible customers in [TARGET_SEGMENT] can receive [OFFER_VALUE] through [OFFER_MECHANIC] for qualifying activity linked to [TARGET_EVENT], subject to [T&CS].

## 11. Channel Plan
- Channel: [TARGET_CHANNEL]
- Channel role: Deliver the primary campaign prompt if eligibility and opt-in are confirmed.
- Timing: [NEEDS CONFIRMATION]
- CTA direction: One clear next action.
- T&C handling: Reference [T&CS] clearly.
- SMS suitability if applicable: [RECOMMENDATION] Use one message, one offer, one CTA.
- Complexity risk: [RISK] Simplify if [OFFER_MECHANIC] cannot be explained clearly.

## 12. Copy Direction
- Main copy angle: Clear value linked to [TARGET_EVENT] or [CAMPAIGN_OBJECTIVE].
- Alternative copy angle: Simple offer-led value.
- Tone: [BRAND_TONE]
- Words/claims to avoid: Guaranteed profit, risk-free unless approved, chasing-loss wording, financial-solution claims, and aggressive urgency.
- CTA guidance: Direct eligible customers to the approved campaign action.

## 13. Personalisation Logic
- Safe personalisation: [TARGET_EVENT], [TARGET_SPORT], eligibility, and offer value when confirmed.
- Personalisation to avoid: Losses, financial stress, sensitive attributes, and overly specific behavioural pressure.
- Required data fields: Segment eligibility, channel opt-in, suppression status, offer eligibility, and product availability.
- Privacy/UX risks: [RISK] Avoid personalisation that feels invasive.

## 14. RG & Compliance Notes
- RG suppression requirements: Self-exclusion, RG risk flags, cooling-off, channel opt-out, and recent risky behaviour exclusions.
- Compliance unknowns: [REGULATORY_NOTES]
- Copy risks: Aggressive urgency, guaranteed profit, risk-free wording, or hidden restrictions.
- Offer risks: Open-ended exposure or unclear qualification.
- Targeting risks: Recent heavy-loss targeting, bonus abuse, sharp or arb-sensitive exposure.
- T&C risks: [T&CS]
- Required review: crm-sportsbook-rg-compliance-review before launch.

## 15. Commercial Risk Review
- Bonus cost risk: [RISK] [OFFER_VALUE] and [MAX_BONUS_VALUE] require confirmation.
- Margin risk: [RISK] [MINIMUM_ODDS] and [ELIGIBLE_MARKETS] require confirmation.
- Bonus abuse risk: [RISK] [BONUS_SENSITIVITY] requires confirmation.
- Sharp/arb risk: [RISK] [SHARP_OR_ARB_RISK] requires confirmation.
- Low incrementality risk: [NEEDS CONFIRMATION] Requires control group or historical baseline.
- Operational risk: [NEEDS CONFIRMATION] Confirm setup, tracking, settlement, and expiry handling.

## 16. Operational Requirements
- Audience build: Build [TARGET_SEGMENT] with suppressions.
- Offer setup: Configure [OFFER_MECHANIC], [OFFER_VALUE], [MINIMUM_STAKE], [MINIMUM_ODDS], [MAX_BONUS_VALUE], [ELIGIBLE_MARKETS], and [EXPIRY].
- Tracking: Campaign ID, offer ID, channel tracking, and conversion tracking.
- T&C page/support: [T&CS]
- QA: Audience, offer, links, tracking, copy, suppressions, and expiry.
- Launch timing: [NEEDS CONFIRMATION]
- Expiry handling: [EXPIRY]
- Reporting setup: [SUCCESS_METRICS], control group, and guardrail metrics.
- Owner dependencies: CRM, product, trading, risk, BI, and compliance owners.

## 17. A/B Test Recommendation
- Hypothesis: A clearer [OFFER_MECHANIC] explanation will improve eligible action conversion without increasing RG or opt-out risk.
- Variant A: [TARGET_EVENT]-led angle.
- Variant B: [OFFER_VALUE]-led angle.
- Primary KPI: [SUCCESS_METRICS]
- Guardrail metrics: Opt-out rate, complaint rate, bonus cost, and post-campaign RG flags.
- Measurement window: [NEEDS CONFIRMATION]
- Decision rule: Choose the variant with better incremental conversion and no material guardrail deterioration.

## 18. Success Metrics
- Primary KPI: [SUCCESS_METRICS]
- Secondary KPIs: Delivery, engagement, bet conversion, bonus uptake, turnover, GGR, NGR, and retention.
- Commercial KPIs: Bonus cost, incremental revenue, margin impact, and cost per incremental action.
- RG/UX guardrail metrics: Opt-out rate, complaint rate, and post-campaign RG flags.
- Measurement window: [NEEDS CONFIRMATION]
- Control group recommendation: [RECOMMENDATION] Hold out an eligible control group if feasible.

## 19. Launch Checklist
- Market context checked: [NEEDS CONFIRMATION]
- Event details checked: [NEEDS CONFIRMATION]
- Segment logic checked: [NEEDS CONFIRMATION]
- Suppressions applied: [NEEDS CONFIRMATION]
- Offer configured: [NEEDS CONFIRMATION]
- T&Cs approved: [NEEDS CONFIRMATION]
- Copy reviewed: [NEEDS CONFIRMATION]
- RG/compliance reviewed: [NEEDS CONFIRMATION]
- Tracking ready: [NEEDS CONFIRMATION]
- Control group ready: [NEEDS CONFIRMATION]
- QA complete: [NEEDS CONFIRMATION]
- Reporting ready: [NEEDS CONFIRMATION]

## 20. Recommended Next Skills
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-ab-testing

## 21. Final Recommendation
- Needs missing inputs before copy creation.
- Rationale: Offer constraints, [T&CS], [REGULATORY_NOTES], segment eligibility, suppression logic, event details, and [SUCCESS_METRICS] must be confirmed before execution.
```
