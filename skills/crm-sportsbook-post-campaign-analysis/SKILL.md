---
name: crm-sportsbook-post-campaign-analysis
description: Analyses sportsbook CRM campaign performance including performance summary, segment analysis, offer performance, channel performance, bonus cost, GGR/NGR impact, RG and compliance observations, learnings, and next campaign recommendations.
---

# CRM Sportsbook Post-Campaign Analysis

## Purpose

Analyse sportsbook CRM campaign performance and produce learnings for future campaigns, segments, offers, journeys, tests, and compliance decisions.

## Role in the Skill Pack

This skill closes the loop. It uses campaign brief, test plan, and performance data to generate evidence-based recommendations that feed market context, segmentation, offer mechanics, and future campaign briefs.

## When to Use

- A campaign has completed.
- A CRM manager provides campaign performance data.
- A/B test results need interpretation.
- Bonus cost, GGR, NGR, or margin impact must be evaluated.
- RG/compliance observations need to be captured.
- The team wants next campaign recommendations.

## When Not to Use

- Do not invent missing performance data.
- Do not create a launch campaign from scratch; use `crm-sportsbook-campaign-brief`.
- Do not decide future compliance rules without runtime evidence and review.
- Do not infer market-wide behaviour from one small campaign without caveats.

## Required Inputs

### Minimum required inputs

- Campaign objective.
- Campaign audience or `[TARGET_SEGMENT]`.
- Delivered count or reachable audience.
- Conversion or outcome data.

### Recommended inputs

- Campaign brief.
- A/B test plan.
- Control-group results.
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- Bonus issued and redeemed.
- Turnover.
- GGR.
- NGR.
- Opt-outs.
- RG interactions.

### Advanced optional inputs

- Segment-level performance.
- Bet type performance.
- Sport or event performance.
- Stake-band performance.
- VIP performance.
- Bonus sensitivity cuts.
- Margin by eligible market.
- Complaint data.
- Long-term retention.
- Incrementality model.

## Output

This skill produces a post-campaign report with performance summary, segment analysis, offer performance, channel performance, bonus cost, GGR/NGR impact, RG/compliance observations, learnings, and next campaign recommendations.

## Workflow

1. Load `crm-sportsbook-shared-principles`, campaign brief, and test plan if available.
2. Confirm objective, audience, offer, channel, timing, and measurement window.
3. Validate available data and mark missing data `[NEEDS CONFIRMATION]`.
4. Summarise delivery, conversion, offer redemption, bonus cost, turnover, GGR, NGR, and margin.
5. Compare variants and control group where available.
6. Analyse by segment, lifecycle, value, sport preference, bet type, stake band, bonus sensitivity, VIP status, churn risk, and channel eligibility where data exists.
7. Review RG/compliance signals, opt-outs, complaints, and risky behaviour indicators.
8. Extract learnings and next campaign recommendations.
9. Identify what to stop, start, continue, or test next.

## Decision Logic

- If no control group exists, avoid claiming incrementality.
- If NGR is negative after bonus cost, recommend offer constraint changes.
- If conversion is high but RG signals or opt-outs rise, prioritise safety and contact strategy review.
- If active users converted without incremental lift, reduce incentives or retarget.
- If bonus abuse indicators appear, tighten eligibility and constraints.
- If VIP response is strong but cost is high, review bespoke value and margin.
- If event relevance drove performance, feed that into future event opportunity scoring.
- If copy clarity issues appear, feed learnings to SMS copy and localisation.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, optionally `crm-sportsbook-ab-testing`.
- Skills that should normally run after this one: `crm-sportsbook-market-context`, `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel principles, and measurement principles.

## Sportsbook-Specific Considerations

Analyse sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume market benchmarks, local behaviours, local sports calendars, local regulation, local operators, local payment methods, or geo-specific performance norms.

If market-specific interpretation is needed, ask for it, label it `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Analyse performance by `[TARGET_CHANNEL]`.

For SMS:

- Check delivered count, click or response where available, conversion, opt-outs, complaints, offer clarity issues, CTA clarity, and T&C handling.
- Keep future copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules during interpretation. Flag campaigns that may have reached suppressed users, generated RG interactions, used risky copy, encouraged chasing, referenced losses, implied financial solutions, used guaranteed-win language, used misleading risk-free claims unless approved, applied aggressive urgency, hid T&Cs, used emotional pressure, targeted recent heavy losses, or used manipulative win-back language.

## Commercial Guardrails

Evaluate margin and bonus cost. Review whether `[OFFER_VALUE]` matched customer value, whether active users were over-incentivised, whether bonus abusers received rich offers, whether exposure was capped, and whether minimum odds, minimum stake, max bonus value, eligible markets, and expiry worked.

## Brand & UX Guardrails

Review whether communication was direct, jargon-free, clear on customer value, clear on next action, not misleading, not fake-personalised, not stereotyped, and not implying certainty of winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Post-Campaign Analysis

### Performance Summary
- Delivered:
- Conversion:
- Bonus issued:
- Bonus cost:
- GGR:
- NGR:

### Segment Analysis
- Best-performing segment:
- Weak segment:
- Risk segment:

### Offer Performance
- Mechanic:
- Redemption:
- Cost:
- Margin impact:

### Channel Performance
- [TARGET_CHANNEL]:
- Opt-outs:
- Complaints:

### RG & Compliance Observations
- [RISK]

### Learnings
- [CONFIRMED]
- [ASSUMPTION]

### Next Campaign Recommendations
- [RECOMMENDATION]
```

## Example User Request

Analyse this completed `[TARGET_CHANNEL]` campaign for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` using `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`: `[PERFORMANCE_DATA]`.

## Example Output

```markdown
## Post-Campaign Analysis

- [CONFIRMED] Campaign: `[TARGET_CHANNEL]` campaign for `[TARGET_SEGMENT]`.
- [NEEDS CONFIRMATION] Control-group results are required before claiming incrementality.
- [RECOMMENDATION] Compare conversion, bonus cost, GGR, NGR, opt-outs, and RG interactions by lifecycle, value band, sport preference, bet type, and bonus sensitivity.
- [RISK] If bonus cost exceeds incremental NGR, tighten `[OFFER_MECHANIC]` constraints or retarget the segment.
```

