---
name: crm-sportsbook-post-campaign-analysis
description: Light execution version for analysing supplied sportsbook CRM campaign results, variants, journeys, commercial outcomes, and RG/compliance observations without inventing performance data, causality, market facts, or statistical conclusions.
---

# CRM Sportsbook Post-Campaign Analysis Light

## Purpose
Analyse completed sportsbook CRM campaigns using supplied results and prior campaign context to produce learnings, recommendations, and feedback for future skills.

## Role in the Skill Pack
This is the learning and optimisation skill. It runs after campaign brief, SMS copy, localisation, RG review, journey builder, and A/B testing when campaign results are available. It feeds future market context, event opportunity, segmentation, offer mechanics, campaign brief, SMS copy, localisation, RG review, journey, and testing.

## When to Use
Use for completed campaign analysis, SMS results, offer performance, event-led results, journey performance, A/B test readout, segment comparison, ROI/NGR review, RG/compliance post-review, management summary, and recommendations to repeat, scale, revise, retest, stop, or investigate.

## When Not to Use
Do not create campaign strategy, copy, offers, journeys, or pre-launch tests. Do not invent missing results, uplift, causality, statistical significance, market facts, or legal conclusions. Do not ignore bonus cost, NGR, opt-outs, complaints, or RG flags.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT]
- [OFFER_MECHANIC], if promotional.
- Campaign results or key performance data.
- Primary KPI or campaign success metric.
- Campaign brief output, if available.

## Core Workflow
1. Apply shared principles and review available brief, SMS, localisation, RG review, journey, and A/B test outputs.
2. Identify supplied performance, commercial, variant, control, guardrail, and operational data.
3. Separate confirmed results from assumptions and missing data.
4. Assess data quality, tracking reliability, control group availability, sample size, and measurement window.
5. Review objective, funnel, segment, offer, channel, journey, variant, commercial, RG/compliance, UX/brand, localisation, and operational performance.
6. Avoid causality and incrementality claims unless supported by valid comparison data.
7. Classify A/B results only when data supports it.
8. Produce learnings, recommendations, next campaign ideas, and skill-pack feedback.

## Core Decision Logic
- If campaign results are missing, mark [NEEDS CONFIRMATION].
- If no control group or valid comparison exists, do not claim incrementality; use directional language.
- If no valid A/B design exists, do not claim a variant caused performance differences.
- If sample size is small, tracking is broken, or measurement window is too short, mark conclusions as directional or unreliable.
- Turnover alone is not success; compare GGR, NGR, bonus cost, incrementality, and guardrails.
- If GGR rises but bonus cost rises more or NGR falls, flag commercial quality risk.
- If opt-outs, complaints, RG flags, self-exclusions, cooling-off, or high-loss indicators worsen, do not recommend scale without RG/compliance review.
- If commercial performance is positive but guardrails fail, do not roll out broadly.
- If event context is unique, avoid overgeneralising.
- If reactivation returns are one-time only or guardrails worsen, do not scale without revision.
- If localisation variants differ in meaning, do not treat them as clean A/B variants.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, plus SMS/localisation/RG review outputs where relevant.
- Feeds back into: market context, event opportunity, segmentation, offer mechanics, campaign brief, SMS copy, localisation, RG/compliance review, journey builder, and A/B testing.

## Analysis Modes
- Campaign summary: objective, KPI, commercial result, guardrails, verdict.
- SMS analysis: delivery, click, conversion, opt-out, complaints, copy clarity, [T&CS] friction.
- Offer analysis: uptake, qualification, redemption, bonus cost, NGR/GGR, abuse, sustainability.
- Event-led analysis: timing, segment-event fit, product availability, repeatability.
- Journey analysis: step funnel, drop-off, exits, reminder impact, frequency/fatigue.
- A/B test analysis: hypothesis, assignment, sample, KPI, guardrails, control, winner classification.
- Segment analysis: conversion, NGR/GGR, bonus cost, opt-out, complaints, RG flags.
- Commercial analysis: turnover, GGR, NGR, bonus cost, incrementality, margin, abuse.
- RG post-review: opt-outs, complaints, RG flags, self-exclusion, cooling-off, pressure patterns.

## Market-Agnostic Rules
Do not assume local laws, language, event schedules, sport preferences, opt-in rules, channel norms, performance benchmarks, payment methods, operators, regulators, or cultural tone.

## Responsible-Gaming Guardrails
If guardrails worsened, recommend stop, revise, suppression review, copy/journey review, and `crm-sportsbook-rg-compliance-review` before scale.

## Commercial Guardrails
Evaluate bonus cost, NGR, GGR, incrementality, control quality, margin, abuse, sharp/arb indicators, VIP cost, repeat activity, support burden, and opt-out/complaint cost. Do not estimate impact without data.

## Brand/UX Guardrails
Identify offer misunderstanding, CTA confusion, [T&CS] friction, copy fatigue, aggressive tone, invasive personalisation, localisation friction, excessive frequency, and support burden.

## A/B Test Result Classification
- Clear winner: primary KPI improves, guardrails stable, sample and measurement credible, decision rule met.
- Directional winner: likely better but data limited and guardrails acceptable.
- Inconclusive: weak sample, incomplete tracking, short window, close results, or external factors.
- Do not roll out: KPI improves but guardrails, bonus cost, complaints, RG risk, abuse, or customer understanding fail.

## Incrementality Caution
- Use control group comparison where available.
- Without control group, use directional language.
- Historical baselines are weaker and must be caveated.
- Highly active segments may have acted without the campaign.
- Do not scale on engagement alone when NGR, bonus cost, or guardrails are weak.

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
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
- Measurement window:
- Material analysed:

## 2. Executive Summary
- Overall performance:
- Commercial outcome:
- Guardrail outcome:
- Main learning:
- Final recommendation:

## 3. Confirmed Inputs
- [CONFIRMED]

## 4. Working Assumptions
- [ASSUMPTION]

## 5. Needs Confirmation
- [NEEDS CONFIRMATION]

## 6. Data Quality Assessment
- Completeness:
- Tracking reliability:
- Control group availability:
- Variant assignment reliability:
- Sample size:
- Measurement window:
- Known anomalies:
- Confidence: Strong / Usable with limitations / Directional only / Insufficient

## 7. Objective and Funnel Performance
- Primary KPI:
- Result:
- Interpretation:
- Delivered:
- Clicked/viewed:
- Offer opted in:
- Deposited if relevant:
- Bet placed:
- Bonus awarded/redeemed:
- Conversion:
- Main friction:

## 8. Segment, Offer, Channel, and Journey Performance
- Segment performance:
- Offer uptake:
- Bonus cost:
- GGR/NGR:
- Delivery and engagement:
- Opt-outs:
- Complaints:
- Journey step results:
- Exit reasons:

## 9. A/B Test or Variant Analysis
- Hypothesis:
- Variant A:
- Variant B:
- Control group:
- Primary KPI:
- Guardrails:
- Winner classification: Clear winner / Directional winner / Inconclusive / Do not roll out
- Reason:
- Rollout/retest recommendation:

## 10. Commercial Review
- Turnover:
- GGR:
- NGR:
- Bonus cost:
- Incremental revenue:
- Low incrementality risk:
- Abuse/sharp/arb risk:
- Commercial verdict:

## 11. Responsible-Gaming & Compliance Post-Review
- Opt-out rate:
- Complaints:
- Post-campaign RG flags:
- Self-exclusion after campaign:
- Cooling-off after campaign:
- Heavy-loss indicators if supplied:
- Copy or journey pressure concerns:
- Required follow-up:
- Verdict:

## 12. UX, Brand, Localisation, and Operational Review
- Copy clarity:
- CTA clarity:
- [T&CS] clarity:
- Localisation issues:
- Tone issues:
- Support burden:
- Suppression execution:
- Tracking:
- QA:
- Incidents:

## 13. Key Learnings
- Confirmed learnings:
- Directional learnings:
- Future hypotheses:

## 14. Recommendations
- Repeat:
- Scale:
- Revise:
- Retest:
- Stop:
- Investigate:
- Send to RG/compliance review:

## 15. Skill-Pack Feedback Loop
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

## 16. Final Recommendation
- Repeat same setup / Scale with guardrails / Revise and retest / Stop campaign type / Needs BI/statistical review / Needs RG/compliance investigation / Insufficient data:
- Rationale:

## 17. Recommended Next Skills
- crm-sportsbook-ab-testing
- crm-sportsbook-offer-mechanics
- crm-sportsbook-player-segmentation
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-campaign-brief
```

## Recommended Next Skills
Route follow-up to the skill where the learning applies. Use RG/compliance review if guardrails worsened and A/B testing if the next step is a cleaner test.
