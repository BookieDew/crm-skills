---
name: crm-sportsbook-journey-builder
description: Turns market-agnostic sportsbook CRM campaign briefs, offers, segments, SMS copy, localisation outputs, and responsible-gaming reviews into safe operational CRM journeys with triggers, entry rules, steps, timing, suppressions, exits, frequency caps, control groups, measurement, and fallback logic.
---

# CRM Sportsbook Journey Builder

## Purpose

This skill helps CRM teams turn campaign strategy into a practical CRM journey.

It helps CRM teams define:

- `[JOURNEY_TRIGGER]`.
- Target audience entry rules.
- `[JOURNEY_STEPS]`.
- Timing.
- Message sequencing.
- `[TARGET_CHANNEL]` usage.
- Reminder logic.
- `[SUPPRESSION_RULES]`.
- `[EXIT_CRITERIA]`.
- `[FREQUENCY_CAPS]`.
- `[CONTROL_GROUP]`.
- Measurement points.
- Operational requirements.
- Responsible-gaming and compliance safety checks.

The skill supports:

- Single-message campaigns.
- Multi-step SMS journeys.
- Event-led journeys.
- Activation journeys.
- Retention journeys.
- Reactivation journeys.
- Deposit or reload journeys.
- VIP journeys, with manual review.
- Tournament or multi-day event journeys.
- Product cross-sell journeys within sportsbook.

This skill designs CRM journey logic. It does not provide final legal approval, final compliance approval, or final customer-facing copy.

## Role in the Skill Pack

This skill usually runs after:

- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`, if SMS is used.
- `crm-sportsbook-localisation`, if localised copy exists.
- `crm-sportsbook-rg-compliance-review`, before final journey approval.

It uses outputs from:

- Market context.
- Event opportunity.
- Player segmentation.
- Offer mechanics.
- Campaign brief.
- SMS copy.
- Localisation.
- Responsible-gaming and compliance review.

It may be selected by `crm-sportsbook-skill-router` when the user asks for journey design, message sequence, reminders, contact cadence, trigger logic, exits, suppressions, frequency caps, control groups, or operational CRM execution.

It feeds:

- `crm-sportsbook-ab-testing`
- `crm-sportsbook-post-campaign-analysis`

It should not:

- Invent market facts.
- Write all final channel copy from scratch.
- Replace `crm-sportsbook-sms-copy`.
- Replace `crm-sportsbook-localisation`.
- Replace `crm-sportsbook-rg-compliance-review`.
- Replace legal approval.
- Override suppressions.
- Design unsafe high-pressure journeys.

It creates the operational journey structure, including the journey trigger and all related entry, timing, suppression, exit, and measurement logic.

## When to Use

Use this skill when the CRM manager needs to:

- Turn a campaign brief into a CRM journey.
- Create a single-message campaign flow.
- Create a multi-step SMS journey.
- Create an event-led communication flow.
- Define pre-event, event-day, reminder, and post-event logic.
- Define activation journey logic.
- Define retention journey logic.
- Define reactivation journey logic.
- Define deposit or reload campaign journey logic.
- Define VIP journey logic with manual review.
- Define entry and exit criteria.
- Define `[SUPPRESSION_RULES]`.
- Define `[FREQUENCY_CAPS]`.
- Define `[CONTROL_GROUP]` logic.
- Define operational setup for CRM execution.
- Define journey measurement points.
- Convert approved copy variants into journey steps.
- Check whether a journey creates excessive pressure or contact frequency.

## When Not to Use

Do not use this skill to:

- Create market context from scratch.
- Select player segments from raw data without segmentation input.
- Design offer mechanics from scratch.
- Write final SMS copy from scratch.
- Localise copy from scratch.
- Provide final legal or compliance approval.
- Override responsible-gaming suppressions.
- Build journeys that target self-excluded or responsible-gaming-risk users.
- Build journeys that encourage chasing losses.
- Build journeys that rely on unconfirmed event dates or schedules.
- Invent channel opt-in rules, regulatory rules, or runtime market requirements.
- Analyse completed campaign performance.

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
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]` or player segmentation output.
- `[OFFER_MECHANIC]` and `[OFFER_VALUE]`, if promotional journey.
- Campaign brief output or enough campaign context to build a journey.
- `[SUPPRESSION_RULES]` or instruction to use shared baseline suppressions.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[EVENT_DATE]`
- `[EVENT_START_TIME]`
- SMS copy output, if SMS is used.
- Localisation output, if localised copy exists.
- RG/compliance review output.
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[CUSTOMER_VALUE_SEGMENT]`
- `[VIP_STATUS]`
- `[BONUS_SENSITIVITY]`
- `[SHARP_OR_ARB_RISK]`
- `[CHURN_RISK]`
- `[RG_RISK_STATUS]`
- `[SELF_EXCLUSION_STATUS]`
- `[COMMUNICATION_OPT_IN_STATUS]`
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
- `[EXIT_CRITERIA]`
- `[CONTROL_GROUP]`
- `[SUCCESS_METRICS]`

### Advanced optional inputs

- CRM platform capabilities.
- Journey automation rules.
- Dynamic audience refresh logic.
- Real-time trigger availability.
- Event calendar feed.
- Offer redemption feed.
- Bet placement feed.
- Deposit feed.
- Opt-in and opt-out feed.
- Responsible-gaming flag feed.
- Self-exclusion feed.
- Bonus abuse flag feed.
- Risk or trading restriction feed.
- BI measurement framework.
- Control group methodology.
- Attribution rules.
- Previous journey performance.
- Previous opt-out rates.
- Previous complaints.
- Message frequency policy.
- Suppression hierarchy.
- VIP manual approval process.
- Runtime market approval process.
- Customer support escalation process.
- Offer configuration dependencies.
- `[T&CS]` page dependencies.
- Tracking link rules.
- Deep link rules.
- `[EXPIRY]` handling rules.
- Fallback logic if `[TARGET_EVENT]` is postponed or offer availability changes.

## Output

The skill should produce:

- Journey summary.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Journey objective.
- Entry criteria.
- Exclusion and suppression logic.
- `[JOURNEY_TRIGGER]`.
- `[JOURNEY_STEPS]`.
- Timing plan.
- Message purpose per step.
- Channel plan.
- Copy placement notes.
- Offer handling.
- `[EXIT_CRITERIA]`.
- `[FREQUENCY_CAPS]`.
- `[CONTROL_GROUP]` recommendation.
- Responsible-gaming and compliance safety checks.
- Commercial risk checks.
- Operational requirements.
- Measurement plan.
- Failure and fallback logic.
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
11. Review `crm-sportsbook-sms-copy` output if available.
12. Review `crm-sportsbook-localisation` output if available.
13. Review `crm-sportsbook-rg-compliance-review` output if available.
14. List all confirmed inputs as `[CONFIRMED]`.
15. Separate confirmed inputs from assumptions.
16. Mark missing journey-critical inputs as `[NEEDS CONFIRMATION]`.
17. Define the journey type:
    - Single-message campaign.
    - Multi-step campaign.
    - Event-led journey.
    - Lifecycle journey.
    - Reactivation journey.
    - VIP journey.
    - Product cross-sell journey.
18. Define entry criteria.
19. Define mandatory exclusions and suppressions.
20. Define `[JOURNEY_TRIGGER]`.
21. Define step-by-step journey flow.
22. Define timing and delay logic.
23. Define `[EXIT_CRITERIA]`.
24. Define `[FREQUENCY_CAPS]`.
25. Define `[CONTROL_GROUP]` logic.
26. Define offer redemption and `[EXPIRY]` handling.
27. Define fallback logic.
28. Check responsible-gaming and compliance safety.
29. Check commercial and operational risks.
30. Define measurement points.
31. Recommend next skill chain.

## Decision Logic

Apply these rules:

- If `[CAMPAIGN_OBJECTIVE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_SEGMENT]` is missing, recommend running `crm-sportsbook-player-segmentation`.
- If `[OFFER_MECHANIC]` is missing for a promotional journey, recommend running `crm-sportsbook-offer-mechanics`.
- If campaign brief is missing, the skill may still build a provisional journey but must label assumptions.
- If `[EVENT_DATE]` or `[EVENT_START_TIME]` is required but missing, mark it as `[NEEDS CONFIRMATION]`.
- If SMS copy is missing for an SMS journey, recommend running `crm-sportsbook-sms-copy`.
- If localisation is required but missing, recommend running `crm-sportsbook-localisation`.
- If RG/compliance review has not been run, recommend running `crm-sportsbook-rg-compliance-review` before launch.
- If `[SUPPRESSION_RULES]` are missing, apply shared baseline suppressions and mark runtime suppressions as `[NEEDS CONFIRMATION]`.
- If `[COMMUNICATION_OPT_IN_STATUS]` is unknown, mark it as `[RISK]`.
- If journey targets self-excluded, responsible-gaming-risk, or cooling-off users, mark it as Do Not Build / Do Not Launch.
- If journey uses repeated reminders, check whether reminders create pressure.
- If the journey is reactivation-focused, avoid emotional pressure and keep frequency conservative.
- If the journey is event-led, avoid excessive last-minute urgency.
- If the journey depends on live betting, flag operational and timing risk.
- If the journey is VIP-focused, require manual review and exposure controls.
- If `[OFFER_MECHANIC]` is complex, reduce the number of steps or move explanation to support page, onsite, inbox, or `[T&CS]`.
- If the journey has no clear `[EXIT_CRITERIA]`, flag it as `[RISK]`.
- If the journey has no `[FREQUENCY_CAPS]`, flag it as `[RISK]`.
- If there is no measurement plan, recommend adding `[CONTROL_GROUP]` and `[SUCCESS_METRICS]`.
- If a customer completes the desired action, they should exit or move to a non-promotional confirmation or thank-you state.
- If a customer opts out, receives an RG restriction, self-excludes, enters cooling-off, or triggers account restrictions, they must exit immediately.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy` when SMS copy exists, `crm-sportsbook-localisation` when localised copy exists, and `crm-sportsbook-rg-compliance-review` before final launch.
- Normally run after this skill: `crm-sportsbook-rg-compliance-review` if the final journey has not been reviewed, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, measurement principles, and final campaign quality checklist.

## Journey Types

Support these journey types.

### Single-Message Campaign

Use when:

- Offer is simple.
- `[TARGET_CHANNEL]` is SMS.
- Event timing is tight.
- No reminders are needed.
- `[CAMPAIGN_OBJECTIVE]` is straightforward.

Include:

- One entry trigger.
- One message.
- Clear exit after send or conversion.
- Suppression check before send.
- Measurement window.

### Multi-Step SMS Journey

Use when:

- Campaign has more than one message.
- Reminder is justified.
- `[EXPIRY]` is meaningful.
- `[TARGET_SEGMENT]` is eligible and safe to contact again.

Include:

- Initial message.
- Reminder only if no conversion.
- Suppression check before each message.
- `[FREQUENCY_CAPS]`.
- Exit on conversion, opt-out, RG flag, self-exclusion, cooling-off, account restriction, or `[EXPIRY]`.

### Event-Led Journey

Use when:

- Campaign is linked to `[TARGET_EVENT]`, `[TARGET_FIXTURE]`, or `[TARGET_TOURNAMENT]`.

Include:

- Pre-event message.
- Optional reminder.
- Optional event-day message.
- Avoid pressure-heavy last-minute wording.
- Fallback if event is postponed, cancelled, or product unavailable.
- Exit after event or `[EXPIRY]`.

### Tournament Journey

Use when:

- Event spans multiple days, rounds, or stages.

Include:

- Stage-based messaging.
- Fatigue controls.
- `[FREQUENCY_CAPS]`.
- Segment refresh rules.
- Exit on conversion or disqualification.
- Post-stage suppression if engagement drops or risk flags appear.

### Activation Journey

Use when:

- Customers need to complete a first action.

Include:

- Simple trigger.
- Low-friction action.
- Educational or value-focused message.
- No high-pressure reminders.
- Exit on first deposit, first bet, or defined conversion action.

### Retention Journey

Use when:

- Customers are active or slightly declining.

Include:

- Relevance-based targeting.
- Avoid over-incentivising natural activity.
- Conservative reminder logic.
- `[CONTROL_GROUP]` for incrementality.

### Reactivation Journey

Use when:

- Customers are dormant and safe to contact.

Include:

- Defined dormancy threshold.
- Strong suppressions.
- Calm copy.
- Limited frequency.
- No loss-recovery framing.
- No pressure language.
- Exit on conversion, no response after defined window, opt-out, RG flag, self-exclusion, cooling-off, or account restriction.

### Deposit / Reload Journey

Use when:

- Deposit or reload offer is approved and appropriate.

Include:

- Deposit eligibility.
- Responsible-gaming sensitivity review.
- Clear bonus terms.
- No financial-solution framing.
- `[FREQUENCY_CAPS]`.
- Exit on deposit, `[EXPIRY]`, RG flag, self-exclusion, cooling-off, account restriction, or opt-out.

### VIP Journey

Use when:

- `[TARGET_SEGMENT]` is an approved VIP audience.

Include:

- Manual review.
- Personal but safe tone.
- Exposure caps.
- Strong responsible-gaming check.
- Relationship-manager or VIP owner approval.
- No automated high-value pressure.

### Product Cross-Sell Journey

Use when:

- Introducing sportsbook product behaviour such as live betting, bet builder, accumulator, or another sport.

Include:

- Education where needed.
- Simple trial mechanic.
- Low-risk offer.
- Segment fit.
- Product availability.
- No nudging into unsuitable or high-risk behaviour.

## Journey Step Design Rules

Each journey step should define:

- Step number.
- Trigger.
- Audience condition.
- Timing.
- Channel.
- Message purpose.
- Copy source or copy placeholder.
- Offer state.
- Suppression check.
- Exit check.
- Tracking event.
- Risk note.

Possible step types:

- Entry check.
- Initial message.
- Reminder message.
- Conversion check.
- Offer expiry reminder.
- Confirmation message.
- Non-converter exit.
- Converted-user exit.
- Suppression exit.
- Manual review queue.
- Fallback message, if approved.
- Reporting event.

## Entry Criteria Rules

Entry criteria should include:

- `[TARGET_SEGMENT]`.
- Channel opt-in.
- Account eligibility.
- Offer eligibility.
- Product eligibility.
- Market eligibility.
- Responsible-gaming eligibility.
- Self-exclusion exclusion.
- Cooling-off exclusion.
- Fraud, AML, or account restriction exclusion.
- Bonus abuse exclusion where relevant.
- `[FREQUENCY_CAPS]` eligibility.
- `[CONTROL_GROUP]` assignment.

## Exit Criteria Rules

Customers should exit if:

- Desired conversion action is completed.
- Offer is redeemed.
- Offer expires.
- Customer opts out.
- Customer becomes self-excluded.
- Customer receives responsible-gaming risk flag.
- Customer enters cooling-off.
- Customer receives account restriction.
- Customer becomes ineligible for the offer.
- `[FREQUENCY_CAPS]` are reached.
- Event ends or is cancelled or postponed, depending on logic.
- Journey window ends.
- Manual review rejects eligibility.

## Suppression Rules

The journey must apply suppression checks:

- Before journey entry.
- Before every message send.
- Before offer award where relevant.
- Before reminder sends.
- Before VIP outreach.
- Before reactivation messaging.

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
- Users recently heavy-losing, where relevant to reactivation or incentive campaign.

## Timing Rules

The skill should define safe timing logic.

For SMS:

- Avoid excessive frequency.
- Avoid repeated urgent reminders.
- Avoid inappropriate send times unless approved at runtime.
- Avoid event reminders that pressure immediate betting.
- Allow enough time for customer understanding.
- Respect `[FREQUENCY_CAPS]`.

For event-led campaigns:

- Pre-event message should allow enough time.
- Event-day message should be simple.
- Live or in-play journeys require operational caution.
- Post-event messages should avoid loss references.

For reactivation:

- Use limited touchpoints.
- Avoid escalating pressure.
- Avoid "last chance" wording unless approved and not manipulative.

For VIP:

- Prefer manual or semi-manual timing review.

## Control Group Rules

The skill should recommend control groups when measurement matters.

Include:

- `[CONTROL_GROUP]` purpose.
- Suggested holdout logic.
- Exclusions from `[CONTROL_GROUP]`.
- Measurement window.
- Primary KPI.
- Guardrail metrics.
- Incrementality notes.

Do not invent exact percentages unless the user provides requirements or explicitly asks for assumptions.

## Measurement Rules

The journey should define tracking for:

- Audience entered.
- Message sent.
- Message delivered.
- Clicked, if links exist.
- Offer viewed.
- Offer opted in.
- Deposit made, if relevant.
- Bet placed.
- Bonus awarded.
- Bonus redeemed.
- Conversion completed.
- Revenue generated.
- Bonus cost.
- Opt-out.
- Complaint.
- Responsible-gaming flag after contact.
- Exit reason.
- `[CONTROL_GROUP]` comparison.

## Sportsbook-Specific Journey Considerations

The skill should consider, without inventing local facts:

- Event timing.
- Fixture or tournament schedule.
- `[EXPIRY]`.
- Odds or market availability.
- Product availability.
- Pre-match vs live timing.
- In-play suspension risk.
- Bet settlement timing.
- Single vs accumulator behaviour.
- Bet builder availability.
- Odds boost exposure.
- Cashback calculation window.
- Free bet expiry.
- Deposit or reload sensitivity.
- VIP approval.
- Sharp or arb restrictions.
- Bonus abuse restrictions.
- Trading or risk review.
- Margin protection.
- Frequency fatigue around major events.
- Responsible-gaming monitoring after campaign.

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

All journey-specific and market-specific details must come from:

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

Do not present assumptions as facts. Do not invent market facts, current fixtures, event schedules, local behaviour, or local requirements.

## Channel-Aware Journey Rules

### SMS

For SMS journeys:

- Keep journey short.
- Prefer one message plus one reminder at most unless justified.
- Use simple copy.
- Check SMS opt-in before every send.
- Respect `[FREQUENCY_CAPS]`.
- Use `[T&CS_LINK]` or short `[T&CS]` cue.
- Avoid pressure-heavy reminders.
- Track opt-outs.
- Track delivery and conversion.
- Feed copy changes back to `crm-sportsbook-sms-copy`.

### Email

For email journeys:

- Do not write full email copy.
- Note that detailed email execution should be handled by a future email-specific skill.
- Email can support more explanation, but journey frequency still needs controls.

### Push

For push journeys:

- Do not write full push copy.
- Note that detailed push execution should be handled by a future push-specific skill.
- Push urgency must be carefully controlled.

### Onsite / Inbox

For onsite or inbox:

- Use as supporting explanation when SMS is too short.
- Ensure offer details and `[T&CS]` are clear.

### VIP Outreach

For VIP journeys:

- Require manual review.
- Require safe engagement profile.
- Use exposure caps.
- Avoid automated high-pressure reminders.
- Keep owner accountability clear.

## Responsible Gaming & Compliance Guardrails

The skill must follow shared responsible-gaming principles.

It must reject or require redesign for journeys that:

- Target self-excluded users.
- Target users with responsible-gaming risk flags.
- Target users in cooling-off periods.
- Contact users without channel opt-in.
- Encourage chasing losses.
- Use recent losses as a trigger.
- Use financial pressure.
- Use shame, guilt, or emotional pressure.
- Escalate urgency through repeated reminders.
- Push deposit or reload behaviour aggressively.
- Encourage excessive bet frequency.
- Encourage excessive accumulator complexity.
- Use VIP status to over-incentivise risky behaviour.
- Continue contacting users after opt-out, responsible-gaming flag, self-exclusion, cooling-off, account restriction, `[EXPIRY]`, or conversion.

Every journey must include:

- Suppression check before entry.
- Suppression check before each send.
- Exit on opt-out.
- Exit on responsible-gaming flag.
- Exit on self-exclusion.
- Exit on cooling-off.
- Exit on account restriction.
- `[FREQUENCY_CAPS]`.
- RG/compliance review before launch.

## Compliance Guardrails

The skill must flag:

- Missing `[REGULATORY_NOTES]`.
- Missing opt-in handling.
- Missing opt-out handling where required.
- Missing `[T&CS]`.
- Missing runtime approval workflow.
- Missing age, verification, or account eligibility handling where relevant.
- Missing offer eligibility rules.
- Missing suppression logic.
- Missing consent handling.
- Missing journey audit trail.
- Missing fallback logic for changed event or offer availability.

The skill must not claim that a journey is compliant unless required inputs and approvals are supplied.

## Commercial Guardrails

The skill must flag:

- Excessive contact frequency.
- Low incrementality.
- Bonus cost exposure.
- Uncapped rewards.
- Bonus abuse risk.
- Sharp or arb exposure.
- VIP over-costing.
- Over-incentivising natural activity.
- Offer leakage to unintended segments.
- Operational setup gaps.
- Tracking gaps.
- Poor `[CONTROL_GROUP]` design.
- Support burden from unclear journey rules.

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

- Journey feels helpful, not pushy.
- Message sequence is easy to understand.
- Customer is not over-contacted.
- `[OFFER_VALUE]` is clear.
- `[CTA]` is clear.
- `[T&CS]` are accessible.
- Reminders are not manipulative.
- Personalisation is not invasive.
- Tone respects `[BRAND_TONE]`.
- Journey does not stereotype `[TARGET_MARKET]`.
- Betting is not framed as necessary to enjoy an event.
- Customer exits journey after conversion.

## Fallback Logic

The journey should include fallback rules for:

- Event postponed.
- Event cancelled.
- `[EVENT_START_TIME]` changed.
- Offer configuration unavailable.
- Market unavailable.
- Product unavailable.
- Customer becomes ineligible.
- Customer opts out.
- Customer triggers responsible-gaming flag.
- Customer self-excludes.
- `[T&CS]` page unavailable.
- Tracking link unavailable.
- CRM platform failure.
- Message delivery failure.

Do not invent fallback copy unless requested.

## Assumption Labels

Use these labels consistently:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked before launch.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

Use this response format when the skill is activated:

# Journey Builder Output

## 1. Journey Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Offer value: `[OFFER_VALUE]`
- Journey type:
- Material used:

## 2. Confirmed Inputs

List all confirmed user-provided facts and relevant prior skill outputs.

## 3. Working Assumptions

List assumptions clearly.

## 4. Needs Confirmation

List missing or uncertain journey, market, timing, offer, channel, suppression, compliance, or operational details.

## 5. Journey Summary

Provide a short summary of the recommended journey.

Include:

- Journey objective:
- Entry trigger:
- Number of steps:
- Main conversion action:
- Exit logic:
- Launch readiness:

## 6. Entry Criteria

Define:

- Inclusion criteria:
- Channel eligibility:
- Offer eligibility:
- Product eligibility:
- Account eligibility:
- Responsible-gaming eligibility:
- `[FREQUENCY_CAPS]` eligibility:
- `[CONTROL_GROUP]` assignment:

## 7. Exclusions & Suppressions

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

## 8. Journey Flow

Provide a step-by-step flow.

For each step:

- Step number:
- Step name:
- Trigger:
- Timing:
- Audience condition:
- Channel:
- Message purpose:
- Copy source / copy placeholder:
- Offer state:
- Suppression check:
- Exit check:
- Tracking event:
- Risk notes:

## 9. Timing Plan

Define:

- Launch timing:
- Delay between steps:
- Reminder timing:
- `[EXPIRY]` handling:
- Event timing dependency:
- Send-time restrictions:
- `[FREQUENCY_CAPS]`:

## 10. Exit Criteria

List all exit conditions:

- Conversion:
- Offer redeemed:
- Offer expired:
- Opt-out:
- Responsible-gaming flag:
- Self-exclusion:
- Cooling-off:
- Account restriction:
- Event ended or cancelled:
- Journey window ended:
- Manual review rejection:

## 11. Offer Handling

Define:

- Offer award logic:
- Qualification check:
- Redemption check:
- `[EXPIRY]`:
- Max reward:
- `[ELIGIBLE_MARKETS]`:
- `[T&CS]` dependency:
- Abuse controls:

## 12. Channel Considerations

Assess:

- SMS/email/push/inbox/VIP suitability:
- Message length risk:
- Frequency risk:
- `[CTA]` clarity:
- `[T&CS]` handling:
- Opt-in/opt-out handling:

## 13. RG & Compliance Review

Assess:

- Suppression before entry:
- Suppression before each send:
- Responsible-gaming-risk exits:
- Reactivation pressure risk:
- Deposit pressure risk:
- Event urgency risk:
- Required approvals:
- Verdict:

## 14. Commercial Risk Review

Assess:

- Bonus cost risk:
- Open exposure:
- Bonus abuse risk:
- Sharp/arb risk:
- Low incrementality:
- VIP cost:
- Operational risk:
- Support burden:

## 15. Operational Requirements

List:

- Audience build:
- Suppression automation:
- Offer setup:
- Promo/token setup:
- `[T&CS]` page:
- Tracking links:
- Deep links:
- `[CONTROL_GROUP]`:
- QA:
- Reporting:
- Fallback setup:
- Owner dependencies:

## 16. Control Group Recommendation

Define:

- `[CONTROL_GROUP]` purpose:
- Holdout logic:
- Eligibility:
- Measurement window:
- Primary KPI:
- Guardrail metrics:
- Decision rule:

## 17. Measurement Plan

Define:

- Primary KPI:
- Secondary KPIs:
- Commercial KPIs:
- Responsible-gaming/UX guardrail metrics:
- Journey-step tracking:
- Exit reason tracking:
- Measurement window:
- Post-campaign analysis inputs:

## 18. Fallback Logic

Define:

- Event postponed:
- Event cancelled:
- Offer unavailable:
- Product or market unavailable:
- Customer becomes ineligible:
- Link or `[T&CS]` issue:
- CRM delivery issue:
- Tracking issue:

## 19. Required Fixes Before Launch

List exact required changes.

For each:

- Issue:
- Risk type:
- Required fix:
- Owner:
- Blocking status: Blocking / Non-blocking.

## 20. Recommended Next Skills

Recommend next skill chain.

Examples:

- `crm-sportsbook-rg-compliance-review`, if not already completed after final journey design.
- `crm-sportsbook-ab-testing`.
- `crm-sportsbook-post-campaign-analysis`.

## 21. Final Recommendation

Use one:

- Ready for RG/compliance review.
- Needs missing inputs before journey finalisation.
- Needs copy/localisation before journey finalisation.
- Needs offer/commercial approval before journey finalisation.
- Needs specialist review before launch.
- Not recommended based on current information.

Explain why.

## Example User Request

Use a market-neutral example with placeholders only.

Example:

"Build a CRM journey for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`, channel is `[TARGET_CHANNEL]`, offer is `[OFFER_VALUE]` via `[OFFER_MECHANIC]`, and the campaign is linked to `[TARGET_EVENT]`."

## Example Output

Use placeholders only. Do not include a real country, region, language, league, tournament, team, operator, payment method, regulation, regulator, slang, or cultural reference.

# Journey Builder Output

## 1. Journey Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Offer value: `[OFFER_VALUE]`
- Journey type: Single-message campaign with one optional neutral reminder.
- Material used: Campaign brief, SMS copy output, offer mechanics output, and RG/compliance review output supplied at runtime.

## 2. Confirmed Inputs

- `[CONFIRMED]` `[TARGET_MARKET]` supplied at runtime.
- `[CONFIRMED]` `[TARGET_CHANNEL]` supplied at runtime.
- `[CONFIRMED]` `[TARGET_SEGMENT]` supplied at runtime.
- `[CONFIRMED]` `[OFFER_MECHANIC]` and `[OFFER_VALUE]` supplied at runtime.
- `[CONFIRMED]` `[TARGET_EVENT]` supplied at runtime.

## 3. Working Assumptions

- `[ASSUMPTION]` Shared baseline suppression rules apply unless detailed `[SUPPRESSION_RULES]` are provided.
- `[ASSUMPTION]` Journey should remain short because `[TARGET_CHANNEL]` is SMS.

## 4. Needs Confirmation

- `[NEEDS CONFIRMATION]` `[EVENT_DATE]` and `[EVENT_START_TIME]`.
- `[NEEDS CONFIRMATION]` `[COMMUNICATION_OPT_IN_STATUS]`.
- `[NEEDS CONFIRMATION]` `[SELF_EXCLUSION_STATUS]` handling.
- `[NEEDS CONFIRMATION]` `[RG_RISK_STATUS]` handling.
- `[NEEDS CONFIRMATION]` `[FREQUENCY_CAPS]`.
- `[NEEDS CONFIRMATION]` `[T&CS_LINK]`.
- `[NEEDS CONFIRMATION]` `[REGULATORY_NOTES]`.

## 5. Journey Summary

- Journey objective: Move eligible `[TARGET_SEGMENT]` toward the campaign conversion action linked to `[CAMPAIGN_OBJECTIVE]`.
- Entry trigger: `[JOURNEY_TRIGGER]`.
- Number of steps: One initial message plus one optional reminder if safe and justified.
- Main conversion action: Customer uses `[OFFER_MECHANIC]` with `[OFFER_VALUE]`.
- Exit logic: Exit on conversion, opt-out, responsible-gaming flag, self-exclusion, cooling-off, account restriction, `[EXPIRY]`, or event end.
- Launch readiness: Needs missing inputs before journey finalisation.

## 6. Entry Criteria

- Inclusion criteria: `[TARGET_SEGMENT]` eligible for `[CAMPAIGN_OBJECTIVE]`.
- Channel eligibility: `[COMMUNICATION_OPT_IN_STATUS]` confirmed for `[TARGET_CHANNEL]`.
- Offer eligibility: Customer eligible for `[OFFER_MECHANIC]`.
- Product eligibility: Product availability confirmed.
- Account eligibility: No account restriction.
- Responsible-gaming eligibility: No `[RG_RISK_STATUS]` restriction, self-exclusion, or cooling-off.
- `[FREQUENCY_CAPS]` eligibility: Not exceeded.
- `[CONTROL_GROUP]` assignment: Exclude assigned holdout users from journey sends.

## 7. Exclusions & Suppressions

- Self-exclusion: Suppress before entry and before each send.
- Responsible-gaming risk flags: Suppress and exit immediately.
- Cooling-off: Suppress and exit immediately.
- Channel opt-out: Suppress and exit immediately.
- Compliance/account restrictions: Suppress.
- AML/fraud restrictions: Suppress.
- Bonus abuse restrictions: Suppress or route to manual review.
- Sharp/arb restrictions: Suppress or route to risk review.
- VIP manual review: Required if `[VIP_STATUS]` applies.
- Recently heavy-losing users, if relevant: Suppress or route to RG/compliance review.
- Other supplied `[SUPPRESSION_RULES]`: Apply before every send.

## 8. Journey Flow

- Step number: 0
  Step name: Entry and suppression check.
  Trigger: `[JOURNEY_TRIGGER]`.
  Timing: Before any message send.
  Audience condition: `[TARGET_SEGMENT]` and all eligibility checks passed.
  Channel: Internal CRM logic.
  Message purpose: None.
  Copy source / copy placeholder: Not applicable.
  Offer state: Eligible but not awarded unless journey rules confirm.
  Suppression check: Required.
  Exit check: Exit if any mandatory suppression applies.
  Tracking event: Audience entered or suppressed.
  Risk notes: `[RISK]` Missing suppression data blocks launch.
- Step number: 1
  Step name: Initial SMS.
  Trigger: Eligible audience after entry check.
  Timing: `[NEEDS CONFIRMATION]` based on event timing and `[FREQUENCY_CAPS]`.
  Audience condition: Not in `[CONTROL_GROUP]`, not suppressed, channel opt-in confirmed.
  Channel: SMS.
  Message purpose: Present one clear offer and `[CTA]`.
  Copy source / copy placeholder: Approved SMS variant from `crm-sportsbook-sms-copy`.
  Offer state: Available if configured.
  Suppression check: Required immediately before send.
  Exit check: Exit on opt-out, conversion, responsible-gaming flag, self-exclusion, cooling-off, account restriction, `[EXPIRY]`, or event end.
  Tracking event: Message sent, delivered, clicked if link exists, offer viewed, conversion.
  Risk notes: Keep copy short and non-pressuring.
- Step number: 2
  Step name: Optional neutral reminder.
  Trigger: No conversion after Step 1 and reminder is justified.
  Timing: `[NEEDS CONFIRMATION]`.
  Audience condition: Still eligible, not converted, not opted out, not suppressed, within `[FREQUENCY_CAPS]`.
  Channel: SMS.
  Message purpose: Neutral reminder of existing offer.
  Copy source / copy placeholder: Approved reminder copy from `crm-sportsbook-sms-copy`.
  Offer state: Still active and within `[EXPIRY]`.
  Suppression check: Required immediately before send.
  Exit check: Exit on conversion, opt-out, responsible-gaming flag, self-exclusion, cooling-off, account restriction, `[EXPIRY]`, or event end.
  Tracking event: Reminder sent, delivered, clicked if link exists, conversion, opt-out.
  Risk notes: Do not escalate urgency or increase incentive value without review.

## 9. Timing Plan

- Launch timing: `[NEEDS CONFIRMATION]`.
- Delay between steps: `[NEEDS CONFIRMATION]`.
- Reminder timing: Only if non-pressuring and inside `[FREQUENCY_CAPS]`.
- `[EXPIRY]` handling: Stop sends after `[EXPIRY]`.
- Event timing dependency: `[EVENT_DATE]` and `[EVENT_START_TIME]` must be confirmed.
- Send-time restrictions: `[NEEDS CONFIRMATION]`.
- `[FREQUENCY_CAPS]`: `[NEEDS CONFIRMATION]`.

## 10. Exit Criteria

- Conversion: Exit immediately.
- Offer redeemed: Exit immediately.
- Offer expired: Exit immediately.
- Opt-out: Exit immediately.
- Responsible-gaming flag: Exit immediately.
- Self-exclusion: Exit immediately.
- Cooling-off: Exit immediately.
- Account restriction: Exit immediately.
- Event ended or cancelled: Exit or use approved fallback logic.
- Journey window ended: Exit.
- Manual review rejection: Exit.

## 11. Offer Handling

- Offer award logic: `[NEEDS CONFIRMATION]`.
- Qualification check: Validate `[MINIMUM_STAKE]`, `[MINIMUM_ODDS]`, and `[ELIGIBLE_MARKETS]` if relevant.
- Redemption check: Track offer use.
- `[EXPIRY]`: `[NEEDS CONFIRMATION]`.
- Max reward: `[MAX_BONUS_VALUE]`.
- `[ELIGIBLE_MARKETS]`: `[NEEDS CONFIRMATION]`.
- `[T&CS]` dependency: `[T&CS_LINK]` required before launch.
- Abuse controls: Apply bonus abuse, sharp, arb, and risk restrictions.

## 12. Channel Considerations

- SMS/email/push/inbox/VIP suitability: SMS is suitable only if the offer is simple and opt-in is confirmed.
- Message length risk: Use approved SMS copy only.
- Frequency risk: Limit to one initial message plus one justified reminder.
- `[CTA]` clarity: `[NEEDS CONFIRMATION]`.
- `[T&CS]` handling: `[T&CS_LINK]` required.
- Opt-in/opt-out handling: `[COMMUNICATION_OPT_IN_STATUS]` and opt-out handling required.

## 13. RG & Compliance Review

- Suppression before entry: Required.
- Suppression before each send: Required.
- Responsible-gaming-risk exits: Required.
- Reactivation pressure risk: Keep frequency conservative if reactivation.
- Deposit pressure risk: Review if deposit or reload is involved.
- Event urgency risk: Avoid pressure-heavy last-minute reminders.
- Required approvals: `[NEEDS CONFIRMATION]`.
- Verdict: Needs RG/compliance review before launch.

## 14. Commercial Risk Review

- Bonus cost risk: `[NEEDS CONFIRMATION]`.
- Open exposure: `[RISK]` if `[MAX_BONUS_VALUE]` is missing.
- Bonus abuse risk: `[NEEDS CONFIRMATION]`.
- Sharp/arb risk: `[NEEDS CONFIRMATION]`.
- Low incrementality: Use `[CONTROL_GROUP]`.
- VIP cost: `[NEEDS CONFIRMATION]` if `[VIP_STATUS]` applies.
- Operational risk: `[NEEDS CONFIRMATION]`.
- Support burden: `[RISK]` if journey rules or `[T&CS]` are unclear.

## 15. Operational Requirements

- Audience build: Define target and suppression logic.
- Suppression automation: Required before entry and each send.
- Offer setup: `[NEEDS CONFIRMATION]`.
- Promo/token setup: `[NEEDS CONFIRMATION]` if used.
- `[T&CS]` page: `[NEEDS CONFIRMATION]`.
- Tracking links: `[NEEDS CONFIRMATION]`.
- Deep links: `[NEEDS CONFIRMATION]` if used.
- `[CONTROL_GROUP]`: Recommended.
- QA: Required.
- Reporting: Required.
- Fallback setup: Required if event or offer availability can change.
- Owner dependencies: `[NEEDS CONFIRMATION]`.

## 16. Control Group Recommendation

- `[CONTROL_GROUP]` purpose: Measure incrementality and avoid over-crediting natural activity.
- Holdout logic: Assign before journey entry using approved methodology.
- Eligibility: Same eligible audience as target group, excluding mandatory suppressions.
- Measurement window: `[NEEDS CONFIRMATION]`.
- Primary KPI: `[SUCCESS_METRICS]`.
- Guardrail metrics: Opt-out, complaints, responsible-gaming flags, bonus cost, and support contacts.
- Decision rule: `[NEEDS CONFIRMATION]`.

## 17. Measurement Plan

- Primary KPI: `[SUCCESS_METRICS]`.
- Secondary KPIs: Delivery, click, offer uptake, deposit if relevant, bet conversion, and retention.
- Commercial KPIs: Bonus cost, turnover, GGR, NGR, and incrementality where available.
- Responsible-gaming/UX guardrail metrics: Opt-out, complaints, and responsible-gaming flags after contact.
- Journey-step tracking: Track entry, sends, delivery, clicks, conversions, reminders, exits, and suppressions.
- Exit reason tracking: Required.
- Measurement window: `[NEEDS CONFIRMATION]`.
- Post-campaign analysis inputs: Provide journey steps, audience counts, offer cost, conversion, revenue, guardrail metrics, and exit reasons to `crm-sportsbook-post-campaign-analysis`.

## 18. Fallback Logic

- Event postponed: Pause journey and require approved revised timing.
- Event cancelled: Stop event-led sends unless approved fallback exists.
- Offer unavailable: Stop sends and prevent awards.
- Product or market unavailable: Stop affected steps and flag operational issue.
- Customer becomes ineligible: Exit immediately.
- Link or `[T&CS]` issue: Stop sends until fixed.
- CRM delivery issue: Pause and QA before retry.
- Tracking issue: Do not launch or pause until measurement is restored if tracking is required.

## 19. Required Fixes Before Launch

- Issue: Missing suppression data.
  Risk type: Responsible-gaming and compliance.
  Required fix: Confirm `[SELF_EXCLUSION_STATUS]`, `[RG_RISK_STATUS]`, cooling-off handling, `[COMMUNICATION_OPT_IN_STATUS]`, and `[SUPPRESSION_RULES]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.
- Issue: Missing timing details.
  Risk type: Operational and UX.
  Required fix: Confirm `[EVENT_DATE]`, `[EVENT_START_TIME]`, `[EXPIRY]`, launch timing, reminder timing, and `[FREQUENCY_CAPS]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking if event-led or time-limited.
- Issue: Missing terms handling.
  Risk type: Compliance and UX.
  Required fix: Confirm `[T&CS]` and `[T&CS_LINK]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.

## 20. Recommended Next Skills

- `crm-sportsbook-rg-compliance-review`, if not already completed after final journey design.
- `crm-sportsbook-ab-testing`, to define journey variant, holdout, KPI, and decision rules.
- `crm-sportsbook-post-campaign-analysis`, after campaign completion.

## 21. Final Recommendation

- Needs missing inputs before journey finalisation.

The provisional journey structure is usable, but launch requires confirmed suppression handling, opt-in status, event timing where relevant, `[T&CS_LINK]`, `[FREQUENCY_CAPS]`, and RG/compliance review.
