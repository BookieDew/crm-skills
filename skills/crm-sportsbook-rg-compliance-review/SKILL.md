---
name: crm-sportsbook-rg-compliance-review
description: Reviews market-agnostic sportsbook CRM campaigns, offers, customer segments, copy, journeys, and localisation outputs for responsible-gaming, compliance, commercial, UX, brand, suppression, T&C, and operational risk before launch. This is a structured pre-review only, not final legal or compliance approval.
---

# CRM Sportsbook Responsible Gaming & Compliance Review

## Purpose

This skill reviews sportsbook CRM campaign material for responsible-gaming, compliance, commercial, UX, and brand risks before launch.

It helps CRM teams identify:

- Targeting risks.
- Responsible-gaming risks.
- Suppression gaps.
- Offer mechanic risks.
- Copy risks.
- `[T&CS]` clarity risks.
- Localisation risks.
- Channel risks.
- Commercial exposure risks.
- Operational readiness issues.
- Items requiring manual compliance, legal, responsible-gaming, risk, trading, product, VIP, BI, or market-owner review.

The skill produces a clear launch recommendation:

- Pass.
- Needs Revision.
- Do Not Launch.
- Requires Specialist Review.

This skill is a structured pre-review and risk detection tool for CRM planning. It is not a substitute for legal, compliance, responsible-gaming, risk, trading, product, or market-owner approval.

## Role in the Skill Pack

This skill is the final safety and quality gate before campaign launch.

It usually runs after:

- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-sms-copy`
- `crm-sportsbook-localisation`

It may also review outputs from:

- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`
- `crm-sportsbook-player-segmentation`

It may be selected by `crm-sportsbook-skill-router` when the user asks for responsible-gaming review, compliance review, launch readiness, safer rewrites, copy risk detection, offer risk review, journey risk review, or campaign improvement.

It feeds:

- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`
- `crm-sportsbook-post-campaign-analysis`

It should not:

- Replace final legal approval.
- Replace runtime compliance approval.
- Invent market regulation.
- Approve campaigns where required `[REGULATORY_NOTES]` are missing.
- Override responsible-gaming suppressions.
- Rewrite the entire campaign strategy unless needed for safety.
- Create new offers from scratch unless recommending safer alternatives.

## When to Use

Use this skill when the CRM manager needs to:

- Review a campaign before launch.
- Check SMS copy for responsible-gaming or compliance risks.
- Review an `[OFFER_MECHANIC]`.
- Review a campaign brief.
- Review localisation output.
- Review a reactivation campaign.
- Review a deposit or reload campaign.
- Review a VIP campaign.
- Review an event-led campaign.
- Review a multi-step journey.
- Check `[SUPPRESSION_RULES]`.
- Check opt-in and channel eligibility.
- Check risky wording.
- Check `[T&CS]` visibility.
- Check whether "risk-free", "guaranteed", "free money", or urgency wording is safe.
- Check whether `[TARGET_SEGMENT]` should be excluded.
- Identify required manual approvals.
- Produce a final pre-launch risk summary.

## When Not to Use

Do not use this skill to:

- Provide final legal advice.
- Replace a compliance officer, legal reviewer, or responsible-gaming team.
- Invent local legal requirements.
- Draft full legal `[T&CS]`.
- Create market research from scratch.
- Create campaign strategy from scratch.
- Write final SMS copy from scratch unless only small safer rewrites are needed.
- Approve campaigns with missing critical compliance inputs.
- Approve campaigns targeted at excluded or responsible-gaming-risk users.
- Override `[REGULATORY_NOTES]`, internal policy, or runtime approval requirements.
- Make claims about specific laws unless supplied by the user, internal policy, or confirmed research.

Route those requests to the appropriate skills or human review:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- SMS copy: `crm-sportsbook-sms-copy`.
- Localisation: `crm-sportsbook-localisation`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_SEGMENT]` or segmentation output.
- `[OFFER_MECHANIC]` and `[OFFER_VALUE]`, if reviewing an offer.
- `[CAMPAIGN_MATERIAL]` or campaign brief, copy, localisation, segment, offer, or journey material to review.
- `[SUPPRESSION_RULES]` or instruction to use shared baseline suppressions.

### Recommended inputs

- Campaign brief output.
- SMS copy output.
- Localisation output.
- Offer mechanics output.
- Player segmentation output.
- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
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
- `[T&CS]`
- `[T&CS_LINK]`
- `[CTA]`
- `[BRAND_NAME]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- `[LOCALISATION_NOTES]`
- `[APPROVED_TERMS]`
- `[FORBIDDEN_TERMS]`
- `[OPT_OUT_TEXT]`
- `[COPY_VARIANTS]`
- `[JOURNEY_STEPS]`

### Advanced optional inputs

- Runtime compliance checklist.
- Legal sign-off requirements.
- Responsible-gaming policy.
- Internal suppression rules.
- Cooling-off rules.
- Self-exclusion logic.
- Channel opt-in policy.
- Age, identity, or account verification rules.
- AML or fraud restrictions.
- Bonus abuse rules.
- VIP manual review policy.
- Trading or risk restrictions.
- Product availability notes.
- Promotion approval workflow.
- Historical complaints.
- Prior campaign responsible-gaming incident data.
- Customer support escalation notes.
- Previous opt-out rates.
- Previous campaign performance.
- Control group rules.
- Frequency cap rules.
- Journey timing rules.
- Runtime disclaimer requirements.
- Required safer-gambling wording.
- Required `[OPT_OUT_TEXT]`.
- Approved claims glossary.
- Forbidden claims glossary.

## Output

The skill should produce:

- Review verdict.
- Risk level.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Responsible-gaming review.
- Compliance review.
- Suppression review.
- Segment risk review.
- Offer mechanic review.
- Copy and claims review.
- `[T&CS]` clarity review.
- Channel suitability review.
- Localisation review.
- Commercial risk review.
- Operational readiness review.
- Required fixes.
- Safer wording rewrites, where relevant.
- Required approvals.
- Final recommendation.
- Recommended next skills.

## Workflow

1. Identify what is being reviewed:
   - Campaign brief.
   - Offer mechanic.
   - SMS copy.
   - Localisation.
   - Journey.
   - Segment.
   - Full campaign package.
2. Identify `[TARGET_MARKET]` as runtime context only.
3. Identify `[TARGET_CHANNEL]`.
4. Identify `[CAMPAIGN_OBJECTIVE]`.
5. Identify `[TARGET_SEGMENT]`.
6. Identify `[OFFER_MECHANIC]` and `[OFFER_VALUE]`, if applicable.
7. Load and apply `crm-sportsbook-shared-principles`.
8. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
9. Read `crm-sportsbook-campaign-brief` output if available.
10. Read `crm-sportsbook-sms-copy` output if available.
11. Read `crm-sportsbook-localisation` output if available.
12. Read `crm-sportsbook-offer-mechanics` output if available.
13. Read `crm-sportsbook-player-segmentation` output if available.
14. Read `crm-sportsbook-market-context` and `crm-sportsbook-event-opportunity` outputs if relevant.
15. List all confirmed inputs as `[CONFIRMED]`.
16. Separate confirmed inputs from assumptions.
17. Mark missing review-critical inputs as `[NEEDS CONFIRMATION]`.
18. Check mandatory suppression logic.
19. Check responsible-gaming risks.
20. Check compliance and regulatory uncertainty.
21. Check segment targeting risks.
22. Check offer mechanic risks.
23. Check copy claims and wording risks.
24. Check `[T&CS]` visibility and clarity.
25. Check channel suitability.
26. Check localisation risks.
27. Check commercial exposure and abuse risks.
28. Check operational readiness.
29. Assign a verdict.
30. Provide required fixes.
31. Provide safer rewrites where appropriate.
32. List required human approvals.
33. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[REGULATORY_NOTES]` are missing, do not claim compliance. Mark them as `[NEEDS CONFIRMATION]`.
- If `[SUPPRESSION_RULES]` are missing, apply shared baseline suppression rules and mark runtime suppression rules as `[NEEDS CONFIRMATION]`.
- If `[SELF_EXCLUSION_STATUS]` handling is missing, mark it as `[RISK]`.
- If `[RG_RISK_STATUS]` handling is missing, mark it as `[RISK]`.
- If `[COMMUNICATION_OPT_IN_STATUS]` is missing for `[TARGET_CHANNEL]`, mark it as `[RISK]`.
- If the campaign targets self-excluded users, the verdict must be Do Not Launch.
- If the campaign targets users with active responsible-gaming restrictions or cooling-off restrictions, the verdict must be Do Not Launch.
- If the campaign targets recently heavy-losing users with incentives, the verdict should be Do Not Launch or Requires Specialist Review.
- If the campaign encourages chasing losses, the verdict must be Do Not Launch until rewritten.
- If copy references previous losses, debt, financial pressure, or recovery, the verdict must be Needs Revision or Do Not Launch.
- If copy implies guaranteed profit or guaranteed winning, the verdict must be Needs Revision or Do Not Launch.
- If copy uses "risk-free", "free money", or equivalent claims without explicit approval in `[REGULATORY_NOTES]` and `[T&CS]`, mark it as `[RISK]` and require revision.
- If `[T&CS]` or `[T&CS_LINK]` are missing or materially unclear, the verdict cannot be Pass.
- If the offer has open-ended exposure, mark commercial risk and require `[MAX_BONUS_VALUE]` or equivalent caps.
- If offer terms are too complex for SMS, require simplification or supporting `[T&CS]`, onsite, inbox, or landing-page explanation.
- If `[CAMPAIGN_OBJECTIVE]` is VIP engagement, require manual review.
- If `[SHARP_OR_ARB_RISK]` is present, require risk or trading review, audience exclusion, or mechanic constraints.
- If bonus abuse exposure is high, require commercial or risk review.
- If `[CAMPAIGN_OBJECTIVE]` is reactivation, check for emotional pressure and risky targeting.
- If the campaign is event-led, check that betting is not framed as necessary to enjoy `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, or `[TARGET_FIXTURE]`.
- If localisation changes offer meaning, require review.
- If legal or responsible-gaming wording is required but absent, mark it as `[NEEDS CONFIRMATION]`.
- If critical unknowns remain, the verdict should be Needs Revision or Requires Specialist Review, not Pass.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, and `crm-sportsbook-localisation`.
- Normally run after this skill: `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, measurement principles, and final campaign quality checklist.

## Sportsbook-Specific Considerations

Review sportsbook CRM material for:

- Sport and event relevance.
- Pre-match vs live betting implications.
- Single bet vs accumulator behaviour.
- Bet builder suitability.
- Odds boost suitability.
- Free bet suitability.
- Cashback suitability.
- Deposit and reload pressure.
- Mission or challenge pressure.
- Bonus history and bonus sensitivity.
- VIP status and manual review.
- Recreational vs sharp behaviour.
- Arb-sensitive exposure.
- Churn and reactivation sensitivity.
- Stake level and value tier.
- Margin protection.
- Event timing and operational readiness.
- In-play suspension or settlement complexity.
- Bonus abuse risk.
- Channel opt-in, opt-out, and frequency caps.
- Post-campaign responsible-gaming monitoring.

## Review Verdicts

Use one of the following verdicts.

### Pass

Use only when:

- No major responsible-gaming, compliance, commercial, UX, brand, or operational risks are detected.
- Suppression logic is clear.
- Channel eligibility is clear.
- `[T&CS]` are visible or clearly handled.
- Claims are safe.
- Critical market, regulatory, segment, offer, and channel inputs are supplied or not required for the reviewed material.
- Any remaining issues are minor and clearly non-blocking.

### Needs Revision

Use when:

- Campaign material may be launchable after copy, offer, targeting, `[T&CS]`, channel, localisation, or clarity fixes.
- Risks are fixable without full redesign.
- Missing details are important but not necessarily blocking if supplied before launch.
- Wording needs safer alternatives.
- Offer constraints need tightening.
- The skill can provide clear required fixes.

### Requires Specialist Review

Use when:

- Runtime regulatory interpretation is needed.
- VIP approval is needed.
- Responsible-gaming team input is needed.
- Legal sign-off is needed.
- Trading, risk, AML, fraud, BI, product, or market-owner approval is needed.
- Account status or customer eligibility rules may apply.
- Campaign material may be acceptable but cannot be cleared by this skill alone.

### Do Not Launch

Use when:

- Self-excluded users are targeted.
- Users with active responsible-gaming restrictions are targeted.
- Users with cooling-off restrictions are targeted.
- Copy encourages chasing losses.
- Offer logic is based on recent heavy losses.
- Copy claims guaranteed profit or guaranteed winning.
- `[T&CS]` materially mislead or omit key restrictions.
- Campaign uses prohibited or clearly unsafe targeting.
- Critical compliance blockers are present.
- The campaign cannot be made safe without redesign.

## Risk Categories

Review the campaign across the following categories.

### Responsible-Gaming Risk

Check for:

- Self-exclusion suppression.
- Responsible-gaming-risk suppression.
- Cooling-off suppression.
- Recently heavy-losing users.
- Loss-chasing language.
- Financial pressure language.
- Emotional manipulation.
- Excessive urgency.
- Excessive bet frequency encouragement.
- Excessive accumulator encouragement.
- Risky reactivation logic.
- VIP over-incentivisation.
- Invasive personalisation.

### Compliance Risk

Check for:

- Missing `[REGULATORY_NOTES]`.
- Missing `[COMMUNICATION_OPT_IN_STATUS]`.
- Missing `[OPT_OUT_TEXT]` where required.
- Missing `[T&CS]` or `[T&CS_LINK]`.
- Misleading claims.
- Unapproved "risk-free" wording.
- Unapproved "free money" wording.
- Guaranteed-win claims.
- Unclear eligibility.
- Unclear `[EXPIRY]`.
- Unclear bonus terms.
- Age, verification, or account eligibility uncertainty.
- Runtime approval uncertainty.

### Segment Targeting Risk

Check for:

- Broad targeting without suppressions.
- Dormant users targeted too aggressively.
- Recently heavy-losing users.
- Bonus abusers.
- Sharp or arb-sensitive users.
- VIPs without manual review.
- Users without `[COMMUNICATION_OPT_IN_STATUS]` for `[TARGET_CHANNEL]`.
- Users with account restrictions.
- Sensitive or inappropriate targeting attributes.

### Offer Mechanic Risk

Check for:

- Open-ended exposure.
- Missing `[MAX_BONUS_VALUE]`.
- Missing `[MINIMUM_ODDS]`.
- Missing `[MINIMUM_STAKE]`.
- Unclear `[ELIGIBLE_MARKETS]`.
- Unclear `[EXPIRY]`.
- Complex qualification.
- Cashback framed as loss recovery.
- Accumulator mechanics encouraging excessive leg counts.
- Deposit bonus framed as a financial solution.
- Bet builder or odds boost overclaiming value.
- VIP offer without exposure control.

### Copy and Claims Risk

Check for:

- "Guaranteed".
- "Risk-free".
- "Free money".
- "Win back".
- "Recover losses".
- "You need this".
- "Last chance" or excessive urgency.
- Overpromising.
- Misleading simplicity.
- Hidden restrictions.
- Invasive personalisation.
- Overly emotional reactivation language.
- Jargon-heavy wording.

### T&C Risk

Check for:

- Missing `[T&CS_LINK]`.
- Missing key restrictions.
- Unclear qualification.
- Unclear reward type.
- Unclear bonus vs cash distinction.
- Unclear `[EXPIRY]`.
- Unclear `[ELIGIBLE_MARKETS]`.
- Unclear usage limits.
- Important restrictions only hidden in long `[T&CS]`.
- `[T&CS]` too complex for `[TARGET_CHANNEL]`.

### Channel Risk

Check for:

- SMS too long or complex.
- Missing opt-in.
- Missing `[OPT_OUT_TEXT]` where required.
- Push urgency too aggressive.
- Email subject line overclaiming.
- VIP SMS too impersonal.
- Journey frequency too high.
- Reminder logic too pressuring.
- Character count or encoding issues.

### Localisation Risk

Check for:

- Changed offer meaning.
- Ambiguous translation.
- Unapproved local terms.
- Unsupported slang.
- Idioms that may mislead.
- Risky urgency after translation.
- Misleading translation of "free", "bonus", "cashback", "refund", or "boost".
- Native-speaker QA needed.

### Commercial Risk

Check for:

- Bonus abuse.
- Arbitrage exposure.
- Sharp-player exploitation.
- Margin impact.
- Over-incentivising natural activity.
- Low incrementality.
- Uncapped reward.
- VIP over-costing.
- Operational failure.
- Product or market unavailability.
- Support burden from unclear rules.

### Operational Risk

Check for:

- Audience build not defined.
- Suppressions not applied.
- Offer configuration unclear.
- Promo code or token setup missing.
- `[T&CS]` page missing.
- Tracking missing.
- Control group missing.
- QA missing.
- `[EXPIRY]` handling missing.
- Reporting missing.
- Owner dependencies unclear.

## Review by Campaign Objective

### Activation

Check:

- First action is clear.
- Offer is simple.
- No excessive pressure.
- Eligibility is clear.
- Verification and account restrictions are handled where relevant.
- New users are not misled.

### Retention

Check:

- Incrementality is plausible.
- Highly active users are not over-incentivised.
- `[OFFER_VALUE]` is controlled.
- Campaign does not create fatigue.
- Frequency caps are respected.

### Reactivation

Check:

- No emotional pressure.
- No loss-recovery framing.
- No targeting based on recent heavy losses.
- Dormancy threshold is defined if used.
- Responsible-gaming suppressions are strong.
- Message is calm and neutral.

### Event Activation

Check:

- Event facts are confirmed.
- Event is relevant to `[TARGET_SEGMENT]`.
- Betting is not framed as necessary to enjoy `[TARGET_EVENT]`.
- Timing does not create pressure.
- Offer is simple enough for `[TARGET_CHANNEL]`.

### Cross-Sell Within Sportsbook

Check:

- Product trial is safe and clear.
- Mechanic is not too complex.
- No high-risk product nudging.
- Segment fit is justified.
- Customer action is easy to understand.

### VIP Engagement

Check:

- Manual review is required.
- Safe engagement profile is confirmed.
- Offer exposure is capped.
- Tone is personal but not invasive.
- Responsible-gaming and compliance review is explicit.

## Review by Offer Mechanic

### Free Bet

Check:

- Free bet value is clear.
- Stake-return rules are not misleading where relevant.
- `[EXPIRY]` is clear.
- `[ELIGIBLE_MARKETS]` are clear.
- `[MAX_BONUS_VALUE]` is capped.

### Bet-and-Get

Check:

- Qualifying action is clear.
- Reward is clear.
- Time window is clear.
- SMS does not overload conditions.
- Customer effort is proportionate to `[OFFER_VALUE]`.

### Odds Boost

Check:

- Does not imply guaranteed profit.
- Eligible market or selection is clear.
- Max stake or cap is clear if relevant.
- Trading or risk approval is considered where needed.
- Boost value does not create uncontrolled exposure.

### Accumulator Insurance

Check:

- Refund conditions are clear.
- Minimum legs and minimum odds are clear where material.
- Does not encourage excessive leg counts without controls.
- Refund type and cap are clear.
- Settlement rules are not hidden.

### Cashback

Check:

- Does not frame cashback as recovering losses.
- Calculation basis is clear.
- Cap is clear.
- Time window is clear.
- Reward type is clear.

### Bet Builder Boost

Check:

- Product availability is confirmed.
- Eligible events or markets are clear.
- Boost does not imply better chance of winning.
- Combinability and settlement complexity are not hidden.

### Deposit Bonus

Check:

- Does not frame deposit as a financial solution.
- Deposit minimum is clear.
- Max bonus is clear.
- Wagering or eligibility is clear where relevant.
- Responsible-gaming sensitivity is considered.

### Reload Offer

Check:

- Does not create excessive deposit pressure.
- Incrementality is justified.
- Frequency caps are considered.
- Bonus abuse risk is reviewed.
- Deposit behaviour is not used in a pressuring way.

### Mission or Challenge

Check:

- Does not encourage excessive play.
- Steps are clear.
- Reward is capped.
- Time pressure is not excessive.
- Progress mechanics are not manipulative.

### Loyalty Points

Check:

- Point value is clear if relevant.
- Redemption rules are not misleading.
- `[EXPIRY]` is clear if relevant.
- Customer value is not overstated.

### VIP Bespoke Offer

Check:

- Manual review is required.
- Exposure is capped.
- `[RG_RISK_STATUS]` is checked.
- Personalisation is safe.
- Offer value is justified by confirmed customer value and policy.

### Event-Specific Voucher

Check:

- `[TARGET_EVENT]` is confirmed.
- Timing is clear.
- `[ELIGIBLE_MARKETS]` are clear.
- `[EXPIRY]` is clear.
- Product availability is confirmed.

### Personalised Stake-Back Offer

Check:

- Does not use unapproved "risk-free" wording.
- Stake-back cap is clear.
- Refund type is clear.
- Responsible-gaming sensitivity is reviewed.
- It is not framed as protection from losing.

## Market-Agnostic Design Rules

The skill must never assume:

- Local laws.
- Local approval requirements.
- Local language.
- Local legal wording.
- Local opt-in rules.
- Local `[T&CS]` rules.
- Local responsible-gaming requirements.
- Local sport preferences.
- Local betting habits.
- Local cultural tone.
- Local payment methods.
- Local competitor behaviour.
- Local operator conventions.

All market-specific and compliance-specific details must come from:

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

Do not present assumptions as facts. Do not invent market facts.

## Channel-Aware Review Rules

### SMS

Check:

- Message is short enough.
- Offer is clear.
- `[CTA]` is clear.
- `[T&CS]` are linked or clearly referenced.
- Opt-in is confirmed or flagged.
- `[OPT_OUT_TEXT]` is included if required.
- No aggressive urgency.
- No complex mechanics.
- Character count and token expansion risks are flagged where relevant.

### Email

Check:

- Subject line is not misleading.
- Header does not overclaim.
- Body explains conditions clearly.
- `[T&CS]` are visible.
- Email detail does not contradict SMS or campaign brief.
- Detailed email execution should be handled by a future email-specific skill.

### Push

Check:

- No excessive urgency.
- No misleading value claim.
- Very short copy still preserves key truth.
- Detailed push execution should be handled by a future push-specific skill.

### Onsite / Inbox

Check:

- Supporting explanation is available.
- Offer details are clear.
- Customer does not need to infer key restrictions.
- Onsite or inbox messaging aligns with the campaign brief.

### VIP Outreach

Check:

- Manual review.
- Tone safety.
- Exposure cap.
- Safe personalisation.
- No pressure based on spend, losses, or status.

## Responsible-Gaming Guardrails

The skill must reject or require revision for material that:

- Encourages chasing losses.
- Refers to recent losses.
- Suggests betting solves money problems.
- Uses emotional pressure.
- Uses shame or guilt.
- Implies the customer needs to return.
- Makes betting sound necessary.
- Overemphasises urgency.
- Encourages excessive bet frequency.
- Encourages excessive accumulator complexity.
- Targets vulnerable or restricted users.
- Uses behavioural profiling in a creepy or unsafe way.

The skill must also verify or flag:

- `[SELF_EXCLUSION_STATUS]`.
- `[RG_RISK_STATUS]`.
- Cooling-off handling.
- `[SUPPRESSION_RULES]`.
- Recently heavy-losing-user handling.
- Post-campaign responsible-gaming monitoring.

## Compliance Guardrails

The skill must flag:

- Missing `[REGULATORY_NOTES]`.
- Missing `[T&CS]`.
- Missing `[COMMUNICATION_OPT_IN_STATUS]`.
- Missing `[OPT_OUT_TEXT]` where required.
- Missing age, verification, or account eligibility notes where relevant.
- Misleading bonus wording.
- Misleading cashback or refund wording.
- Misleading free bet wording.
- Misleading odds boost wording.
- Unapproved claims.
- Unsupported guarantees.
- Unclear restrictions.
- Unclear eligibility.
- Unclear `[EXPIRY]`.

## Commercial Guardrails

The skill must flag:

- Open-ended bonus cost.
- Missing caps.
- Missing `[MINIMUM_ODDS]`.
- Missing `[MINIMUM_STAKE]`.
- High abuse risk.
- Sharp or arb exposure.
- VIP over-costing.
- Low incrementality.
- Product unavailability.
- In-play operational risk.
- Settlement complexity.
- Support burden.
- Overly broad eligibility.
- Campaign fatigue.

## Brand & UX Guardrails

The skill must flag:

- Spammy tone.
- Misleading simplicity.
- Jargon-heavy copy.
- Confusing offer structure.
- Hidden conditions.
- Unclear `[CTA]`.
- Over-personalisation.
- Stereotyping of `[TARGET_MARKET]`.
- Tone inconsistent with `[BRAND_TONE]`.
- Copy that sounds too aggressive for `[CAMPAIGN_OBJECTIVE]`.
- Copy that implies certainty of winning.

## Safer Rewrite Rules

When risky copy is detected, provide safer alternatives.

Rewrite principles:

- Remove pressure.
- Remove loss references.
- Remove guarantee claims.
- Remove "risk-free" unless approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Clarify `[OFFER_VALUE]`.
- Clarify key conditions.
- Keep `[CTA]` simple.
- Keep tone neutral.
- Preserve commercial intent.
- Preserve `[T&CS]` visibility.
- Do not add unsupported facts.

Provide rewrites only for the risky parts unless the full copy needs rewriting.

## Assumption Labels

Use these labels consistently:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked before launch.
- `[RISK]` - Compliance, responsible-gaming, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

Use this response format when the skill is activated:

# RG & Compliance Review Output

## 1. Review Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Material reviewed: `[CAMPAIGN_MATERIAL]`

## 2. Review Verdict

Use one:

- Pass.
- Needs Revision.
- Requires Specialist Review.
- Do Not Launch.

Include:

- Overall risk level: Low / Medium / High / Critical.
- Short reason for verdict.

## 3. Confirmed Inputs

List all confirmed user-provided facts and relevant prior skill outputs.

## 4. Working Assumptions

List assumptions clearly.

## 5. Needs Confirmation

List missing or uncertain compliance, responsible-gaming, `[T&CS]`, suppression, market, language, offer, or channel details.

## 6. Responsible-Gaming Review

Assess:

- Self-exclusion handling:
- Responsible-gaming-risk suppression:
- Cooling-off suppression:
- Heavy-loss targeting risk:
- Loss-chasing language:
- Financial pressure language:
- Urgency pressure:
- Reactivation sensitivity:
- Personalisation risk:
- Verdict:

## 7. Compliance Review

Assess:

- `[REGULATORY_NOTES]`:
- Opt-in status:
- `[OPT_OUT_TEXT]`:
- `[T&CS]` visibility:
- Eligibility clarity:
- Bonus terms clarity:
- `[EXPIRY]` clarity:
- `[APPROVED_TERMS]` / `[FORBIDDEN_TERMS]`:
- Required approvals:
- Verdict:

## 8. Segment & Suppression Review

Assess:

- `[TARGET_SEGMENT]` suitability:
- Required exclusions:
- Channel eligibility:
- VIP/manual review need:
- Bonus abuse restrictions:
- Sharp/arb restrictions:
- Account, AML, or fraud restrictions:
- Verdict:

## 9. Offer Mechanic Review

Assess:

- `[OFFER_MECHANIC]` suitability:
- Qualification clarity:
- Reward clarity:
- `[MINIMUM_STAKE]`:
- `[MINIMUM_ODDS]`:
- `[MAX_BONUS_VALUE]`:
- `[ELIGIBLE_MARKETS]`:
- `[EXPIRY]`:
- Abuse risk:
- Margin risk:
- Verdict:

## 10. Copy & Claims Review

Assess:

- Misleading claims:
- Guaranteed-win language:
- Risk-free/free-money wording:
- Pressure wording:
- Loss-recovery wording:
- `[CTA]` clarity:
- Tone safety:
- Verdict:

## 11. T&C Review

Assess:

- `[T&CS_LINK]` or `[T&CS]` cue:
- Key restrictions:
- Bonus vs cash clarity:
- Usage limits:
- `[EXPIRY]`:
- `[ELIGIBLE_MARKETS]`:
- Customer understanding:
- Verdict:

## 12. Channel Review

Assess:

- SMS/email/push/inbox/VIP suitability:
- Character count or length risks:
- Frequency cap risks:
- Reminder pressure:
- Opt-out risk:
- Verdict:

## 13. Localisation Review

Assess:

- Meaning preservation:
- Translation ambiguity:
- Local terms uncertainty:
- Native-speaker QA need:
- Compliance wording risk:
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
- Verdict:

## 15. Operational Readiness Review

Assess:

- Audience build:
- Suppression implementation:
- Offer setup:
- `[T&CS]` page:
- Tracking:
- Control group:
- QA:
- Reporting:
- Owner dependencies:
- Verdict:

## 16. Required Fixes

List exact required changes before launch.

For each:

- Issue:
- Risk type:
- Required fix:
- Owner:
- Blocking status: Blocking / Non-blocking.

## 17. Safer Rewrites

If copy has risks, provide safer alternatives.

For each:

- Risky wording:
- Risk:
- Safer rewrite:
- Why safer:

## 18. Required Approvals

List approvals needed:

- Compliance:
- Legal:
- Responsible gaming:
- Risk/trading:
- BI:
- Product:
- VIP manager:
- Market owner:

Use `[NEEDS CONFIRMATION]` where unclear.

## 19. Final Recommendation

Use one:

- Approved for next step.
- Revise and resubmit.
- Send to specialist review.
- Do not launch.

Explain why.

## 20. Recommended Next Skills

Recommend next skill chain.

Examples:

- `crm-sportsbook-sms-copy`, if copy needs rewriting.
- `crm-sportsbook-localisation`, if language needs review.
- `crm-sportsbook-offer-mechanics`, if mechanic needs redesign.
- `crm-sportsbook-player-segmentation`, if audience needs revision.
- `crm-sportsbook-journey-builder`, if campaign can proceed to journey design.
- `crm-sportsbook-ab-testing`, if launch-ready and testing is needed.
- `crm-sportsbook-post-campaign-analysis`, after campaign ends.

## Example User Request

Use a market-neutral example with placeholders only.

Example:

"Review this sportsbook SMS campaign for responsible-gaming and compliance risk. Target market is `[TARGET_MARKET]`, channel is `[TARGET_CHANNEL]`, segment is `[TARGET_SEGMENT]`, offer is `[OFFER_VALUE]` via `[OFFER_MECHANIC]`, and material is `[CAMPAIGN_MATERIAL]`. `[T&CS]` link: `[T&CS_LINK]`."

## Example Output

Use placeholders only. Do not include a real country, region, language, league, tournament, team, operator, payment method, regulation, regulator, slang, or cultural reference.

# RG & Compliance Review Output

## 1. Review Context

- Target market: `[TARGET_MARKET]`
- Target language: `[TARGET_LANGUAGE]`
- Target channel: `[TARGET_CHANNEL]`
- Campaign objective: `[CAMPAIGN_OBJECTIVE]`
- Target segment: `[TARGET_SEGMENT]`
- Sport/event: `[TARGET_SPORT]` / `[TARGET_EVENT]`
- Offer mechanic: `[OFFER_MECHANIC]`
- Material reviewed: `[CAMPAIGN_MATERIAL]`

## 2. Review Verdict

- Verdict: Needs Revision.
- Overall risk level: Medium.
- Short reason for verdict: `[T&CS_LINK]`, `[COMMUNICATION_OPT_IN_STATUS]`, and `[REGULATORY_NOTES]` need confirmation before launch. The reviewed material also needs a safer wording check for urgency and offer clarity.

## 3. Confirmed Inputs

- `[CONFIRMED]` `[TARGET_MARKET]` was supplied at runtime.
- `[CONFIRMED]` `[TARGET_CHANNEL]` is SMS.
- `[CONFIRMED]` `[TARGET_SEGMENT]` was supplied at runtime.
- `[CONFIRMED]` `[OFFER_MECHANIC]` and `[OFFER_VALUE]` were supplied at runtime.

## 4. Working Assumptions

- `[ASSUMPTION]` Shared baseline suppression rules apply because detailed `[SUPPRESSION_RULES]` were not supplied.

## 5. Needs Confirmation

- `[NEEDS CONFIRMATION]` `[REGULATORY_NOTES]`.
- `[NEEDS CONFIRMATION]` `[COMMUNICATION_OPT_IN_STATUS]`.
- `[NEEDS CONFIRMATION]` `[SELF_EXCLUSION_STATUS]` handling.
- `[NEEDS CONFIRMATION]` `[RG_RISK_STATUS]` handling.
- `[NEEDS CONFIRMATION]` `[T&CS_LINK]`.
- `[NEEDS CONFIRMATION]` `[OPT_OUT_TEXT]` if required for `[TARGET_CHANNEL]`.

## 6. Responsible-Gaming Review

- Self-exclusion handling: `[RISK]` Not confirmed.
- Responsible-gaming-risk suppression: `[RISK]` Not confirmed.
- Cooling-off suppression: `[NEEDS CONFIRMATION]`.
- Heavy-loss targeting risk: `[NEEDS CONFIRMATION]`.
- Loss-chasing language: No explicit loss-chasing wording detected in `[CAMPAIGN_MATERIAL]`.
- Financial pressure language: No explicit financial-solution wording detected in `[CAMPAIGN_MATERIAL]`.
- Urgency pressure: `[RISK]` Check whether timing language creates pressure.
- Reactivation sensitivity: `[NEEDS CONFIRMATION]` if `[CAMPAIGN_OBJECTIVE]` is reactivation.
- Personalisation risk: `[NEEDS CONFIRMATION]` if personalisation tokens or behavioural targeting are used.
- Verdict: Needs Revision.

## 7. Compliance Review

- `[REGULATORY_NOTES]`: `[NEEDS CONFIRMATION]`.
- Opt-in status: `[RISK]` `[COMMUNICATION_OPT_IN_STATUS]` not confirmed.
- `[OPT_OUT_TEXT]`: `[NEEDS CONFIRMATION]`.
- `[T&CS]` visibility: `[RISK]` `[T&CS_LINK]` not confirmed.
- Eligibility clarity: `[NEEDS CONFIRMATION]`.
- Bonus terms clarity: `[NEEDS CONFIRMATION]`.
- `[EXPIRY]` clarity: `[NEEDS CONFIRMATION]`.
- `[APPROVED_TERMS]` / `[FORBIDDEN_TERMS]`: `[NEEDS CONFIRMATION]`.
- Required approvals: `[NEEDS CONFIRMATION]`.
- Verdict: Requires Specialist Review if these items remain unresolved.

## 8. Segment & Suppression Review

- `[TARGET_SEGMENT]` suitability: Usable only after suppression checks.
- Required exclusions: self-excluded users, responsible-gaming-risk users, cooling-off users, channel opt-outs, restricted accounts, bonus abuse restrictions where relevant, and recently heavy-losing users where relevant.
- Channel eligibility: `[RISK]` opt-in not confirmed.
- VIP/manual review need: `[NEEDS CONFIRMATION]` based on `[VIP_STATUS]`.
- Bonus abuse restrictions: `[NEEDS CONFIRMATION]`.
- Sharp/arb restrictions: `[NEEDS CONFIRMATION]`.
- Account, AML, or fraud restrictions: `[NEEDS CONFIRMATION]`.
- Verdict: Needs Revision.

## 9. Offer Mechanic Review

- `[OFFER_MECHANIC]` suitability: Usable with constraints if it fits `[TARGET_SEGMENT]` and `[TARGET_CHANNEL]`.
- Qualification clarity: `[NEEDS CONFIRMATION]`.
- Reward clarity: `[CONFIRMED]` `[OFFER_VALUE]` supplied, but terms need validation.
- `[MINIMUM_STAKE]`: `[NEEDS CONFIRMATION]` if relevant.
- `[MINIMUM_ODDS]`: `[NEEDS CONFIRMATION]` if relevant.
- `[MAX_BONUS_VALUE]`: `[NEEDS CONFIRMATION]`.
- `[ELIGIBLE_MARKETS]`: `[NEEDS CONFIRMATION]`.
- `[EXPIRY]`: `[NEEDS CONFIRMATION]`.
- Abuse risk: `[NEEDS CONFIRMATION]`.
- Margin risk: `[NEEDS CONFIRMATION]`.
- Verdict: Needs Revision.

## 10. Copy & Claims Review

- Misleading claims: Check `[CAMPAIGN_MATERIAL]` against `[APPROVED_TERMS]` and `[FORBIDDEN_TERMS]`.
- Guaranteed-win language: Must be removed if present.
- Risk-free/free-money wording: Must be removed unless explicitly approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Pressure wording: Soften any aggressive urgency.
- Loss-recovery wording: Must be removed if present.
- `[CTA]` clarity: `[NEEDS CONFIRMATION]`.
- Tone safety: Use calm, clear wording aligned to `[BRAND_TONE]`.
- Verdict: Needs Revision if any risky claims are present.

## 11. T&C Review

- `[T&CS_LINK]` or `[T&CS]` cue: `[NEEDS CONFIRMATION]`.
- Key restrictions: `[NEEDS CONFIRMATION]`.
- Bonus vs cash clarity: `[NEEDS CONFIRMATION]`.
- Usage limits: `[NEEDS CONFIRMATION]`.
- `[EXPIRY]`: `[NEEDS CONFIRMATION]`.
- `[ELIGIBLE_MARKETS]`: `[NEEDS CONFIRMATION]`.
- Customer understanding: Not launch-ready until key restrictions are visible or linked.
- Verdict: Needs Revision.

## 12. Channel Review

- SMS/email/push/inbox/VIP suitability: `[TARGET_CHANNEL]` requires channel-specific checks.
- Character count or length risks: `[NEEDS CONFIRMATION]` for SMS material.
- Frequency cap risks: `[NEEDS CONFIRMATION]`.
- Reminder pressure: `[NEEDS CONFIRMATION]` if `[JOURNEY_STEPS]` include reminders.
- Opt-out risk: `[NEEDS CONFIRMATION]`.
- Verdict: Needs Revision.

## 13. Localisation Review

- Meaning preservation: `[NEEDS CONFIRMATION]` if `[TARGET_LANGUAGE]` output was changed.
- Translation ambiguity: `[NEEDS CONFIRMATION]`.
- Local terms uncertainty: `[NEEDS CONFIRMATION]`.
- Native-speaker QA need: `[RECOMMENDATION]` Use native-language QA if `[TARGET_LANGUAGE]` copy is produced.
- Compliance wording risk: `[NEEDS CONFIRMATION]`.
- Verdict: Requires Specialist Review if translation changes offer meaning.

## 14. Commercial Risk Review

- Bonus cost risk: `[NEEDS CONFIRMATION]`.
- Open exposure: `[RISK]` if `[MAX_BONUS_VALUE]` is missing.
- Bonus abuse risk: `[NEEDS CONFIRMATION]`.
- Sharp/arb risk: `[NEEDS CONFIRMATION]`.
- Low incrementality: `[NEEDS CONFIRMATION]`.
- VIP cost: `[NEEDS CONFIRMATION]`.
- Operational risk: `[NEEDS CONFIRMATION]`.
- Support burden: `[RISK]` if qualification or reward rules remain unclear.
- Verdict: Needs Revision.

## 15. Operational Readiness Review

- Audience build: `[NEEDS CONFIRMATION]`.
- Suppression implementation: `[RISK]` not confirmed.
- Offer setup: `[NEEDS CONFIRMATION]`.
- `[T&CS]` page: `[NEEDS CONFIRMATION]`.
- Tracking: `[NEEDS CONFIRMATION]`.
- Control group: `[RECOMMENDATION]` Include if measuring incrementality.
- QA: `[NEEDS CONFIRMATION]`.
- Reporting: `[NEEDS CONFIRMATION]`.
- Owner dependencies: `[NEEDS CONFIRMATION]`.
- Verdict: Needs Revision.

## 16. Required Fixes

- Issue: Suppression handling not confirmed.
  Risk type: Responsible-gaming and compliance.
  Required fix: Confirm `[SELF_EXCLUSION_STATUS]`, `[RG_RISK_STATUS]`, cooling-off handling, and `[SUPPRESSION_RULES]`.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.
- Issue: `[T&CS_LINK]` not confirmed.
  Risk type: Compliance and UX.
  Required fix: Add visible `[T&CS_LINK]` or approved short `[T&CS]` cue.
  Owner: `[NEEDS CONFIRMATION]`.
  Blocking status: Blocking.

## 17. Safer Rewrites

- Risky wording: "risk-free" if present in `[CAMPAIGN_MATERIAL]`.
  Risk: May mislead unless explicitly approved.
  Safer rewrite: "See `[T&CS_LINK]` for offer details."
  Why safer: It avoids implying no risk and directs the customer to conditions.

## 18. Required Approvals

- Compliance: `[NEEDS CONFIRMATION]`.
- Legal: `[NEEDS CONFIRMATION]`.
- Responsible gaming: `[NEEDS CONFIRMATION]`.
- Risk/trading: `[NEEDS CONFIRMATION]`.
- BI: `[NEEDS CONFIRMATION]`.
- Product: `[NEEDS CONFIRMATION]`.
- VIP manager: `[NEEDS CONFIRMATION]` if `[VIP_STATUS]` applies.
- Market owner: `[NEEDS CONFIRMATION]`.

## 19. Final Recommendation

- Revise and resubmit.

The material is not ready to launch because suppression handling, opt-in status, `[REGULATORY_NOTES]`, `[T&CS_LINK]`, and offer constraints need confirmation.

## 20. Recommended Next Skills

- `crm-sportsbook-offer-mechanics`, if offer constraints need redesign.
- `crm-sportsbook-sms-copy`, if SMS wording needs safer rewriting.
- `crm-sportsbook-localisation`, if `[TARGET_LANGUAGE]` wording needs review.
- `crm-sportsbook-player-segmentation`, if `[TARGET_SEGMENT]` or suppressions need revision.
- `crm-sportsbook-journey-builder`, only after required fixes are resolved.
