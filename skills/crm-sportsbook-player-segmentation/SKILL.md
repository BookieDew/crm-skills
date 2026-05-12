---
name: crm-sportsbook-player-segmentation
description: Defines, evaluates, refines, and safely applies market-agnostic sportsbook CRM player segments using runtime customer, campaign, channel, event, responsible-gaming, and commercial context.
---

# CRM Sportsbook Player Segmentation

## Purpose

This skill helps sportsbook CRM teams define and evaluate player segments for sportsbook CRM campaigns.

It helps the CRM team decide:

- Which customers should be targeted.
- Which customers should be excluded.
- Which segment is most relevant for `[CAMPAIGN_OBJECTIVE]`.
- Which segment fits `[TARGET_EVENT]`, `[TARGET_SPORT]`, offer direction, and `[TARGET_CHANNEL]`.
- Which responsible-gaming, commercial, or abuse risks exist.
- What segmentation logic should be passed into offer mechanics, campaign brief, copy, journey, and testing skills.

This skill creates targeting and exclusion logic. It does not write final copy or final campaign briefs.

## Role in the Skill Pack

This skill usually runs after:

- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`, if the campaign is event-led.

It may be selected by `crm-sportsbook-skill-router` when the user asks for audience definition, targeting logic, eligibility, suppression, segment comparison, or segment safety review.

It translates customer data and campaign goals into actionable CRM targeting logic.

It informs:

- Offer mechanics.
- Campaign brief.
- SMS copy direction.
- Localisation.
- RG/compliance review.
- Journey builder.
- A/B testing.
- Post-campaign analysis.

It should not write final copy or final campaign briefs by itself. It creates the targeting and exclusion logic that other skills use.

## When to Use

Use this skill when the CRM manager needs to:

- Define a target segment for a sportsbook campaign.
- Validate whether a proposed segment is suitable.
- Create segment logic for personalised offers.
- Compare possible campaign audiences.
- Identify suppression rules.
- Separate activation, retention, reactivation, VIP, recreational, bonus-sensitive, sharp, or dormant users.
- Match segments to sports, events, bet types, or offer mechanics.
- Create safe reactivation audiences.
- Build SMS-eligible audiences.
- Prepare segmentation logic for campaign brief creation.
- Prepare segment splits for A/B testing.
- Analyse whether a campaign target group creates RG or commercial risk.

## When Not to Use

Do not use this skill to:

- Write final SMS copy.
- Design the complete offer mechanic.
- Build the full campaign brief.
- Analyse final campaign results.
- Decide legal eligibility without compliance input.
- Override responsible-gaming suppressions.
- Make unsupported assumptions about a specific market.
- Create segments based on sensitive or prohibited attributes.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
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
- `[TARGET_CHANNEL]` if known.
- Available customer data or proposed `[TARGET_SEGMENT]`.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[CUSTOMER_VALUE_SEGMENT]`
- `[PREFERRED_BET_TYPE]`
- `[PRE_MATCH_OR_LIVE_PREFERENCE]`
- `[SINGLE_OR_ACCUMULATOR_PREFERENCE]`
- `[VIP_STATUS]`
- `[BONUS_SENSITIVITY]`
- `[SHARP_OR_ARB_RISK]`
- `[CHURN_RISK]`
- `[COMMUNICATION_OPT_IN_STATUS]`
- `[RG_RISK_STATUS]`
- `[SELF_EXCLUSION_STATUS]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`

### Advanced optional inputs

- Registration date.
- Last active date.
- Last deposit date.
- Last bet date.
- Deposit frequency.
- Average deposit.
- Average stake.
- Bet frequency.
- Turnover.
- GGR.
- NGR.
- Bonus uptake history.
- Bonus cost history.
- Bonus abuse markers.
- Sharp or arb sensitivity.
- Preferred sport.
- Preferred league.
- Preferred team.
- Preferred market type.
- Live betting share.
- Accumulator share.
- Bet builder usage.
- Free bet usage.
- Odds boost usage.
- Cashback usage.
- Device preference.
- Channel engagement history.
- Opt-in status by channel.
- Previous campaign response.
- Complaints history.
- RG interactions.
- Cooling-off history.
- Fraud, AML, or account status restrictions.
- Internal customer value model.
- Predictive churn model.
- Propensity model.
- Control group requirements.

## Output

The skill should produce:

- Segmentation summary.
- Confirmed segmentation inputs.
- Working assumptions.
- Items needing confirmation.
- Recommended target segment.
- Secondary segment options.
- Exclusion and suppression rules.
- Segment rationale.
- Segment-event fit.
- Segment-channel fit.
- Segment-offer fit.
- RG risk notes.
- Commercial risk notes.
- Data quality notes.
- Recommended next skills.

## Workflow

1. Identify `[CAMPAIGN_OBJECTIVE]`.
2. Identify `[TARGET_MARKET]` and treat it as runtime context only.
3. Load and apply `crm-sportsbook-shared-principles`.
4. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
5. Use `crm-sportsbook-market-context` output when market context is available.
6. Use `crm-sportsbook-event-opportunity` output when the campaign is tied to `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, or `[TARGET_SPORT]`.
7. Identify the proposed `[TARGET_SEGMENT]`, if provided.
8. List all confirmed customer and campaign inputs as `[CONFIRMED]`.
9. Separate confirmed facts from assumptions.
10. Mark missing segmentation data as `[NEEDS CONFIRMATION]`.
11. Check mandatory exclusions:
    - Self-excluded users.
    - Users with active RG restrictions.
    - Users in cooling-off period.
    - Users opted out of `[TARGET_CHANNEL]`.
    - Users blocked by compliance, AML, fraud, or account status rules.
12. Evaluate the segment against `[CAMPAIGN_OBJECTIVE]`.
13. Evaluate segment fit with `[TARGET_SPORT]`, `[TARGET_EVENT]`, or betting moment if provided.
14. Evaluate channel eligibility and suitability.
15. Evaluate offer suitability at a directional level.
16. Identify commercial risks:
    - Bonus abuse.
    - Over-incentivising.
    - Low incrementality.
    - Sharp or arb exposure.
    - High bonus cost.
17. Identify RG and compliance risks.
18. Recommend target segment and exclusions.
19. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[TARGET_SEGMENT]` is missing, propose a segmentation framework rather than inventing a final audience.
- If `[CAMPAIGN_OBJECTIVE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is SMS, only include users with valid SMS opt-in or mark opt-in as `[NEEDS CONFIRMATION]`.
- If `[COMMUNICATION_OPT_IN_STATUS]` is unknown for `[TARGET_CHANNEL]`, mark channel eligibility `[NEEDS CONFIRMATION]`.
- If `[SELF_EXCLUSION_STATUS]` is unknown, mark suppression handling as `[NEEDS CONFIRMATION]`.
- If `[RG_RISK_STATUS]` is unknown, mark RG suppression as `[NEEDS CONFIRMATION]`.
- If users are self-excluded, under cooling-off restrictions, or RG-restricted, exclude them.
- If users recently show risky gambling behaviour, exclude or route for RG/compliance review.
- If the campaign is reactivation, avoid targeting recently heavy-losing users with incentives.
- If the campaign is retention, avoid over-incentivising users who are already highly active without incremental reason.
- If the campaign is activation, prioritise simple first-action segments.
- If the campaign is event-led, prioritise players with relevant sport, league, team, market, or bet-type interest where confirmed.
- If the campaign is VIP-focused, recommend manual review and tighter controls.
- If `[BONUS_SENSITIVITY]` is high, recommend lower-exposure or more constrained mechanics.
- If `[SHARP_OR_ARB_RISK]` is present, recommend exclusion, reduced value, or low-exposure mechanics.
- If the audience is broad recreational, recommend simple mechanics and clear channel messaging.
- If data quality is weak, label the segment as provisional.
- Do not use sensitive, prohibited, or inappropriate personal attributes for targeting unless explicitly allowed and compliant.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, and `crm-sportsbook-event-opportunity` when the campaign is event-led.
- Normally run after this skill: `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, channel communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Segmentation Dimensions

The skill should consider the following, without inventing local facts.

### Lifecycle Segments

- Newly registered, no deposit.
- Deposited, no bet.
- First bet completed.
- Early lifecycle active.
- Mature active.
- Declining activity.
- Dormant.
- Reactivation-eligible.
- VIP.
- Former VIP.
- Bonus-only user.
- At-risk user, subject to RG rules.

### Value Segments

- Low value.
- Mid value.
- High value.
- VIP.
- High turnover but low margin.
- High bonus cost.
- Potentially high-value new customer.
- Low incrementality active user.

### Behavioural Segments

- Pre-match bettors.
- Live/in-play bettors.
- Single bet users.
- Accumulator users.
- Bet builder users.
- Odds boost users.
- Free bet users.
- Cashback users.
- Deposit-offer users.
- Sport-specific bettors.
- League/team-specific bettors, if confirmed.
- Event-led bettors.
- Multi-sport users.
- Mobile-first users, if confirmed.
- Channel-responsive users.

### Risk and Commercial Segments

- Bonus-sensitive users.
- Bonus abusers or bonus-abuse risk.
- Sharp users.
- Arb-sensitive users.
- High stake users.
- Low stake recreational users.
- High frequency users.
- Inactive users.
- Recently heavy-losing users, subject to suppression/RG review.
- Users with complaints or friction history.
- Users with verification, AML, fraud, or account restrictions.

### Responsible-Gaming and Suppression Segments

- Self-excluded users.
- Users in cooling-off period.
- Users with active RG restrictions.
- Users with RG risk flags.
- Users who opted out of `[TARGET_CHANNEL]`.
- Users requiring manual review.
- Users excluded by local compliance notes.
- Users excluded by internal policy.

## Segment Fit by Campaign Objective

### Activation

Best-fit groups may include:

- Registered but not deposited.
- Deposited but not bet.
- New users with clear product interest.
- Users eligible for simple first-action offers.

Avoid:

- Users with RG risk.
- Users without opt-in.
- Users with verification restrictions.

### Retention

Best-fit groups may include:

- Active but declining users.
- Sport/event-relevant users.
- Recreational users with positive engagement history.
- Users who may respond to event-led value.

Avoid:

- Over-incentivising highly active users who would bet anyway.
- High bonus-cost users without incrementality.
- RG-risk users.

### Reactivation

Best-fit groups may include:

- Dormant users with no RG risk.
- Previously active users with positive history.
- Users dormant for a defined threshold.

Avoid:

- Recently heavy-losing users.
- Users with RG flags.
- Emotionally manipulative targeting.
- Aggressive urgency.

### Event Activation

Best-fit groups may include:

- Relevant sport bettors.
- Relevant league/team bettors, if confirmed.
- Recent active users in related betting categories.
- Recreational users with event interest.

Avoid:

- Broad targeting if event relevance is weak.
- Users where event interest is inferred too aggressively.

### Cross-Sell Within Sportsbook

Best-fit groups may include:

- Single-sport users who may engage with another sport.
- Pre-match users who may try live betting.
- Single bet users who may try accumulators.
- Sportsbook users who may try bet builder.

Avoid:

- Complex mechanics for low-engagement users.
- High-risk product nudges without RG review.

### VIP Engagement

Best-fit groups may include:

- Confirmed VIPs.
- High-value users with safe engagement profile.
- Users approved for bespoke treatment.

Avoid:

- Automated high-value incentives without manual review.
- Users with RG risk.
- Users whose high value comes from risky behaviour.

## Market-Agnostic Design Rules

The skill must never assume:

- Local sport preferences.
- Local betting habits.
- Local channel preferences.
- Local language.
- Local deposit behaviour.
- Local payment methods.
- Local regulations.
- Local cultural tone.
- Local competitor behaviour.
- Local player value thresholds.

All segment-specific and market-specific details must come from:

- User-provided inputs.
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

The skill should consider `[TARGET_CHANNEL]` if supplied.

For SMS:

- Require or flag SMS opt-in status.
- Recommend simple and broad-enough segment logic.
- Avoid segments requiring complex explanation in copy.
- Avoid overly personalised wording that may feel invasive.
- Consider frequency caps and opt-out risk.
- Feed into `crm-sportsbook-sms-copy`.

For email:

- Note that detailed email execution should be handled by a future email-specific skill.
- Email may allow more explanation and richer segmentation, but this skill should only define the audience logic.

For push:

- Note that detailed push execution should be handled by a future push-specific skill.
- Push audiences should consider app activity and push opt-in.

For onsite/inbox:

- Consider logged-in state, visibility, and timing.

For VIP outreach:

- Recommend manual approval, careful tone, and RG/compliance review.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag or exclude:

- Self-excluded users.
- Users with RG risk flags.
- Users in cooling-off periods.
- Users with active limits or restrictions where promotion is inappropriate.
- Users recently showing risky gambling behaviour.
- Users targeted because of recent losses.
- Users targeted with emotionally manipulative reactivation.
- Users without valid communication opt-in for `[TARGET_CHANNEL]`.
- Users restricted by compliance, AML, fraud, or account status.

The skill must never recommend segments based on:

- Chasing losses.
- Financial distress.
- Vulnerability.
- Attempts to recover losses.
- Sensitive personal attributes.
- Invasive or creepy personalisation.

If suppression data is unavailable, mark launch readiness `[NEEDS CONFIRMATION]` and recommend `crm-sportsbook-rg-compliance-review`.

## Commercial Guardrails

The skill should identify segmentation risks that could affect:

- Bonus cost.
- Incrementality.
- Margin exposure.
- Bonus abuse.
- Arb exposure.
- Sharp-player exposure.
- VIP cost.
- Channel cost.
- Opt-out risk.
- Segment size.
- Campaign fatigue.
- Frequency caps.
- Overlap with other campaigns.
- Control group integrity.

Do not estimate commercial impact unless data is provided or the user explicitly asks for assumptions.

## Brand & UX Guardrails

The skill should help the CRM team understand:

- Whether the segment logic can be explained internally.
- Whether the customer-facing personalisation may feel natural or invasive.
- Whether the segment is too broad or too narrow.
- Whether the segment is suitable for `[TARGET_CHANNEL]`.
- Whether the campaign could feel spammy.
- Whether the campaign creates fatigue.
- Whether the value proposition is relevant to `[TARGET_SEGMENT]`.

Do not stereotype `[TARGET_MARKET]`. Do not claim local player preferences, local sport interest, local channel behaviour, or local promotional expectations unless supplied by the user or confirmed through research.

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
# Player Segmentation Output

## 1. Segmentation Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament: [TARGET_TOURNAMENT]
- Proposed segment: [TARGET_SEGMENT]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Recommended Target Segment
- Segment name:
- Inclusion criteria:
- Exclusion criteria:
- Lifecycle criteria:
- Behaviour criteria:
- Channel eligibility:
- RG/compliance eligibility:
- Commercial eligibility:

## 6. Segment Rationale
- Customer relevance:
- Sport/event relevance:
- Offer relevance:
- Channel relevance:
- Commercial rationale:

## 7. Secondary Segment Options
| Segment name | Use case | Benefit | Risk | When to use |
|---|---|---|---|---|
|  |  |  |  |  |

## 8. Suppression Rules
- Self-exclusion:
- RG risk flags:
- Cooling-off:
- Channel opt-out:
- Compliance/account restrictions:
- Bonus abuse restrictions, where relevant:
- Recently heavy-losing users, where relevant:

## 9. Segment-to-Offer Fit
- Suitable offer directions:
- Offer directions to avoid:
- Constraints to pass to offer mechanics:

## 10. Channel Considerations
- [TARGET_CHANNEL]:
- SMS opt-in if applicable:
- Frequency cap considerations:
- Simple copy implications:

## 11. RG & Compliance Considerations
- [REGULATORY_NOTES]:
- [RISK]

## 12. Commercial Considerations
- [BONUS_SENSITIVITY]:
- [SHARP_OR_ARB_RISK]:
- [RISK]
- [RECOMMENDATION]

## 13. Data Quality Notes
- Strong segmentation basis / Usable with assumptions / Needs more data before launch / Not recommended based on current data:
- Rationale:

## 14. Recommended Next Skills
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 15. Launch Readiness
- Ready to proceed with assumptions / Needs segmentation data before offer design / Needs RG/compliance input before campaign design / Not recommended based on current information
```

## Example User Request

"Define the target segment for a sportsbook campaign in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`, the channel is `[TARGET_CHANNEL]`, and the campaign is linked to `[TARGET_EVENT]`."

## Example Output

```markdown
# Player Segmentation Output

## 1. Segmentation Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament: [TARGET_TOURNAMENT]
- Proposed segment: [TARGET_SEGMENT]

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Event context: [TARGET_EVENT]

## 3. Working Assumptions
- [ASSUMPTION] No sport preference, event affinity, lifecycle status, value segment, VIP status, or bonus sensitivity is assumed until customer data is provided.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_SEGMENT]
- [NEEDS CONFIRMATION] [TARGET_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [CUSTOMER_LIFECYCLE_STAGE]
- [NEEDS CONFIRMATION] [CUSTOMER_VALUE_SEGMENT]
- [NEEDS CONFIRMATION] [PREFERRED_BET_TYPE]
- [NEEDS CONFIRMATION] [PRE_MATCH_OR_LIVE_PREFERENCE]
- [NEEDS CONFIRMATION] [SINGLE_OR_ACCUMULATOR_PREFERENCE]
- [NEEDS CONFIRMATION] [VIP_STATUS]
- [NEEDS CONFIRMATION] [BONUS_SENSITIVITY]
- [NEEDS CONFIRMATION] [SHARP_OR_ARB_RISK]
- [NEEDS CONFIRMATION] [CHURN_RISK]
- [NEEDS CONFIRMATION] [RG_RISK_STATUS]
- [NEEDS CONFIRMATION] [SELF_EXCLUSION_STATUS]
- [NEEDS CONFIRMATION] [COMMUNICATION_OPT_IN_STATUS]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]

## 5. Recommended Target Segment
- Segment name: [TARGET_SEGMENT] with confirmed event relevance and valid channel eligibility.
- Inclusion criteria: Customers with confirmed relevance to [TARGET_SPORT] or [TARGET_EVENT], suitable lifecycle stage, appropriate value segment, valid [TARGET_CHANNEL] opt-in, and no suppression flags.
- Exclusion criteria: Self-excluded users, RG-risk users, cooling-off users, opted-out users, compliance-restricted users, bonus-abuse risk users where relevant, and recently heavy-losing users where relevant.
- Lifecycle criteria: [CUSTOMER_LIFECYCLE_STAGE]
- Behaviour criteria: [PREFERRED_BET_TYPE], [PRE_MATCH_OR_LIVE_PREFERENCE], [SINGLE_OR_ACCUMULATOR_PREFERENCE]
- Channel eligibility: [COMMUNICATION_OPT_IN_STATUS]
- RG/compliance eligibility: [RG_RISK_STATUS], [SELF_EXCLUSION_STATUS], [REGULATORY_NOTES]
- Commercial eligibility: [CUSTOMER_VALUE_SEGMENT], [BONUS_SENSITIVITY], [SHARP_OR_ARB_RISK]

## 6. Segment Rationale
- Customer relevance: [NEEDS CONFIRMATION] Validate lifecycle, value, and recent engagement.
- Sport/event relevance: [NEEDS CONFIRMATION] Confirm [TARGET_SPORT] and [TARGET_EVENT] affinity before targeting.
- Offer relevance: [RECOMMENDATION] Pass segment constraints to `crm-sportsbook-offer-mechanics`.
- Channel relevance: [RECOMMENDATION] If [TARGET_CHANNEL] is SMS, require opt-in and keep targeting logic simple enough for clear copy.
- Commercial rationale: [RISK] Bonus sensitivity, sharp or arb risk, and incrementality require confirmation.

## 7. Secondary Segment Options
| Segment name | Use case | Benefit | Risk | When to use |
|---|---|---|---|---|
| Event-relevant recreational users | Broad event activation | Simple fit for event-led messaging | Event relevance may be unconfirmed | Use when sport or event affinity is confirmed |
| Declining active users | Retention | Potential incremental engagement | Over-incentivising risk | Use when activity decline and safe profile are confirmed |
| Reactivation-eligible dormant users | Reactivation | Can restore activity | RG and loss-history risk | Use only with strong suppressions and neutral messaging |

## 8. Suppression Rules
- Self-exclusion: [NEEDS CONFIRMATION] Exclude if [SELF_EXCLUSION_STATUS] indicates exclusion.
- RG risk flags: [NEEDS CONFIRMATION] Exclude if [RG_RISK_STATUS] indicates risk.
- Cooling-off: [NEEDS CONFIRMATION] Exclude users in cooling-off periods.
- Channel opt-out: [NEEDS CONFIRMATION] Exclude if [COMMUNICATION_OPT_IN_STATUS] is not valid for [TARGET_CHANNEL].
- Compliance/account restrictions: [NEEDS CONFIRMATION]
- Bonus abuse restrictions, where relevant: [RISK] Exclude or constrain.
- Recently heavy-losing users, where relevant: [RISK] Exclude and route to RG/compliance review.

## 9. Segment-to-Offer Fit
- Suitable offer directions: [RECOMMENDATION] Use simple, capped, segment-appropriate offer directions.
- Offer directions to avoid: [RISK] Avoid rich or exploitable value for high [BONUS_SENSITIVITY] or [SHARP_OR_ARB_RISK].
- Constraints to pass to offer mechanics: [RECOMMENDATION] Customer value band, bonus sensitivity, opt-in, suppression status, and event relevance.

## 10. Channel Considerations
- [TARGET_CHANNEL]: [RECOMMENDATION] Match audience size and complexity to channel limitations.
- SMS opt-in if applicable: [NEEDS CONFIRMATION] [COMMUNICATION_OPT_IN_STATUS]
- Frequency cap considerations: [NEEDS CONFIRMATION]
- Simple copy implications: [RECOMMENDATION] Avoid overly granular personalisation in customer-facing copy.

## 11. RG & Compliance Considerations
- [REGULATORY_NOTES]: [NEEDS CONFIRMATION]
- [RISK] Do not launch until self-exclusion, RG risk, cooling-off, channel opt-in, and account restriction suppressions are confirmed.

## 12. Commercial Considerations
- [BONUS_SENSITIVITY]: [NEEDS CONFIRMATION]
- [SHARP_OR_ARB_RISK]: [NEEDS CONFIRMATION]
- [RISK] Segment may create bonus cost, low incrementality, or abuse exposure if value and behaviour data are missing.
- [RECOMMENDATION] Use a control group and analyse by lifecycle, value, sport/event relevance, bonus sensitivity, and channel eligibility.

## 13. Data Quality Notes
- Needs more data before launch:
- Rationale: Key suppression, channel eligibility, sport/event affinity, value, and risk fields are not confirmed.

## 14. Recommended Next Skills
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 15. Launch Readiness
- Needs segmentation data before offer design.
```
