---
name: crm-sportsbook-ab-testing
description: Designs safe, measurable, commercially useful, market-agnostic sportsbook CRM A/B tests and simple experiment plans with hypotheses, variants, audience splits, controls, KPIs, guardrails, measurement windows, decision rules, suppression logic, and post-campaign analysis handoff.
---

# CRM Sportsbook A/B Testing

## Purpose

This skill helps CRM teams design responsible, measurable, commercially useful A/B tests for sportsbook CRM campaigns.

It helps CRM teams define:

- Test objective.
- `[TEST_HYPOTHESIS]`.
- Variants.
- Audience split.
- `[CONTROL_GROUP]`.
- `[PRIMARY_KPI]`.
- `[SECONDARY_KPIS]`.
- `[GUARDRAIL_METRICS]`.
- `[MEASUREMENT_WINDOW]`.
- Eligibility and `[SUPPRESSION_RULES]`.
- Commercial risk controls.
- Responsible-gaming controls.
- `[DECISION_RULE]`.
- Post-campaign analysis inputs.

The skill supports:

- SMS copy tests.
- Offer mechanic tests.
- Offer value tests.
- `[CTA]` tests.
- Event-led angle tests.
- Timing tests.
- Journey step tests.
- Segment tests.
- Localisation tests.
- Control group or holdout tests.
- Incrementality tests.

This skill designs CRM testing logic. It does not invent expected uplift, `[SAMPLE_SIZE]`, market facts, or final statistical conclusions unless the user provides data or explicitly asks for labelled assumptions.

## Role in the Skill Pack

This skill usually runs after:

- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`, if testing SMS variants.
- `crm-sportsbook-localisation`, if testing localised variants.
- `crm-sportsbook-rg-compliance-review`, before launch.
- `crm-sportsbook-journey-builder`, if testing journey logic.

It uses outputs from:

- Market context.
- Event opportunity.
- Player segmentation.
- Offer mechanics.
- Campaign brief.
- SMS copy.
- Localisation.
- Responsible-gaming and compliance review.
- Journey builder.

It may be selected by `crm-sportsbook-skill-router` when the user asks for A/B testing, test design, variant logic, hypothesis, KPIs, control groups, holdouts, measurement windows, decision rules, or incrementality planning.

It feeds:

- `crm-sportsbook-post-campaign-analysis`

It should not:

- Invent market facts.
- Invent event schedules.
- Invent expected uplift.
- Replace BI or statistics review for large experiments.
- Replace compliance or responsible-gaming review.
- Approve unsafe tests.
- Recommend tests that expose vulnerable users to greater risk.
- Treat short-term turnover as the only success metric.

It creates the test design and measurement logic.

## When to Use

Use this skill when the CRM manager needs to:

- Design an A/B test for a sportsbook CRM campaign.
- Compare SMS copy variants.
- Compare offer mechanics.
- Compare offer values.
- Compare `[CTA]` options.
- Compare event-led vs value-led messaging.
- Compare expiry framing.
- Compare personalised vs non-personalised copy.
- Compare single message vs reminder journey.
- Compare different journey timings.
- Compare localisation variants.
- Define `[CONTROL_GROUP]`.
- Define `[PRIMARY_KPI]` and `[SECONDARY_KPIS]`.
- Define `[GUARDRAIL_METRICS]`.
- Define `[MEASUREMENT_WINDOW]`.
- Define `[DECISION_RULE]`.
- Prepare a test plan for BI, CRM operations, product, risk, or management review.
- Avoid weak tests that cannot produce useful learning.

## When Not to Use

Do not use this skill to:

- Create campaign strategy from scratch.
- Create market context from scratch.
- Select player segments from raw data without segmentation input.
- Design offer mechanics from scratch.
- Write final SMS copy from scratch.
- Localise copy from scratch.
- Review final legal or compliance status.
- Analyse completed campaign results in depth.
- Claim statistical significance without data.
- Invent `[SAMPLE_SIZE]` or uplift expectations without data.
- Recommend tests that bypass responsible-gaming or compliance review.
- Recommend tests that increase exposure to vulnerable or restricted users.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- SMS copy: `crm-sportsbook-sms-copy`.
- Localisation: `crm-sportsbook-localisation`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]` or player segmentation output.
- Campaign brief output or enough campaign context.
- `[TEST_HYPOTHESIS]` or request to create one.
- `[VARIANT_A]` and `[VARIANT_B]`, or instruction to propose variants.
- `[PRIMARY_KPI]` or request to recommend one.
- `[SUPPRESSION_RULES]` or instruction to use shared baseline suppressions.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[EVENT_DATE]`
- `[EVENT_START_TIME]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- `[EXPIRY]`
- `[ELIGIBLE_MARKETS]`
- `[CTA]`
- `[T&CS]`
- `[T&CS_LINK]`
- `[BRAND_NAME]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- `[FREQUENCY_CAPS]`
- `[JOURNEY_TRIGGER]`
- `[JOURNEY_STEPS]`
- `[CONTROL_GROUP]`
- `[SECONDARY_KPIS]`
- `[GUARDRAIL_METRICS]`
- `[MEASUREMENT_WINDOW]`
- `[DECISION_RULE]`
- `[SEGMENT_SIZE]`
- SMS copy output, if testing SMS.
- Localisation output, if testing localised copy.
- Journey builder output, if testing journey flow.
- RG/compliance review output, if available.

### Advanced optional inputs

- Historical campaign performance.
- Baseline conversion rate.
- Expected uplift supplied at runtime.
- Minimum detectable effect.
- Confidence level requirement.
- Power requirement.
- Sample size calculator output.
- `[SAMPLE_SIZE]`
- `[SEGMENT_SIZE]`
- Audience eligibility count.
- `[CONTROL_GROUP]` policy.
- Randomisation method.
- Holdout rules.
- Attribution rules.
- Conversion window.
- Bonus cost limit.
- GGR target.
- NGR target.
- Turnover target.
- Deposit conversion target.
- Bet conversion target.
- Offer uptake target.
- Opt-out threshold.
- Complaint threshold.
- Responsible-gaming flag threshold.
- BI tracking plan.
- CRM platform experiment capabilities.
- Journey automation constraints.
- Link tracking rules.
- Reporting dashboard requirements.
- Previous A/B test results.
- Seasonality or event timing constraints.
- Product availability constraints.
- Trading or risk restrictions.
- Runtime approval workflow.

## Output

The skill should produce:

- Test plan summary.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Test objective.
- `[TEST_HYPOTHESIS]`.
- Test type.
- Variant definitions.
- Audience eligibility.
- Exclusions and suppressions.
- Split logic.
- `[CONTROL_GROUP]` recommendation.
- `[PRIMARY_KPI]`.
- `[SECONDARY_KPIS]`.
- `[GUARDRAIL_METRICS]`.
- `[MEASUREMENT_WINDOW]`.
- `[DECISION_RULE]`.
- Tracking requirements.
- Commercial risk checks.
- Responsible-gaming and compliance risk checks.
- Operational requirements.
- Post-campaign analysis handoff.
- Recommended next skills.

## Workflow

1. Identify `[CAMPAIGN_OBJECTIVE]`.
2. Identify `[TARGET_MARKET]` as runtime context only.
3. Identify `[TARGET_CHANNEL]`.
4. Load and apply `crm-sportsbook-shared-principles`.
5. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
6. Review `crm-sportsbook-market-context` output if available.
7. Review `crm-sportsbook-event-opportunity` output if available.
8. Review `crm-sportsbook-player-segmentation` output if available.
9. Review `crm-sportsbook-offer-mechanics` output if available.
10. Review `crm-sportsbook-campaign-brief` output if available.
11. Review `crm-sportsbook-sms-copy` output if SMS variants are being tested.
12. Review `crm-sportsbook-localisation` output if localised variants are being tested.
13. Review `crm-sportsbook-journey-builder` output if journey logic is being tested.
14. Review `crm-sportsbook-rg-compliance-review` output if available.
15. List all confirmed inputs as `[CONFIRMED]`.
16. Separate confirmed inputs from assumptions.
17. Mark missing test-critical inputs as `[NEEDS CONFIRMATION]`.
18. Define the test objective.
19. Define or refine `[TEST_HYPOTHESIS]`.
20. Identify the test type.
21. Define `[VARIANT_A]` and `[VARIANT_B]` clearly.
22. Confirm that variants differ by one main variable where possible.
23. Define audience eligibility.
24. Define exclusions and suppressions.
25. Define split logic or `[CONTROL_GROUP]`.
26. Define `[PRIMARY_KPI]`.
27. Define `[SECONDARY_KPIS]`.
28. Define `[GUARDRAIL_METRICS]`.
29. Define `[MEASUREMENT_WINDOW]`.
30. Define tracking requirements.
31. Define `[DECISION_RULE]`.
32. Check commercial risk.
33. Check responsible-gaming and compliance risk.
34. Check operational readiness.
35. Define post-campaign analysis inputs.
36. Recommend next skill chain.

## Decision Logic

Apply these rules:

- If `[CAMPAIGN_OBJECTIVE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_SEGMENT]` is missing, recommend running `crm-sportsbook-player-segmentation`.
- If campaign brief is missing, the skill may still create a provisional test but must label assumptions.
- If SMS copy variants are missing for an SMS copy test, recommend running `crm-sportsbook-sms-copy`.
- If localisation is being tested but localised variants are missing, recommend running `crm-sportsbook-localisation`.
- If journey logic is being tested but no journey exists, recommend running `crm-sportsbook-journey-builder`.
- If RG/compliance review has not been run, recommend running `crm-sportsbook-rg-compliance-review` before launch.
- If `[SUPPRESSION_RULES]` are missing, apply shared baseline suppressions and mark runtime suppressions as `[NEEDS CONFIRMATION]`.
- If the test exposes one group to materially higher responsible-gaming risk, do not recommend it.
- If the test changes multiple major variables at once, warn that learning will be unclear.
- If `[SAMPLE_SIZE]` or `[SEGMENT_SIZE]` is too small to learn from, mark the test as `[RISK]` and recommend treating it as directional only.
- If the test is event-led and the event window is short, flag measurement and sample-size limitations.
- If the test is reactivation-focused, use conservative frequency and include responsible-gaming guardrails.
- If the test is deposit or reload focused, include deposit pressure and responsible-gaming guardrails.
- If the test is VIP-focused, require manual review and avoid fully automated high-value experiments.
- If the test compares `[OFFER_VALUE]`, define `[MAX_BONUS_VALUE]`, bonus cost controls, and exposure limits.
- If the test compares copy only, keep `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, timing, audience, and terms identical.
- If the test compares offer mechanics, keep copy framing as comparable as possible.
- If the test compares timing, keep audience, offer, and copy as consistent as possible.
- If the test compares localisation, preserve offer meaning and `[T&CS]` clarity across variants.
- If no `[PRIMARY_KPI]` is supplied, recommend one based on `[CAMPAIGN_OBJECTIVE]`.
- If no `[GUARDRAIL_METRICS]` are supplied, include opt-out rate, complaints, bonus cost, and post-campaign responsible-gaming flags.
- If success is measured only by turnover, recommend adding NGR, bonus cost, conversion, and guardrail metrics.
- If no `[CONTROL_GROUP]` is supplied, recommend one where incrementality matters.
- If critical tracking is missing, mark launch readiness as not ready for testing.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy` when SMS is tested, `crm-sportsbook-localisation` when localised variants are tested, `crm-sportsbook-rg-compliance-review`, and `crm-sportsbook-journey-builder` when journey logic is tested.
- Normally run after this skill: `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, measurement principles, and final campaign quality checklist.

## Test Types

Support these test types.

### SMS Copy Test

Use when comparing wording variants.

Examples:

- Value-led vs event-led.
- Simple `[CTA]` vs expiry-led.
- Short copy vs clearer longer copy.
- Personalised vs non-personalised.
- Product-led vs offer-led.

Rules:

- Keep audience, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, timing, and `[TARGET_CHANNEL]` constant.
- Keep `[T&CS]` consistent.
- Check character counts when copy is included.
- Check responsible-gaming and compliance risk for both variants.

### Offer Value Test

Use when comparing different reward values.

Examples:

- Lower `[OFFER_VALUE]` vs higher `[OFFER_VALUE]`.
- Lower bonus cap vs higher bonus cap.
- Smaller broad offer vs richer targeted offer.

Rules:

- Define cost exposure.
- Define `[MAX_BONUS_VALUE]`.
- Compare NGR and bonus cost, not just uptake.
- Watch bonus abuse and low incrementality.

### Offer Mechanic Test

Use when comparing mechanics.

Examples:

- Free bet vs odds boost.
- Bet-and-get vs cashback.
- Loyalty points vs free bet.

Rules:

- Keep `[TARGET_SEGMENT]` consistent.
- Make mechanics as comparable as possible.
- Check customer understanding.
- Check bonus cost and risk differences.
- Check responsible-gaming and compliance risk by mechanic.

### CTA Test

Use when comparing action wording.

Examples:

- `[CTA]` option A vs `[CTA]` option B.
- Direct action wording vs detail-view wording.

Rules:

- Avoid pressure-heavy CTAs.
- Keep offer and message unchanged except `[CTA]`.
- Track click or offer-view rate if available.

### Timing Test

Use when comparing send timing.

Examples:

- Pre-event timing option A vs pre-event timing option B.
- Earlier send vs later send.
- Earlier reminder vs later reminder.

Rules:

- Do not invent local send-time rules.
- Respect `[FREQUENCY_CAPS]`.
- Avoid pressure-heavy last-minute reminders.
- Track delivery, engagement, opt-out, conversion, complaints, and responsible-gaming flags.

### Journey Test

Use when comparing journey structure.

Examples:

- One message vs one message plus reminder.
- Reminder timing option A vs reminder timing option B.
- Reminder vs no reminder.

Rules:

- Include `[FREQUENCY_CAPS]`.
- Include suppression before every send.
- Monitor opt-outs and complaints.
- Avoid repeated pressure.

### Segment Test

Use when comparing audience definitions.

Examples:

- Broad event-relevant users vs high-intent users.
- Shorter dormancy threshold vs longer dormancy threshold supplied at runtime.

Rules:

- Ensure fair comparison.
- Do not expose vulnerable users.
- Check `[SEGMENT_SIZE]`.
- Check incrementality and bonus cost.

### Localisation Test

Use when comparing localised wording variants.

Examples:

- Literal translation vs adaptive localisation.
- Brand-approved tone option A vs brand-approved tone option B.
- `[CTA]` wording option A vs `[CTA]` wording option B.

Rules:

- Preserve offer meaning.
- Preserve `[T&CS]` clarity.
- Require native-language QA where needed.
- Monitor complaints and opt-outs.

### Control Group / Holdout Test

Use when measuring incrementality.

Rules:

- Holdout should be eligible but not contacted or not offered, depending on design.
- Do not withhold required responsible-gaming, account, or service communications.
- Define `[MEASUREMENT_WINDOW]`.
- Compare incremental value, not just raw conversion.

## Campaign Objective-to-KPI Logic

### Activation

Potential `[PRIMARY_KPI]` options:

- First deposit conversion.
- First bet conversion.
- First qualifying bet.
- Offer uptake.

Potential `[SECONDARY_KPIS]`:

- Cost per activated customer.
- Bonus cost.
- NGR.
- Repeat action after first conversion.
- Short-term retention after activation.

Potential `[GUARDRAIL_METRICS]`:

- Opt-out rate.
- Complaint rate.
- Responsible-gaming flags.
- Verification or account issues.

### Retention

Potential `[PRIMARY_KPI]` options:

- Bet conversion.
- Active days.
- Repeat betting rate.
- Incremental turnover.
- Incremental NGR.

Potential `[SECONDARY_KPIS]`:

- Offer uptake.
- Bonus cost.
- Margin impact.
- Frequency of betting.

Potential `[GUARDRAIL_METRICS]`:

- Opt-out rate.
- Complaint rate.
- Responsible-gaming flags.
- Bonus abuse indicators.

### Reactivation

Potential `[PRIMARY_KPI]` options:

- Reactivation rate.
- Qualifying bet conversion.
- Deposit conversion if relevant.

Potential `[SECONDARY_KPIS]`:

- Retained activity after reactivation.
- Bonus cost.
- NGR.
- Repeat activity.

Potential `[GUARDRAIL_METRICS]`:

- Opt-out rate.
- Complaint rate.
- Responsible-gaming flags.
- Heavy-loss indicators.
- Support contacts.

### Event Activation

Potential `[PRIMARY_KPI]` options:

- Event bet conversion.
- Offer uptake.
- Qualifying event turnover.
- Incremental event NGR.

Potential `[SECONDARY_KPIS]`:

- Click rate.
- Bet count.
- Product usage.
- Bonus cost.

Potential `[GUARDRAIL_METRICS]`:

- Opt-out rate.
- Complaint rate.
- Responsible-gaming flags.
- Bonus abuse.
- In-play operational issues.

### Cross-Sell Within Sportsbook

Potential `[PRIMARY_KPI]` options:

- First use of target product.
- Bet builder trial.
- Live betting trial.
- Accumulator trial.
- New sport bet conversion.

Potential `[SECONDARY_KPIS]`:

- Repeat product use.
- Incremental NGR.
- Offer cost.
- Retention.

Potential `[GUARDRAIL_METRICS]`:

- Product misunderstanding.
- Complaints.
- Responsible-gaming flags.
- Excessive play indicators.

### VIP Engagement

Potential `[PRIMARY_KPI]` options:

- Engagement with approved offer.
- Qualifying activity.
- Relationship manager follow-up outcome.

Potential `[SECONDARY_KPIS]`:

- NGR.
- Retention.
- Event participation.
- Bonus cost.

Potential `[GUARDRAIL_METRICS]`:

- Responsible-gaming flags.
- High-loss exposure.
- Complaints.
- Manual review completion.

## Variant Design Rules

Each variant should define:

- Variant name.
- What changes.
- What stays the same.
- Audience.
- Offer.
- Channel.
- Timing.
- Copy or journey logic.
- Expected learning.
- Risk notes.

Good tests:

- Change one main variable.
- Have clear `[TEST_HYPOTHESIS]`.
- Use measurable `[PRIMARY_KPI]`.
- Have enough eligible audience.
- Include `[GUARDRAIL_METRICS]`.
- Avoid unsafe pressure.
- Preserve offer truthfulness.

Weak tests:

- Change copy, offer, timing, and audience at the same time.
- Have no clear `[TEST_HYPOTHESIS]`.
- Use only vanity metrics.
- Ignore bonus cost.
- Ignore opt-outs and complaints.
- Ignore responsible-gaming flags.
- Have too small a `[SAMPLE_SIZE]`.
- Run during unusual event windows without noting limitations.

## Audience Split Rules

The skill should recommend:

- Random split where possible.
- Equal split when risk and cost are similar.
- Smaller test cell for higher-risk or higher-cost variant.
- `[CONTROL_GROUP]` where incrementality matters.
- Holdout for broad campaigns.
- Manual review for VIP or high-value segments.

Do not invent exact split percentages unless:

- User provides requirements, or
- User asks for assumptions.

If recommending assumptions, label them `[ASSUMPTION]`.

## Suppression Rules

The test must apply suppression checks:

- Before test assignment.
- Before each message send.
- Before offer award where relevant.
- Before reminders.
- Before VIP outreach.

Mandatory suppressions:

- Self-excluded users.
- Users with responsible-gaming risk flags.
- Users in cooling-off periods.
- Users without channel opt-in.
- Users with compliance or account restrictions.
- Users with AML or fraud restrictions.
- Users blocked from bonuses.
- Users under bonus abuse restrictions.
- Users restricted by runtime market policy, if supplied.
- Users recently heavy-losing, where relevant to reactivation or incentive campaigns.

## Measurement Rules

The skill should define:

- `[PRIMARY_KPI]`.
- `[SECONDARY_KPIS]`.
- `[GUARDRAIL_METRICS]`.
- Conversion event.
- Attribution window.
- `[MEASUREMENT_WINDOW]`.
- `[CONTROL_GROUP]` comparison.
- Segment-level reporting.
- Offer cost tracking.
- NGR/GGR tracking.
- Opt-out tracking.
- Complaint tracking.
- Responsible-gaming flag tracking.
- Exit reason tracking for journeys.
- Data handoff to post-campaign analysis.

Do not claim statistical validity unless sufficient data and method are provided.

## Guardrail Metrics

Every test should include `[GUARDRAIL_METRICS]`.

Recommended guardrails:

- Opt-out rate.
- Complaint rate.
- Post-campaign responsible-gaming flags.
- Self-exclusion after campaign.
- Cooling-off activation after campaign.
- Bonus cost.
- Bonus abuse flags.
- Sharp or arb exploitation indicators.
- Support contacts.
- Negative NGR impact.
- `[FREQUENCY_CAPS]` breaches.
- Delivery issues.

## Decision Rule Guidance

The `[DECISION_RULE]` should define:

- What result wins.
- What metric matters most.
- What guardrail failure blocks rollout.
- What happens if results are inconclusive.
- Whether to roll out, retest, revise, or stop.

Example structure using placeholders:

- Roll out `[VARIANT_A]` or `[VARIANT_B]` only if `[PRIMARY_KPI]` improves versus the other variant and `[GUARDRAIL_METRICS]` remain within acceptable limits.
- If `[PRIMARY_KPI]` improves but `[GUARDRAIL_METRICS]` worsen materially, do not roll out until reviewed.
- If results are inconclusive, repeat only if the campaign remains commercially relevant and safe.

## Sportsbook-Specific Testing Considerations

The skill should consider, without inventing local facts:

- Sport or event relevance.
- Event timing.
- Fixture or tournament schedule.
- `[EXPIRY]`.
- Pre-match vs live timing.
- In-play availability and suspension risk.
- Odds boost exposure.
- Free bet cost.
- Cashback calculation window.
- Accumulator insurance exposure.
- Bet builder availability.
- Deposit or reload responsible-gaming sensitivity.
- VIP manual review.
- Sharp or arb exposure.
- Bonus abuse risk.
- Margin protection.
- Bonus cost.
- GGR and NGR impact.
- Incrementality.
- `[CONTROL_GROUP]` integrity.
- Frequency fatigue around major events.
- Post-campaign responsible-gaming monitoring.

## Market-Agnostic Design Rules

The skill must never assume:

- Local laws.
- Local approval requirements.
- Local language.
- Local channel rules.
- Local opt-in rules.
- Local send-time rules.
- Local sport preferences.
- Local betting habits.
- Local event schedules.
- Local holidays.
- Local payment methods.
- Local cultural tone.
- Local competitor behaviour.
- Local operator conventions.
- Local statistical baselines.

All test-specific and market-specific details must come from:

- User-provided inputs.
- Existing skill outputs.
- Internal documents.
- Approved policies.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts. Do not invent market facts, event schedules, local behaviour, response rates, expected uplift, or final statistical conclusions.

## Channel-Aware Testing Rules

### SMS

For SMS tests:

- Keep one offer per SMS.
- Keep variants comparable.
- Include character counts if copy is included.
- Avoid pressure-heavy urgency.
- Include `[T&CS]` handling.
- Confirm opt-in or flag it.
- Track delivery, clicks if available, conversion, opt-out, complaints, and responsible-gaming flags.

### Email

For email tests:

- Do not write full email copy.
- Note that detailed email execution should be handled by a future email-specific skill.
- Subject line tests must avoid misleading claims.
- Track opens cautiously, but prioritise downstream behaviour.

### Push

For push tests:

- Do not write full push copy.
- Note that detailed push execution should be handled by a future push-specific skill.
- Avoid urgency that creates pressure.
- Track opt-outs and app notification permissions.

### Onsite / Inbox

For onsite or inbox tests:

- Ensure offer details are visible.
- Track impressions, clicks, offer views, and conversion.

### VIP Outreach

For VIP tests:

- Require manual review.
- Avoid automated high-value randomisation without owner approval.
- Use qualitative feedback where relevant.
- Include responsible-gaming checks.

## Responsible Gaming & Compliance Guardrails

The skill must follow shared responsible-gaming principles.

It must reject or require redesign for tests that:

- Target self-excluded users.
- Target users with responsible-gaming risk flags.
- Target users in cooling-off periods.
- Contact users without channel opt-in.
- Encourage chasing losses.
- Use recent losses as trigger.
- Use financial pressure.
- Use shame, guilt, or emotional pressure.
- Escalate urgency through variants.
- Test aggressive pressure vs neutral copy.
- Push deposit or reload behaviour aggressively.
- Encourage excessive bet frequency.
- Encourage excessive accumulator complexity.
- Use VIP status to over-incentivise risky behaviour.
- Continue contacting users after opt-out, responsible-gaming flag, self-exclusion, `[EXPIRY]`, or conversion.

Every test must include:

- Suppression check before assignment.
- Suppression check before contact.
- `[GUARDRAIL_METRICS]`.
- RG/compliance review before launch.

## Compliance Guardrails

The skill must flag:

- Missing `[REGULATORY_NOTES]`.
- Missing opt-in handling.
- Missing opt-out handling where required.
- Missing `[T&CS]`.
- Missing approval workflow.
- Missing age, KYC, or account eligibility handling where relevant.
- Missing offer eligibility rules.
- Missing suppression logic.
- Missing consent handling.
- Missing experiment audit trail.
- Misleading claims in any variant.
- Unequal disclosure of terms between variants.
- Variants that change legal meaning.

The skill must not claim that a test is compliant unless required inputs and approvals are supplied.

## Commercial Guardrails

The skill must flag:

- Excessive bonus cost.
- Uncapped rewards.
- High-cost variant without smaller exposure.
- Bonus abuse risk.
- Sharp or arb exposure.
- VIP over-costing.
- Low incrementality.
- Over-incentivising natural activity.
- Offer leakage to unintended segments.
- Operational setup gaps.
- Tracking gaps.
- Poor `[CONTROL_GROUP]` design.
- Inconclusive test risk.
- Segment overlap with other campaigns.
- Campaign fatigue.

The skill should recommend:

- Exposure caps.
- `[FREQUENCY_CAPS]`.
- `[CONTROL_GROUP]`.
- Offer eligibility checks.
- Segment restrictions.
- `[EXPIRY]` handling.
- Abuse restrictions.
- Manual review where needed.

## Brand & UX Guardrails

The skill should ensure:

- Test variants are fair to compare.
- Variants do not mislead customers.
- `[CTA]` is clear.
- `[T&CS]` are equally visible.
- Personalisation is not invasive.
- Urgency is not manipulative.
- Copy does not stereotype `[TARGET_MARKET]`.
- Tone respects `[BRAND_TONE]`.
- Customer experience is not harmed for the sake of testing.
- Customers exit journey after conversion where relevant.

## Assumption Labels

Use these labels consistently:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked before launch.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

Use this response format when the skill is activated:

# A/B Testing Output

## 1. Test Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Offer value: `[OFFER_VALUE]`
- Test type:
- Material used:

## 2. Confirmed Inputs

List all confirmed user-provided facts and relevant prior skill outputs.

## 3. Working Assumptions

List assumptions clearly.

## 4. Needs Confirmation

List missing or uncertain test, market, timing, offer, channel, suppression, compliance, measurement, or operational details.

## 5. Test Objective

Explain what the test is trying to learn.

## 6. Hypothesis

Write a clear hypothesis.

Format:

If we change the tested element from `[VARIANT_A]` to `[VARIANT_B]`, then `[PRIMARY_KPI]` may improve because `[TEST_HYPOTHESIS]`.

Label any expected behaviour as `[ASSUMPTION]` unless backed by data.

## 7. Test Design

Define:

- Test type:
- `[VARIANT_A]`:
- `[VARIANT_B]`:
- What changes:
- What stays the same:
- Audience:
- Randomisation approach:
- `[CONTROL_GROUP]`:
- `[MEASUREMENT_WINDOW]`:

## 8. Audience Eligibility

Define:

- Inclusion criteria:
- Channel eligibility:
- Offer eligibility:
- Product eligibility:
- Account eligibility:
- Responsible-gaming eligibility:
- `[FREQUENCY_CAPS]` eligibility:
- `[CONTROL_GROUP]` eligibility:

## 9. Exclusions & Suppressions

List:

- Self-exclusion:
- Responsible-gaming risk flags:
- Cooling-off:
- Channel opt-out:
- Compliance/account restrictions:
- AML/fraud restrictions:
- Bonus abuse restrictions:
- Sharp/arb restrictions:
- VIP manual review:
- Recently heavy-losing users, if relevant:
- Other supplied `[SUPPRESSION_RULES]`:

## 10. Variant Detail

For each variant:

- Variant name:
- Description:
- Copy/mechanic/timing/journey logic:
- Customer experience:
- Commercial exposure:
- Responsible-gaming/compliance risk:
- Tracking needed:

## 11. KPI Framework

Define:

- `[PRIMARY_KPI]`:
- `[SECONDARY_KPIS]`:
- Commercial KPIs:
- Responsible-gaming/UX `[GUARDRAIL_METRICS]`:
- Diagnostic metrics:

## 12. Tracking & Measurement Plan

Define:

- Assignment event:
- Message sent:
- Delivery:
- Click or offer view:
- Offer opt-in:
- Deposit, if relevant:
- Bet placed:
- Bonus awarded:
- Bonus redeemed:
- Conversion:
- Revenue:
- Bonus cost:
- Opt-out:
- Complaint:
- Responsible-gaming flag:
- Exit reason, if journey:
- `[CONTROL_GROUP]` comparison:

## 13. Decision Rule

Define:

- Winning condition:
- Guardrail failure condition:
- Inconclusive result handling:
- Rollout rule:
- Retest rule:
- Stop rule:

## 14. RG & Compliance Review

Assess:

- Suppression before assignment:
- Suppression before contact:
- Variant risk difference:
- Pressure risk:
- Deposit pressure risk:
- Reactivation risk:
- `[T&CS]` consistency:
- Required approvals:
- Verdict:

## 15. Commercial Risk Review

Assess:

- Bonus cost risk:
- Open exposure:
- Bonus abuse risk:
- Sharp/arb risk:
- Low incrementality:
- VIP cost:
- Operational risk:
- Inconclusive test risk:

## 16. Operational Requirements

List:

- Audience build:
- Randomisation setup:
- `[CONTROL_GROUP]` setup:
- Suppression automation:
- Offer setup:
- Tracking:
- Link tagging:
- `[T&CS]` consistency:
- QA:
- Reporting:
- Owner dependencies:

## 17. Post-Campaign Analysis Handoff

List the exact data needed by `crm-sportsbook-post-campaign-analysis`.

Include:

- Audience counts:
- Variant assignment:
- Delivery:
- Engagement:
- Conversion:
- Bonus cost:
- GGR:
- NGR:
- `[GUARDRAIL_METRICS]`:
- Segment splits:
- Time window:
- `[CONTROL_GROUP]` data:
- Notes on anomalies:

## 18. Required Fixes Before Launch

List exact required changes.

For each:

- Issue:
- Risk type:
- Required fix:
- Owner:
- Blocking status: Blocking / Non-blocking.

## 19. Recommended Next Skills

Recommend next skill chain.

Examples:

- `crm-sportsbook-rg-compliance-review`, if not already completed after final test design.
- `crm-sportsbook-journey-builder`, if journey logic needs finalisation.
- `crm-sportsbook-post-campaign-analysis`, after campaign ends.

## 20. Final Recommendation

Use one:

- Ready for RG/compliance review.
- Ready for test setup.
- Needs missing inputs before test finalisation.
- Needs copy/localisation before test finalisation.
- Needs offer/commercial approval before test finalisation.
- Needs BI/statistics review before launch.
- Needs specialist review before launch.
- Not recommended based on current information.

Explain why.

## Example User Request

Use a market-neutral example with placeholders only.

Example:

"Design an A/B test for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`, channel is `[TARGET_CHANNEL]`, offer is `[OFFER_VALUE]` via `[OFFER_MECHANIC]`. We want to test `[VARIANT_A]` vs `[VARIANT_B]`."

## Example Output

Use placeholders only. Do not include a real country, region, language, league, tournament, team, operator, payment method, regulation, regulator, slang, or cultural reference.

# A/B Testing Output

## 1. Test Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Offer value: `[OFFER_VALUE]`
- Test type: SMS copy test.
- Material used: Campaign brief, SMS copy output, journey builder output, and RG/compliance review output supplied at runtime.

## 2. Confirmed Inputs

- `[CONFIRMED]` `[TARGET_MARKET]` supplied at runtime.
- `[CONFIRMED]` `[TARGET_CHANNEL]` supplied at runtime.
- `[CONFIRMED]` `[TARGET_SEGMENT]` supplied at runtime.
- `[CONFIRMED]` `[CAMPAIGN_OBJECTIVE]` supplied at runtime.
- `[CONFIRMED]` `[VARIANT_A]` and `[VARIANT_B]` supplied at runtime.

## 3. Working Assumptions

- `[ASSUMPTION]` Shared baseline suppressions apply unless detailed `[SUPPRESSION_RULES]` are supplied.
- `[ASSUMPTION]` The test should isolate one main variable to produce clearer learning.

## 4. Needs Confirmation

- `[NEEDS CONFIRMATION]` `[PRIMARY_KPI]`.
- `[NEEDS CONFIRMATION]` `[SECONDARY_KPIS]`.
- `[NEEDS CONFIRMATION]` `[GUARDRAIL_METRICS]`.
- `[NEEDS CONFIRMATION]` `[MEASUREMENT_WINDOW]`.
- `[NEEDS CONFIRMATION]` `[SEGMENT_SIZE]` and `[SAMPLE_SIZE]`.
- `[NEEDS CONFIRMATION]` `[CONTROL_GROUP]` rules.
- `[NEEDS CONFIRMATION]` `[SUPPRESSION_RULES]`.
- `[NEEDS CONFIRMATION]` `[REGULATORY_NOTES]`.

## 5. Test Objective

Learn whether `[VARIANT_A]` or `[VARIANT_B]` produces stronger customer response for `[TARGET_SEGMENT]` without increasing bonus cost, opt-outs, complaints, or responsible-gaming flags.

## 6. Hypothesis

If we change the tested element from `[VARIANT_A]` to `[VARIANT_B]`, then `[PRIMARY_KPI]` may improve because `[TEST_HYPOTHESIS]`.

- `[ASSUMPTION]` Expected behaviour is directional until supported by prior data.

## 7. Test Design

- Test type: SMS copy test.
- `[VARIANT_A]`: `[VARIANT_A]`.
- `[VARIANT_B]`: `[VARIANT_B]`.
- What changes: One copy angle or `[CTA]` element.
- What stays the same: `[TARGET_SEGMENT]`, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, `[T&CS_LINK]`, timing, and suppression logic.
- Audience: Eligible `[TARGET_SEGMENT]` after mandatory suppressions.
- Randomisation approach: `[NEEDS CONFIRMATION]`.
- `[CONTROL_GROUP]`: `[RECOMMENDATION]` Include if incrementality matters.
- `[MEASUREMENT_WINDOW]`: `[NEEDS CONFIRMATION]`.

## 8. Audience Eligibility

- Inclusion criteria: `[TARGET_SEGMENT]`.
- Channel eligibility: `[COMMUNICATION_OPT_IN_STATUS]` confirmed for `[TARGET_CHANNEL]`.
- Offer eligibility: Customer eligible for `[OFFER_MECHANIC]`.
- Product eligibility: Product availability confirmed.
- Account eligibility: No account restriction.
- Responsible-gaming eligibility: No `[RG_RISK_STATUS]`, self-exclusion, or cooling-off restriction.
- `[FREQUENCY_CAPS]` eligibility: Not exceeded.
- `[CONTROL_GROUP]` eligibility: Same eligibility as contacted audience, excluding mandatory suppressions.

## 9. Exclusions & Suppressions

- Self-exclusion: Suppress before assignment and contact.
- Responsible-gaming risk flags: Suppress before assignment and contact.
- Cooling-off: Suppress before assignment and contact.
- Channel opt-out: Suppress before assignment and contact.
- Compliance/account restrictions: Suppress.
- AML/fraud restrictions: Suppress.
- Bonus abuse restrictions: Suppress or route to risk review.
- Sharp/arb restrictions: Suppress or route to risk review.
- VIP manual review: Required if `[VIP_STATUS]` applies.
- Recently heavy-losing users, if relevant: Suppress or route to RG/compliance review.
- Other supplied `[SUPPRESSION_RULES]`: Apply before assignment and every send.

## 10. Variant Detail

- Variant name: `[VARIANT_A]`.
  Description: Baseline variant supplied at runtime.
  Copy/mechanic/timing/journey logic: Keep offer, timing, and terms consistent.
  Customer experience: Clear, short, and non-pressuring.
  Commercial exposure: Same as `[VARIANT_B]` unless testing `[OFFER_VALUE]`.
  Responsible-gaming/compliance risk: Requires review.
  Tracking needed: Assignment, send, delivery, engagement, conversion, opt-out, complaint, responsible-gaming flag, and bonus cost.
- Variant name: `[VARIANT_B]`.
  Description: Test variant supplied at runtime.
  Copy/mechanic/timing/journey logic: Change only the tested element.
  Customer experience: Clear, short, and non-pressuring.
  Commercial exposure: Same as `[VARIANT_A]` unless testing `[OFFER_VALUE]`.
  Responsible-gaming/compliance risk: Requires review.
  Tracking needed: Assignment, send, delivery, engagement, conversion, opt-out, complaint, responsible-gaming flag, and bonus cost.

## 11. KPI Framework

- `[PRIMARY_KPI]`: `[NEEDS CONFIRMATION]`.
- `[SECONDARY_KPIS]`: Offer uptake, conversion, NGR, GGR, bonus cost, and retention where relevant.
- Commercial KPIs: Bonus cost, NGR, GGR, margin impact, and incrementality.
- Responsible-gaming/UX `[GUARDRAIL_METRICS]`: Opt-out, complaints, responsible-gaming flags, support contacts, and frequency cap breaches.
- Diagnostic metrics: Delivery, click, offer view, and journey exit reason where relevant.

## 12. Tracking & Measurement Plan

- Assignment event: Required.
- Message sent: Required if message test.
- Delivery: Required if available.
- Click or offer view: Required if link or tracked offer view exists.
- Offer opt-in: Required if opt-in exists.
- Deposit, if relevant: Track without using financial pressure.
- Bet placed: Track qualifying conversion.
- Bonus awarded: Track value and timing.
- Bonus redeemed: Track usage.
- Conversion: Track against `[PRIMARY_KPI]`.
- Revenue: Track GGR and NGR where available.
- Bonus cost: Required.
- Opt-out: Required.
- Complaint: Required.
- Responsible-gaming flag: Required.
- Exit reason, if journey: Required.
- `[CONTROL_GROUP]` comparison: Required if incrementality matters.

## 13. Decision Rule

- Winning condition: Roll out the stronger variant only if `[PRIMARY_KPI]` improves and `[GUARDRAIL_METRICS]` remain acceptable.
- Guardrail failure condition: Do not roll out if opt-outs, complaints, responsible-gaming flags, bonus cost, or abuse risk worsen materially.
- Inconclusive result handling: Treat as directional only, or retest if still commercially relevant and safe.
- Rollout rule: Requires RG/compliance review and commercial approval where relevant.
- Retest rule: Retest only with clearer variant isolation or larger eligible audience.
- Stop rule: Stop if suppressions, tracking, `[T&CS]`, or guardrails fail.

## 14. RG & Compliance Review

- Suppression before assignment: Required.
- Suppression before contact: Required.
- Variant risk difference: `[NEEDS CONFIRMATION]`.
- Pressure risk: Avoid aggressive urgency or manipulative framing.
- Deposit pressure risk: Review if deposit or reload is involved.
- Reactivation risk: Use conservative frequency and safe wording.
- `[T&CS]` consistency: Must be equal and visible across variants.
- Required approvals: `[NEEDS CONFIRMATION]`.
- Verdict: Needs RG/compliance review before launch.

## 15. Commercial Risk Review

- Bonus cost risk: `[NEEDS CONFIRMATION]`.
- Open exposure: `[RISK]` if `[MAX_BONUS_VALUE]` is missing.
- Bonus abuse risk: `[NEEDS CONFIRMATION]`.
- Sharp/arb risk: `[NEEDS CONFIRMATION]`.
- Low incrementality: Use `[CONTROL_GROUP]`.
- VIP cost: `[NEEDS CONFIRMATION]` if `[VIP_STATUS]` applies.
- Operational risk: `[NEEDS CONFIRMATION]`.
- Inconclusive test risk: `[RISK]` if `[SAMPLE_SIZE]`, `[SEGMENT_SIZE]`, or `[MEASUREMENT_WINDOW]` is weak.

## 16. Operational Requirements

- Audience build: Required.
- Randomisation setup: Required.
- `[CONTROL_GROUP]` setup: Recommended where incrementality matters.
- Suppression automation: Required.
- Offer setup: Required if offer is included.
- Tracking: Required.
- Link tagging: Required if links are used.
- `[T&CS]` consistency: Required.
- QA: Required.
- Reporting: Required.
- Owner dependencies: `[NEEDS CONFIRMATION]`.

## 17. Post-Campaign Analysis Handoff

- Audience counts: Required.
- Variant assignment: Required.
- Delivery: Required where available.
- Engagement: Required where available.
- Conversion: Required.
- Bonus cost: Required.
- GGR: Required where available.
- NGR: Required where available.
- `[GUARDRAIL_METRICS]`: Required.
- Segment splits: Required where meaningful.
- Time window: `[MEASUREMENT_WINDOW]`.
- `[CONTROL_GROUP]` data: Required if used.
- Notes on anomalies: Required.

## 18. Required Fixes Before Launch

- Issue: Missing measurement framework.
  Risk type: Measurement and commercial.
  Required fix: Confirm `[PRIMARY_KPI]`, `[SECONDARY_KPIS]`, `[GUARDRAIL_METRICS]`, `[MEASUREMENT_WINDOW]`, and `[DECISION_RULE]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.
- Issue: Missing suppression data.
  Risk type: Responsible-gaming and compliance.
  Required fix: Confirm `[SUPPRESSION_RULES]`, `[SELF_EXCLUSION_STATUS]`, `[RG_RISK_STATUS]`, and `[COMMUNICATION_OPT_IN_STATUS]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.
- Issue: Missing tracking readiness.
  Risk type: Operational.
  Required fix: Confirm assignment, conversion, bonus cost, guardrail, and `[CONTROL_GROUP]` tracking.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.

## 19. Recommended Next Skills

- `crm-sportsbook-rg-compliance-review`, if not already completed after final test design.
- `crm-sportsbook-journey-builder`, if journey logic needs finalisation.
- `crm-sportsbook-post-campaign-analysis`, after campaign ends.

## 20. Final Recommendation

- Needs missing inputs before test finalisation.

The test structure is usable, but launch requires confirmed suppression logic, test hypothesis, variants, KPI framework, guardrails, measurement window, decision rule, tracking, and RG/compliance review.
