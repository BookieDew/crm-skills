---
name: crm-sportsbook-post-campaign-analysis
description: Analyses supplied sportsbook CRM campaign results, variants, journeys, offers, segments, commercial outcomes, and responsible-gaming/compliance observations to produce market-agnostic learnings, recommendations, and feedback for future CRM skills without inventing performance data or causality.
---

# CRM Sportsbook Post-Campaign Analysis

## Purpose
This skill helps CRM teams evaluate completed sportsbook CRM campaigns and convert performance results into actionable learnings.

It helps CRM teams understand:
- What happened
- Whether the campaign met its objective
- Which segment performed best
- Which offer mechanic performed best
- Which copy or localisation performed best
- Which channel or journey step performed best
- Whether the campaign was commercially positive
- Whether the campaign created RG, compliance, UX, or brand risks
- Whether the test result is reliable
- What should be repeated, changed, stopped, or tested next

The skill supports:
- Single campaign analysis
- SMS campaign analysis
- Offer performance analysis
- Event-led campaign analysis
- Journey performance analysis
- A/B test analysis
- Segment performance analysis
- Reactivation campaign analysis
- Activation campaign analysis
- Retention campaign analysis
- VIP campaign analysis
- Responsible-gaming and compliance post-review
- Commercial ROI and NGR-oriented review

The skill analyses supplied campaign data. It must not invent campaign performance, uplift, causality, market facts, statistical significance, or regulatory conclusions unless the user provides data or explicitly asks for labelled assumptions.

## Role in the Skill Pack
This is the learning and optimisation skill in the CRM sportsbook skill pack.

It usually runs after:
- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`
- `crm-sportsbook-localisation`
- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`

It uses campaign performance data and prior skill outputs to produce learnings.

It feeds learnings back into:
- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`
- `crm-sportsbook-player-segmentation`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-campaign-brief`
- `crm-sportsbook-sms-copy`
- `crm-sportsbook-localisation`
- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-journey-builder`
- `crm-sportsbook-ab-testing`

It should not:
- Invent missing performance data
- Claim causality without a control group or valid test design
- Claim statistical significance without sufficient data
- Ignore bonus cost or NGR
- Treat turnover alone as success
- Ignore opt-outs, complaints, or RG flags
- Replace BI/statistics review for complex experiments
- Replace compliance or RG incident review
- Make final legal conclusions

It turns campaign results into structured CRM learning.

## Dependencies
Use this skill with:
- `crm-sportsbook-shared-principles` for baseline market-agnostic, responsible-gaming, commercial, and quality principles
- `crm-sportsbook-skill-router` to route follow-up work to the correct specialist skill
- `crm-sportsbook-market-context` for supplied market context and future market-context feedback
- `crm-sportsbook-event-opportunity` for supplied event rationale and future event-opportunity feedback
- `crm-sportsbook-player-segmentation` for supplied audience logic and future segmentation feedback
- `crm-sportsbook-offer-mechanics` for supplied offer design and future offer-mechanics feedback
- `crm-sportsbook-campaign-brief` for the original campaign objective, constraints, and launch plan
- `crm-sportsbook-sms-copy` for supplied message variants and future copy feedback
- `crm-sportsbook-localisation` for supplied language or tone outputs and future localisation feedback
- `crm-sportsbook-rg-compliance-review` for pre-launch risks and post-launch safety feedback
- `crm-sportsbook-journey-builder` for supplied journey logic and future journey feedback
- `crm-sportsbook-ab-testing` for supplied hypothesis, variants, control group, and test design

## When to Use
Use this skill when the CRM manager needs to:
- Analyse a completed campaign
- Analyse SMS campaign results
- Analyse a sportsbook offer campaign
- Analyse an event-led campaign
- Analyse a journey
- Analyse an A/B test
- Compare variants
- Compare segments
- Compare offer mechanics
- Compare message angles
- Evaluate campaign ROI
- Evaluate bonus cost and NGR impact
- Identify whether the campaign was incremental
- Review opt-outs, complaints, and RG flags
- Summarise campaign performance for management
- Create learnings for future CRM campaigns
- Decide whether to repeat, stop, scale, or retest a campaign
- Prepare a post-campaign report for CRM, product, BI, risk, trading, compliance, or management

## When Not to Use
Do not use this skill to:
- Create campaign strategy from scratch
- Create market context from scratch
- Write SMS copy from scratch
- Design offer mechanics from scratch
- Build journey logic from scratch
- Design an A/B test before launch
- Provide final legal approval
- Provide final RG incident review
- Invent missing results
- Claim incrementality without control group or suitable comparison
- Claim statistical significance without data
- Ignore responsible-gaming or commercial guardrails
- Make unsupported conclusions about a market or segment

Route those requests to the appropriate skills.

## Required Inputs

### Minimum required inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT]
- [OFFER_MECHANIC], if promotional
- [CAMPAIGN_RESULTS] or key performance data
- [PRIMARY_KPI] or campaign success metric
- Campaign brief output, if available

### Recommended inputs
- Campaign brief output
- SMS copy output
- Localisation output
- RG/compliance review output
- Journey builder output
- A/B testing output, if a test was run
- [TARGET_LANGUAGE]
- [TARGET_SPORT]
- [TARGET_EVENT]
- [OFFER_VALUE]
- [MINIMUM_STAKE]
- [MINIMUM_ODDS]
- [MAX_BONUS_VALUE]
- [EXPIRY]
- [ELIGIBLE_MARKETS]
- [CONTROL_GROUP]
- [CONTROL_GROUP_RESULTS]
- [VARIANT_RESULTS]
- [SECONDARY_KPIS]
- [GUARDRAIL_METRICS]
- [MEASUREMENT_WINDOW]
- [DECISION_RULE]
- [SEGMENT_SIZE]
- [SAMPLE_SIZE]
- [DELIVERY_RATE]
- [CLICK_RATE]
- [OPT_OUT_RATE]
- [DEPOSIT_CONVERSION]
- [BET_CONVERSION]
- [OFFER_UPTAKE]
- [BONUS_UPTAKE]
- [TURNOVER]
- [GGR]
- [NGR]
- [BONUS_COST]
- [INCREMENTAL_REVENUE]
- [RETENTION_UPLIFT]
- [CHURN_REDUCTION]
- [COMPLAINTS]
- [POST_CAMPAIGN_RG_FLAGS]

### Advanced optional inputs
- Audience eligibility count
- Audience reached
- Audience excluded
- Delivery count
- Failed delivery count
- Click count
- Offer view count
- Offer opt-in count
- Deposit count
- First deposit count
- Bet count
- Qualifying bet count
- Repeat bet count
- Active days
- Stake distribution
- Average stake
- Median stake
- Turnover by segment
- GGR by segment
- NGR by segment
- Bonus cost by segment
- Bonus cost per conversion
- Cost per activated user
- Net incremental value
- Margin by sport or market
- Product usage
- Event-specific turnover
- Event-specific NGR
- Bet builder usage
- Live betting usage
- Accumulator usage
- Cashback payout
- Free bet redemption
- Odds boost usage
- Bonus abuse flags
- Sharp/arb flags
- VIP performance
- Control group holdout data
- Variant assignment data
- Statistical test output
- Confidence interval
- P-value
- Minimum detectable effect
- Segment-level split
- Channel-level split
- Device-level split
- Language-level split
- Time-of-send split
- Journey-step funnel
- Exit reason data
- Complaint categories
- Customer support contacts
- Opt-out reasons
- RG interaction notes
- Self-exclusion after campaign
- Cooling-off after campaign
- Account restriction changes
- Anomalies or incidents
- Product availability issues
- Tracking issues
- Data quality notes
- BI dashboard link or export notes

## Output
The skill should produce:
- Post-campaign summary
- Confirmed inputs
- Working assumptions
- Items needing confirmation
- Data quality assessment
- Objective performance review
- KPI performance review
- Funnel analysis
- Segment analysis
- Variant or A/B test analysis, if applicable
- Offer performance analysis
- Channel performance analysis
- Journey performance analysis, if applicable
- Commercial performance review
- Incrementality assessment
- RG/compliance post-review
- UX/brand impact review
- Operational issues
- Key learnings
- Recommendations
- Next test ideas
- Skill-pack feedback loop
- Management summary

## Workflow
1. Identify [CAMPAIGN_OBJECTIVE].
2. Identify [TARGET_MARKET] as runtime context only.
3. Identify [TARGET_CHANNEL].
4. Review campaign brief output if available.
5. Review A/B testing output if available.
6. Review journey builder output if available.
7. Review RG/compliance review output if available.
8. Review SMS copy and localisation outputs if available.
9. Identify supplied performance data.
10. List all confirmed inputs.
11. Separate confirmed results from assumptions.
12. Mark missing analysis-critical data as [NEEDS CONFIRMATION].
13. Assess data quality.
14. Assess whether the campaign had a control group or valid comparison.
15. Review primary KPI performance.
16. Review secondary KPI performance.
17. Review guardrail metrics.
18. Analyse conversion funnel.
19. Analyse segment performance.
20. Analyse offer performance.
21. Analyse channel performance.
22. Analyse journey performance, if applicable.
23. Analyse A/B test or variant performance, if applicable.
24. Analyse commercial impact:
    - Turnover
    - GGR
    - NGR
    - Bonus cost
    - Incrementality
25. Analyse responsible-gaming and compliance observations:
    - Opt-outs
    - Complaints
    - RG flags
    - Self-exclusions
    - Cooling-off
26. Identify operational or tracking issues.
27. Separate observations from conclusions.
28. Avoid claiming causality unless supported.
29. Produce learnings.
30. Recommend actions:
    - Repeat
    - Scale
    - Revise
    - Retest
    - Stop
31. Recommend which skills should be updated or used next.

## Decision Logic
Apply these rules:

- If [CAMPAIGN_RESULTS] are missing, mark as [NEEDS CONFIRMATION].
- If [PRIMARY_KPI] is missing, infer a likely KPI from the campaign objective only as [ASSUMPTION].
- If no control group exists, do not claim incrementality. Use "directional performance" language.
- If no A/B test design exists, do not claim one variant caused better performance unless the comparison is valid.
- If sample size is small, mark conclusions as directional.
- If measurement window is too short, mark retention or long-term conclusions as [NEEDS CONFIRMATION].
- If tracking was broken or incomplete, mark affected conclusions as unreliable.
- If turnover increased but NGR decreased, flag commercial quality risk.
- If GGR increased but bonus cost increased more, flag profitability risk.
- If offer uptake increased but bet conversion did not, flag offer relevance or friction risk.
- If clicks increased but conversions did not, flag landing page, offer clarity, or eligibility friction.
- If opt-outs increased, flag channel fatigue or tone issue.
- If complaints increased, flag copy, T&C, eligibility, or support burden risk.
- If post-campaign RG flags increased, flag RG risk and recommend specialist review.
- If self-exclusions or cooling-off increased after campaign, flag serious RG review need.
- If bonus abuse flags increased, flag offer mechanic or segment risk.
- If sharp/arb exploitation increased, flag risk/trading review need.
- If VIP campaign performed well commercially but RG flags increased, do not recommend scaling without review.
- If a campaign performed well commercially but failed guardrail metrics, do not recommend broad rollout.
- If SMS delivery was poor, avoid judging copy performance solely on conversion.
- If click tracking is unavailable, use downstream metrics cautiously.
- If localisation variants differ in meaning, do not treat them as clean A/B variants.
- If event-led results are strong but event context was unique, warn against overgeneralising.
- If campaign objective was activation, evaluate activated quality, not just first action.
- If campaign objective was reactivation, evaluate repeat activity and RG guardrails, not just one-time return.
- If campaign objective was retention, evaluate incrementality and future activity, not just immediate turnover.
- If campaign objective was event activation, evaluate event-specific results and post-event retention.
- If campaign objective was cross-sell, evaluate repeat use of the target product.
- If campaign objective was VIP engagement, include manual feedback and risk review.

## Analysis Modes

### Campaign Summary Analysis
Use when the user needs a high-level review.

Include:
- Objective
- Result against objective
- Main KPI result
- Commercial result
- Guardrail result
- Final verdict
- Next recommendation

### SMS Campaign Analysis
Use when analysing SMS performance.

Review:
- Delivered messages
- Delivery rate
- Click rate, if available
- Offer views
- Conversion
- Opt-outs
- Complaints
- Character length or clarity issues
- CTA performance
- T&C friction
- Localisation impact
- Guardrails

### Offer Performance Analysis
Use when analysing a specific offer mechanic.

Review:
- Offer uptake
- Qualification rate
- Redemption rate
- Bonus cost
- NGR/GGR
- Abuse flags
- Segment fit
- Customer understanding
- Commercial sustainability

### Event-Led Campaign Analysis
Use when campaign was tied to [TARGET_EVENT], [TARGET_FIXTURE], or [TARGET_TOURNAMENT].

Review:
- Event timing
- Pre-event performance
- Event-day performance
- Post-event impact
- Product availability issues
- Segment-event fit
- Event uniqueness
- Whether learnings generalise

### Journey Analysis
Use when campaign had multiple steps.

Review:
- Entry count
- Step-level delivery
- Step-level engagement
- Step-level conversion
- Drop-off
- Exit reasons
- Reminder impact
- Frequency issues
- Conversion timing
- Guardrail metrics per step

### A/B Test Analysis
Use when variants were tested.

Review:
- Hypothesis
- Variant assignment
- Sample size
- Primary KPI
- Secondary KPIs
- Guardrails
- Control group
- Decision rule
- Winner, if justified
- Inconclusive result, if data is insufficient
- Rollout or retest recommendation

### Segment Analysis
Use when comparing audience performance.

Review:
- Segment size
- Conversion
- Offer uptake
- NGR
- Bonus cost
- Opt-out
- Complaints
- RG flags
- Abuse flags
- Future targeting recommendation

### Commercial Analysis
Use when evaluating financial performance.

Review:
- Turnover
- GGR
- NGR
- Bonus cost
- Bonus cost as share of value
- Incrementality
- Control group impact
- Margin quality
- Abuse risk
- Scalability

### Responsible-Gaming Post-Review
Use when evaluating safety impact.

Review:
- Opt-outs
- Complaints
- RG flags after campaign
- Self-exclusions after campaign
- Cooling-off after campaign
- High-loss patterns if supplied
- Risky segment behaviour
- Risky copy or journey pressure
- Recommendation for future suppression logic

## Campaign Objective-to-Analysis Logic

### Activation
Evaluate:
- First deposit conversion
- First bet conversion
- Offer uptake
- Cost per activated customer
- Quality of activation
- Second bet or repeat activity
- Bonus cost
- NGR
- RG/UX guardrails

Do not treat first action alone as sufficient success if downstream quality is poor.

### Retention
Evaluate:
- Repeat activity
- Active days
- Incremental turnover
- Incremental NGR
- Bonus cost
- Segment quality
- Control group difference if available
- Opt-outs and fatigue

Do not treat natural activity as campaign success without evidence.

### Reactivation
Evaluate:
- Reactivation rate
- Repeat activity after reactivation
- NGR after return
- Bonus cost
- Opt-outs
- Complaints
- RG flags
- Long-term retention if available

Do not recommend scaling if one-time return is high but guardrails worsen.

### Event Activation
Evaluate:
- Event-specific bet conversion
- Offer uptake
- Event turnover
- Event NGR
- Post-event activity
- Event timing impact
- Segment-event fit
- Whether results are repeatable

Avoid overgeneralising from one unusual event.

### Cross-Sell Within Sportsbook
Evaluate:
- First use of target product
- Repeat use of target product
- Incremental NGR
- Customer understanding
- Support issues
- Product-specific RG or UX concerns

### VIP Engagement
Evaluate:
- Qualitative feedback where available
- Offer uptake
- NGR
- Bonus cost
- Manual review outcome
- RG indicators
- Complaint or support issues
- Relationship impact

Do not recommend automated scaling of VIP mechanics without review.

## KPI Interpretation Rules

### Delivery Rate
Low delivery rate may indicate:
- Data quality issue
- Channel issue
- Invalid contact data
- Platform issue

Do not judge copy performance if delivery was poor.

### Click Rate
High click and low conversion may indicate:
- Offer friction
- T&C confusion
- Landing page issue
- Eligibility mismatch
- Weak offer relevance

Low click and high conversion may indicate:
- Strong direct app behaviour
- Tracking limitation
- Existing intent

### Offer Uptake
High uptake may indicate:
- Strong perceived value
- Easy mechanic
- Bonus sensitivity
- Possible abuse risk

Low uptake may indicate:
- Weak offer
- Poor communication
- Eligibility friction
- Low event relevance

### Bet Conversion
High bet conversion should be evaluated alongside:
- Bonus cost
- NGR
- Segment quality
- Guardrail metrics

### Turnover
Turnover alone is not enough.

Always compare with:
- GGR
- NGR
- Bonus cost
- Margin
- Incrementality
- RG guardrails

### GGR
GGR can look positive while NGR is weak after bonus cost.

Always compare with:
- Bonus cost
- NGR
- Control group if available

### NGR
NGR is stronger than turnover or GGR for commercial quality, but should still be evaluated with:
- Incrementality
- Bonus cost
- Long-term retention
- Guardrails

### Bonus Cost
High bonus cost may be acceptable only if:
- Incremental value is proven or plausible
- Segment quality is strong
- Guardrails are clean
- Abuse risk is controlled

### Opt-Out Rate
Elevated opt-out rate may indicate:
- Poor targeting
- Excessive frequency
- Overly aggressive tone
- Channel fatigue
- Weak offer relevance

### Complaints
Complaints may indicate:
- Misleading copy
- T&C confusion
- Eligibility friction
- Bonus settlement issues
- Localisation problems
- Support burden

### Post-Campaign RG Flags
Any increase should be treated seriously.

Do not recommend scaling without RG review if RG guardrails worsened.

## A/B Test Result Interpretation
Classify test outcomes as one of the following:

### Clear Winner
Use only when:
- Primary KPI improved
- Guardrails did not worsen materially
- Sample size and measurement are credible
- Decision rule was met

### Directional Winner
Use when:
- One variant appears better
- Data is limited
- Guardrails are acceptable
- More testing may be useful

### Inconclusive
Use when:
- Results are too close
- Sample size is weak
- Tracking is incomplete
- Measurement window is too short
- External factors may explain results

### Do Not Roll Out
Use when:
- Primary KPI improved but guardrails failed
- RG/compliance risks increased
- Bonus cost outweighed value
- Complaints or opt-outs increased materially
- Variant created customer misunderstanding
- Abuse or sharp exploitation increased

## Incrementality Rules
Be careful with incrementality.

- If a control group exists, compare campaign group against control group.
- If no control group exists, use directional language.
- If historical baseline is supplied, compare cautiously and flag limitations.
- If event timing is unique, avoid broad claims.
- If segment was highly active already, do not assume campaign caused activity.
- If offer uptake is high but control group also performed well, question incrementality.
- If NGR uplift is negative after bonus cost, do not recommend scaling purely on engagement.

## Responsible-Gaming Post-Review Rules
Flag:
- Increase in opt-outs
- Increase in complaints
- Increase in RG flags
- Increase in self-exclusions
- Increase in cooling-off
- Increase in high-loss patterns, if supplied
- Risky response from reactivation users
- Risky response from VIP users
- Risky response from deposit or reload campaign
- Risky response from frequent reminders
- Copy or journey patterns that may have created pressure

If RG guardrails worsened, recommend:
- Do not scale yet
- Review suppression rules
- Review copy tone
- Review journey frequency
- Review target segment
- Review offer mechanic
- Send to RG/compliance review

## Commercial Post-Review Rules
Flag:
- High bonus cost
- Negative NGR impact
- Poor incremental value
- High cost per conversion
- Offer abuse
- Sharp/arb exploitation
- VIP over-costing
- Low-quality activation
- One-time conversion without repeat activity
- High support burden
- High opt-out cost
- Low scalability

Recommend:
- Repeat only if commercially justified
- Scale only with guardrails
- Retest if learnings are unclear
- Stop if commercial or RG guardrails failed
- Redesign mechanic if cost is too high
- Narrow segment if broad targeting was inefficient

## Sportsbook-Specific Analysis Considerations
Consider, without inventing local facts:
- Sport or event relevance if supplied
- Fixture or tournament timing if supplied
- Offer expiry and redemption timing
- Pre-match versus live activity if supplied
- Single bet, accumulator, bet builder, or live betting behaviour if supplied
- Odds boost usage and exposure
- Free bet cost and redemption
- Cashback calculation and payout
- Accumulator insurance exposure
- Deposit or reload sensitivity
- VIP manual review outcome
- Bonus-sensitive response
- Sharp/arb indicators
- Bonus abuse indicators
- Trading or risk restrictions
- Margin quality
- GGR and NGR impact
- Control group integrity
- Campaign fatigue
- Post-campaign RG monitoring

## Market-Agnostic Design Rules
The skill must never assume:
- Local laws
- Local regulator requirements
- Local language
- Local channel rules
- Local opt-in rules
- Local sport preferences
- Local betting habits
- Local event schedules
- Local holidays
- Local payment methods
- Local cultural tone
- Local competitor behaviour
- Local operator conventions
- Local performance benchmarks
- Local statistical baselines

All analysis-specific and market-specific details must come from:
- User-provided inputs
- Existing skill outputs
- Internal documents
- Approved policies
- Confirmed research
- Runtime browsing or research tools, if available

If a detail is not confirmed, label it:
- [ASSUMPTION]
- [NEEDS CONFIRMATION]
- [RISK]
- [RECOMMENDATION]

Do not present assumptions as facts.

## Channel-Aware Analysis Rules

### SMS
For SMS analysis, review:
- Delivery rate
- Click rate if tracked
- Conversion
- Opt-out rate
- Complaints
- Character length
- CTA clarity
- T&C clarity
- Localisation issues
- Frequency impact
- Message timing
- Guardrails

### Email
For email analysis:
- Do not overvalue open rate
- Prioritise downstream conversion and commercial outcomes
- Review subject line complaints or misleading claims if supplied
- Detailed email execution belongs to a future email-specific skill

### Push
For push analysis:
- Review permission opt-outs
- Review urgency risk
- Review short-copy clarity
- Detailed push execution belongs to a future push-specific skill

### Onsite / Inbox
For onsite/inbox analysis:
- Review impressions
- Clicks
- Offer views
- Conversion
- Eligibility friction
- T&C understanding

### VIP Outreach
For VIP analysis:
- Include manual feedback if supplied
- Review relationship impact
- Review bonus cost
- Review RG indicators
- Avoid automatic rollout without review

## Responsible Gaming & Compliance Guardrails
The skill must follow shared responsible-gaming principles.

It must flag campaigns where supplied results indicate:
- Increased opt-outs, complaints, RG flags, self-exclusions, or cooling-off
- Targeting, suppression, or eligibility failures
- Incentives reaching users with RG risk or account restrictions
- Reactivation users responding in risky patterns
- Deposit or reload pressure concerns
- VIP over-incentivisation concerns
- Copy, localisation, or journey pressure issues
- T&C confusion or misleading offer understanding
- Compliance complaints or approval gaps

If safety guardrails worsened, do not recommend scale until `crm-sportsbook-rg-compliance-review` or specialist review has been completed.

## Commercial Guardrails
The skill must not treat volume as success on its own.

Always evaluate supplied commercial results alongside:
- Bonus cost
- NGR
- GGR
- Incrementality
- Control group or comparison quality
- Bonus abuse indicators
- Sharp/arb indicators
- Margin quality
- Repeat activity
- Support burden
- Opt-out and complaint cost

Do not estimate commercial impact unless data is provided or the user explicitly asks for assumptions.

## Brand & UX Guardrails
The skill should identify whether results suggest:
- Offer misunderstanding
- CTA confusion
- T&C friction
- Copy fatigue
- Overly aggressive tone
- Invasive personalisation
- Localisation friction
- Excessive message frequency
- High support burden
- A campaign experience that is not worth repeating even if short-term response was positive

## Skill-Pack Feedback Loop
Recommend updates to future skill usage.

Examples:
- If market assumptions were wrong, update future `crm-sportsbook-market-context` inputs.
- If event relevance was weak, update `crm-sportsbook-event-opportunity` criteria.
- If segment underperformed, revise `crm-sportsbook-player-segmentation`.
- If offer cost was too high, revise `crm-sportsbook-offer-mechanics`.
- If campaign brief missed operational risks, improve `crm-sportsbook-campaign-brief`.
- If SMS copy had low clarity or high opt-outs, revise `crm-sportsbook-sms-copy`.
- If localisation caused confusion, revise `crm-sportsbook-localisation`.
- If RG issues appeared, strengthen `crm-sportsbook-rg-compliance-review`.
- If reminders caused fatigue, revise `crm-sportsbook-journey-builder`.
- If test design was inconclusive, improve `crm-sportsbook-ab-testing`.

## Assumption Labels
Use these labels consistently:

[CONFIRMED] - Information explicitly provided by the user
[ASSUMPTION] - Reasonable but unconfirmed assumption
[NEEDS CONFIRMATION] - Important detail that should be checked before launch or before conclusion
[RISK] - Compliance, RG, commercial, UX, brand, data-quality, or operational risk
[RECOMMENDATION] - Proposed action

## Output Template
Use this response format when the skill is activated:

# Post-Campaign Analysis Output

## 1. Analysis Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Campaign period:
- Measurement window: [MEASUREMENT_WINDOW]
- Material analysed: [CAMPAIGN_RESULTS]

## 2. Executive Summary
Provide a short management-friendly summary.

Include:
- Overall performance:
- Commercial outcome:
- Guardrail outcome:
- Main learning:
- Final recommendation:

## 3. Confirmed Inputs
List all confirmed user-provided facts, campaign setup details, and supplied results.

## 4. Working Assumptions
List assumptions clearly.

## 5. Needs Confirmation
List missing or uncertain data, tracking, measurement, commercial, RG, or campaign setup items.

## 6. Data Quality Assessment
Assess:
- Completeness:
- Tracking reliability:
- Control group availability:
- Variant assignment reliability:
- Sample size: [SAMPLE_SIZE]
- Measurement window: [MEASUREMENT_WINDOW]
- Known anomalies:
- Confidence in conclusions:

Use one:
- Strong data basis
- Usable with limitations
- Directional only
- Insufficient for reliable conclusions

## 7. Objective Performance
Assess whether the campaign met [CAMPAIGN_OBJECTIVE].

Include:
- Objective:
- Primary KPI: [PRIMARY_KPI]
- Result:
- Target or benchmark, if supplied:
- Interpretation:
- Verdict:

## 8. Funnel Performance
Analyse available funnel steps.

Include relevant supplied metrics:
- Audience eligible:
- Audience contacted:
- Delivered:
- Clicked / viewed:
- Offer opted in:
- Deposited:
- Bet placed:
- Qualified:
- Bonus awarded:
- Bonus redeemed:
- Conversion completed:
- Drop-off points:
- Main friction points:

## 9. Segment Performance
Analyse performance by segment if data is supplied.

For each segment:
- Segment:
- Size:
- Conversion:
- Offer uptake:
- NGR/GGR:
- Bonus cost:
- Opt-out:
- Complaints:
- RG flags:
- Interpretation:
- Recommendation:

## 10. Offer Performance
Assess:
- Mechanic: [OFFER_MECHANIC]
- Offer uptake: [OFFER_UPTAKE]
- Qualification rate:
- Redemption rate:
- Bonus cost: [BONUS_COST]
- NGR/GGR: [NGR] / [GGR]
- Abuse flags:
- Customer understanding:
- Commercial sustainability:
- Recommendation:

## 11. Channel Performance
Assess:
- Channel: [TARGET_CHANNEL]
- Delivery: [DELIVERY_RATE]
- Engagement: [CLICK_RATE]
- Conversion:
- Opt-out: [OPT_OUT_RATE]
- Complaints: [COMPLAINTS]
- Timing:
- Frequency:
- CTA clarity:
- T&C clarity:
- Recommendation:

## 12. Journey Performance
If a journey was used, assess:
- Entry count:
- Step-level delivery:
- Step-level engagement:
- Step-level conversion:
- Reminder impact:
- Exit reasons:
- Frequency cap impact:
- Drop-off:
- Pressure/fatigue risk:
- Recommendation:

## 13. A/B Test or Variant Analysis
If variants were used, assess:
- Hypothesis: [TEST_HYPOTHESIS]
- Variant A result: [VARIANT_A]
- Variant B result: [VARIANT_B]
- Control group result: [CONTROL_GROUP_RESULTS]
- Primary KPI: [PRIMARY_KPI]
- Secondary KPIs: [SECONDARY_KPIS]
- Guardrail metrics: [GUARDRAIL_METRICS]
- Winner classification:
  - Clear winner
  - Directional winner
  - Inconclusive
  - Do not roll out
- Reason:
- Rollout/retest recommendation:

## 14. Commercial Review
Assess:
- Turnover: [TURNOVER]
- GGR: [GGR]
- NGR: [NGR]
- Bonus cost: [BONUS_COST]
- Incremental revenue: [INCREMENTAL_REVENUE]
- Cost per conversion:
- Margin quality:
- Low incrementality risk:
- Bonus abuse risk:
- Sharp/arb risk:
- VIP cost risk:
- Commercial verdict:

## 15. Responsible-Gaming & Compliance Post-Review
Assess:
- Opt-out rate: [OPT_OUT_RATE]
- Complaints: [COMPLAINTS]
- Post-campaign RG flags: [POST_CAMPAIGN_RG_FLAGS]
- Self-exclusion after campaign:
- Cooling-off after campaign:
- Heavy-loss indicators, if supplied:
- Risky segment behaviour:
- Copy or journey pressure concerns:
- T&C complaints:
- Required follow-up:
- RG/compliance verdict:

## 16. UX, Brand & Localisation Review
Assess:
- Copy clarity:
- CTA clarity:
- T&C clarity:
- Offer understanding:
- Localisation issues:
- Tone issues:
- Support burden:
- Customer confusion:
- Recommendation:

## 17. Operational Review
Assess:
- Audience build:
- Suppression execution:
- Offer setup:
- Tracking:
- Control group:
- QA:
- Reporting:
- Product availability:
- Market availability:
- Incident notes:
- Operational verdict:

## 18. Key Learnings
List 5-10 practical learnings.

Separate:
- Confirmed learnings
- Directional learnings
- Hypotheses for future testing

## 19. Recommendations
Provide clear actions.

Use categories:
- Repeat:
- Scale:
- Revise:
- Retest:
- Stop:
- Investigate:
- Send to RG/compliance review:

## 20. Next Campaign Ideas
Suggest future campaign directions using placeholders only.

For each:
- Idea:
- Why:
- Segment:
- Offer direction:
- Channel:
- Required checks:
- Suggested next skill:

## 21. Skill-Pack Feedback Loop
Recommend which skill outputs should be improved next.

For example:
- Market context:
- Event opportunity:
- Player segmentation:
- Offer mechanics:
- Campaign brief:
- SMS copy:
- Localisation:
- RG/compliance review:
- Journey builder:
- A/B testing:

## 22. Final Recommendation
Use one:
- Repeat with same setup
- Scale with guardrails
- Revise and retest
- Stop campaign type
- Needs deeper BI/statistical review
- Needs RG/compliance investigation
- Insufficient data to decide

Explain why.

## 23. Recommended Next Skills
Recommend next skill chain.

Examples:
- `crm-sportsbook-ab-testing`, if another test is needed
- `crm-sportsbook-offer-mechanics`, if offer cost or abuse risk was high
- `crm-sportsbook-player-segmentation`, if audience quality was poor
- `crm-sportsbook-sms-copy`, if copy clarity or opt-outs were an issue
- `crm-sportsbook-localisation`, if language or tone caused friction
- `crm-sportsbook-rg-compliance-review`, if RG/compliance guardrails worsened
- `crm-sportsbook-campaign-brief`, if the campaign should be redesigned

## Example User Request
Use a market-neutral example with placeholders only.

Example:
"Analyse this sportsbook CRM campaign. Target market was [TARGET_MARKET], channel was [TARGET_CHANNEL], objective was [CAMPAIGN_OBJECTIVE], segment was [TARGET_SEGMENT], offer was [OFFER_VALUE] via [OFFER_MECHANIC]. Results: [CAMPAIGN_RESULTS]. Control group: [CONTROL_GROUP_RESULTS]."

## Example Output
Use placeholders only. Do not include a real country, region, language, league, tournament, team, operator, payment method, regulation, regulator, slang, or cultural reference.

# Post-Campaign Analysis Output

## 1. Analysis Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Campaign period: [EVENT_DATE]
- Measurement window: [MEASUREMENT_WINDOW]
- Material analysed: [CAMPAIGN_RESULTS]

## 2. Executive Summary
- Overall performance: [CONFIRMED] Performance is based on [CAMPAIGN_RESULTS].
- Commercial outcome: [CONFIRMED] Review [TURNOVER], [GGR], [NGR], and [BONUS_COST] together before judging success.
- Guardrail outcome: [CONFIRMED] Review [OPT_OUT_RATE], [COMPLAINTS], and [POST_CAMPAIGN_RG_FLAGS].
- Main learning: [RECOMMENDATION] Treat the result as directional unless [CONTROL_GROUP_RESULTS], [SAMPLE_SIZE], and [MEASUREMENT_WINDOW] support stronger conclusions.
- Final recommendation: [RECOMMENDATION] Revise and retest if commercial or guardrail results are unclear.

## 3. Confirmed Inputs
- [CONFIRMED] [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] [TARGET_MARKET]
- [CONFIRMED] [TARGET_CHANNEL]
- [CONFIRMED] [TARGET_SEGMENT]
- [CONFIRMED] [OFFER_MECHANIC]
- [CONFIRMED] [CAMPAIGN_RESULTS]

## 4. Working Assumptions
- [ASSUMPTION] [PRIMARY_KPI] is the main success measure if no alternative KPI is supplied.

## 5. Needs Confirmation
- [NEEDS CONFIRMATION] [CONTROL_GROUP_RESULTS]
- [NEEDS CONFIRMATION] [VARIANT_RESULTS]
- [NEEDS CONFIRMATION] [GUARDRAIL_METRICS]
- [NEEDS CONFIRMATION] [MEASUREMENT_WINDOW]

## 6. Data Quality Assessment
- Completeness: Usable with limitations
- Tracking reliability: [NEEDS CONFIRMATION]
- Control group availability: [CONTROL_GROUP]
- Variant assignment reliability: [NEEDS CONFIRMATION]
- Sample size: [SAMPLE_SIZE]
- Measurement window: [MEASUREMENT_WINDOW]
- Known anomalies: [NEEDS CONFIRMATION]
- Confidence in conclusions: Directional only

## 7. Objective Performance
- Objective: [CAMPAIGN_OBJECTIVE]
- Primary KPI: [PRIMARY_KPI]
- Result: [CAMPAIGN_RESULTS]
- Target or benchmark, if supplied: [NEEDS CONFIRMATION]
- Interpretation: [RECOMMENDATION] Compare result quality with commercial and RG guardrails.
- Verdict: Directional only

## 8. Funnel Performance
- Audience eligible: [SEGMENT_SIZE]
- Delivered: [DELIVERY_RATE]
- Clicked / viewed: [CLICK_RATE]
- Deposited: [DEPOSIT_CONVERSION]
- Bet placed: [BET_CONVERSION]
- Offer opted in: [OFFER_UPTAKE]
- Bonus redeemed: [BONUS_UPTAKE]
- Main friction points: [NEEDS CONFIRMATION]

## 9. Segment Performance
- Segment: [TARGET_SEGMENT]
- Size: [SEGMENT_SIZE]
- Conversion: [BET_CONVERSION]
- Offer uptake: [OFFER_UPTAKE]
- NGR/GGR: [NGR] / [GGR]
- Bonus cost: [BONUS_COST]
- Opt-out: [OPT_OUT_RATE]
- Complaints: [COMPLAINTS]
- RG flags: [POST_CAMPAIGN_RG_FLAGS]
- Interpretation: [RECOMMENDATION] Continue only if conversion quality and guardrails are acceptable.
- Recommendation: [RECOMMENDATION] Feed results into `crm-sportsbook-player-segmentation`.

## 10. Offer Performance
- Mechanic: [OFFER_MECHANIC]
- Offer uptake: [OFFER_UPTAKE]
- Bonus cost: [BONUS_COST]
- NGR/GGR: [NGR] / [GGR]
- Abuse flags: [NEEDS CONFIRMATION]
- Commercial sustainability: [NEEDS CONFIRMATION]
- Recommendation: [RECOMMENDATION] Feed offer cost and uptake into `crm-sportsbook-offer-mechanics`.

## 11. Channel Performance
- Channel: [TARGET_CHANNEL]
- Delivery: [DELIVERY_RATE]
- Engagement: [CLICK_RATE]
- Conversion: [BET_CONVERSION]
- Opt-out: [OPT_OUT_RATE]
- Complaints: [COMPLAINTS]
- CTA clarity: [NEEDS CONFIRMATION]
- T&C clarity: [NEEDS CONFIRMATION]
- Recommendation: [RECOMMENDATION] Feed clarity findings into `crm-sportsbook-sms-copy` and `crm-sportsbook-localisation`.

## 12. Journey Performance
- Entry count: [SEGMENT_SIZE]
- Step-level delivery: [JOURNEY_STEPS]
- Reminder impact: [NEEDS CONFIRMATION]
- Exit reasons: [NEEDS CONFIRMATION]
- Frequency cap impact: [FREQUENCY_CAPS]
- Pressure/fatigue risk: [RISK] Review if [OPT_OUT_RATE], [COMPLAINTS], or [POST_CAMPAIGN_RG_FLAGS] worsened.
- Recommendation: [RECOMMENDATION] Feed learnings into `crm-sportsbook-journey-builder`.

## 13. A/B Test or Variant Analysis
- Hypothesis: [TEST_HYPOTHESIS]
- Variant A result: [VARIANT_A]
- Variant B result: [VARIANT_B]
- Control group result: [CONTROL_GROUP_RESULTS]
- Primary KPI: [PRIMARY_KPI]
- Guardrail metrics: [GUARDRAIL_METRICS]
- Winner classification: Inconclusive
- Reason: [NEEDS CONFIRMATION] Sample size, measurement window, and guardrail results need validation.
- Rollout/retest recommendation: [RECOMMENDATION] Retest only if guardrails are acceptable.

## 14. Commercial Review
- Turnover: [TURNOVER]
- GGR: [GGR]
- NGR: [NGR]
- Bonus cost: [BONUS_COST]
- Incremental revenue: [INCREMENTAL_REVENUE]
- Low incrementality risk: [RISK] Do not claim incrementality without [CONTROL_GROUP_RESULTS].
- Commercial verdict: [NEEDS CONFIRMATION]

## 15. Responsible-Gaming & Compliance Post-Review
- Opt-out rate: [OPT_OUT_RATE]
- Complaints: [COMPLAINTS]
- Post-campaign RG flags: [POST_CAMPAIGN_RG_FLAGS]
- Self-exclusion after campaign: [SELF_EXCLUSION_STATUS]
- Cooling-off after campaign: [RG_RISK_STATUS]
- Required follow-up: [RECOMMENDATION] Run `crm-sportsbook-rg-compliance-review` if guardrails worsened.
- RG/compliance verdict: [NEEDS CONFIRMATION]

## 16. UX, Brand & Localisation Review
- Copy clarity: [NEEDS CONFIRMATION]
- CTA clarity: [CTA]
- T&C clarity: [T&CS_LINK]
- Localisation issues: [NEEDS CONFIRMATION]
- Tone issues: [BRAND_TONE]
- Recommendation: [RECOMMENDATION] Review copy and localisation before repeating.

## 17. Operational Review
- Audience build: [NEEDS CONFIRMATION]
- Suppression execution: [SUPPRESSION_RULES]
- Offer setup: [OFFER_MECHANIC]
- Tracking: [NEEDS CONFIRMATION]
- Control group: [CONTROL_GROUP]
- Reporting: [NEEDS CONFIRMATION]
- Operational verdict: [NEEDS CONFIRMATION]

## 18. Key Learnings
- Confirmed learnings: [CONFIRMED] Use only supplied results.
- Directional learnings: [ASSUMPTION] Mark weak evidence as directional.
- Hypotheses for future testing: [RECOMMENDATION] Use `crm-sportsbook-ab-testing`.

## 19. Recommendations
- Repeat: [NEEDS CONFIRMATION]
- Scale: [NEEDS CONFIRMATION]
- Revise: [RECOMMENDATION]
- Retest: [RECOMMENDATION]
- Stop: [RISK] Stop if commercial or RG guardrails failed.
- Investigate: [RECOMMENDATION]
- Send to RG/compliance review: [RECOMMENDATION]

## 20. Next Campaign Ideas
- Idea: Use [OFFER_MECHANIC] for [TARGET_SEGMENT] only if [NGR], [BONUS_COST], and [GUARDRAIL_METRICS] support it.
- Why: [ASSUMPTION] Future campaign should focus on commercially positive, RG-safe behaviour.
- Segment: [TARGET_SEGMENT]
- Offer direction: [OFFER_MECHANIC]
- Channel: [TARGET_CHANNEL]
- Required checks: [SUPPRESSION_RULES], [REGULATORY_NOTES], [GUARDRAIL_METRICS]
- Suggested next skill: `crm-sportsbook-campaign-brief`

## 21. Skill-Pack Feedback Loop
- Market context: Feed any confirmed market-context learning into `crm-sportsbook-market-context`.
- Event opportunity: Feed event performance into `crm-sportsbook-event-opportunity`.
- Player segmentation: Feed segment response into `crm-sportsbook-player-segmentation`.
- Offer mechanics: Feed offer uptake, cost, and abuse indicators into `crm-sportsbook-offer-mechanics`.
- Campaign brief: Feed missed planning gaps into `crm-sportsbook-campaign-brief`.
- SMS copy: Feed clarity and opt-out learning into `crm-sportsbook-sms-copy`.
- Localisation: Feed language or tone friction into `crm-sportsbook-localisation`.
- RG/compliance review: Feed guardrail issues into `crm-sportsbook-rg-compliance-review`.
- Journey builder: Feed reminder and exit learning into `crm-sportsbook-journey-builder`.
- A/B testing: Feed inconclusive or useful findings into `crm-sportsbook-ab-testing`.

## 22. Final Recommendation
- Revise and retest

Reason: [RECOMMENDATION] Do not scale until [CONTROL_GROUP_RESULTS], [NGR], [BONUS_COST], [OPT_OUT_RATE], [COMPLAINTS], and [POST_CAMPAIGN_RG_FLAGS] support the decision.

## 23. Recommended Next Skills
- `crm-sportsbook-rg-compliance-review`
- `crm-sportsbook-offer-mechanics`
- `crm-sportsbook-player-segmentation`
- `crm-sportsbook-ab-testing`
