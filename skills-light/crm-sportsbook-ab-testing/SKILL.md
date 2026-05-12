---
name: crm-sportsbook-ab-testing
description: Light execution version for safe, measurable sportsbook CRM A/B tests with hypotheses, variants, audience splits, control groups, KPIs, guardrails, measurement windows, decision rules, suppressions, commercial controls, and analysis handoff.
---

# CRM Sportsbook A/B Testing Light

## Purpose
Design responsible, measurable sportsbook CRM tests that compare variants without weakening RG, compliance, commercial, channel, or customer-experience guardrails.

## Role in the Skill Pack
Run after campaign brief, SMS copy if testing SMS, localisation if testing language/tone, RG/compliance review before launch, and journey builder if testing journey logic. Feed post-campaign analysis.

## When to Use
Use for SMS copy tests, offer value tests, offer mechanic tests, CTA tests, timing tests, journey tests, segment tests, localisation tests, holdout/control group tests, and incrementality planning.

## When Not to Use
Do not create campaign strategy, raw segmentation, offer mechanics, SMS copy, localisation, final compliance approval, or completed campaign analysis. Do not invent uplift, market facts, sample size, statistical significance, or expected performance without supplied data or labelled assumptions.

## Minimum Required Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_MARKET]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT] or segmentation output.
- Campaign brief or enough campaign context.
- Test hypothesis or request to create one.
- Variant A and Variant B, or request to propose variants.
- Primary KPI or request to recommend one.
- Suppression rules or instruction to use shared baseline suppressions.

## Core Workflow
1. Apply shared principles and read campaign, copy, localisation, journey, and RG review outputs.
2. Define test objective and hypothesis.
3. Define test type and variants.
4. Keep variants different by one main variable where possible.
5. Define audience eligibility, suppressions, split logic, control group, KPIs, guardrails, measurement window, tracking, and decision rule.
6. Check commercial exposure and RG/compliance safety.
7. Define post-campaign analysis handoff.
8. List required fixes before launch.

## Core Decision Logic
- If campaign context, variants, KPI, measurement window, suppressions, or tracking are missing, mark [NEEDS CONFIRMATION].
- If RG/compliance review has not been run, recommend it before launch.
- If a test exposes one group to materially higher RG risk, do not recommend it.
- Do not test aggressive pressure versus neutral wording.
- If variants change multiple major variables, warn that learning will be unclear.
- If sample size or segment size is weak, treat results as directional only.
- For SMS copy tests, keep audience, offer, timing, and [T&CS_LINK] constant and include character counts if copy is shown.
- For offer value tests, define exposure caps and compare NGR and bonus cost, not just uptake.
- For offer mechanic tests, compare customer understanding, commercial exposure, and RG risk.
- For timing and journey tests, respect frequency caps and monitor fatigue.
- For localisation tests, preserve meaning and [T&CS] clarity.
- Recommend control groups where incrementality matters.
- Do not claim statistical validity without sufficient data and method.

## Dependencies
- Normally before: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder` when journey logic is tested, plus SMS/localisation outputs where relevant.
- Normally after: `crm-sportsbook-post-campaign-analysis`.

## Test Types
- SMS copy: value-led vs event-led, CTA, short vs clearer, personalisation vs none.
- Offer value: lower vs higher [OFFER_VALUE] with exposure controls.
- Offer mechanic: compare mechanics while keeping audience stable.
- CTA: change only action wording.
- Timing: compare send or reminder timing without pressure.
- Journey: reminder vs no reminder or timing variants.
- Segment: compare audience definitions without exposing vulnerable users.
- Localisation: compare language/tone variants that preserve meaning.
- Control group/holdout: measure incrementality without withholding required service or RG communications.

## Market-Agnostic Rules
Do not assume local laws, opt-in rules, event schedules, send-time norms, sports preferences, performance benchmarks, response rates, or statistical baselines.

## Responsible-Gaming Guardrails
Apply suppression before assignment, before contact, before reminders, and before offer award. Suppress self-excluded, RG-risk, cooling-off, opted-out, restricted, bonus-blocked, abuse-restricted, and relevant heavy-loss users. Include opt-outs, complaints, and post-campaign RG flags as guardrails.

## Commercial Guardrails
Track bonus cost, GGR, NGR, incremental value, abuse, sharp/arb exposure, VIP cost, offer leakage, frequency fatigue, control integrity, and inconclusive-test risk.

## Brand/UX Guardrails
Variants must be fair, clear, comparable, non-misleading, equal in [T&CS] visibility, non-invasive, and aligned to [BRAND_TONE].

## Assumption Labels
Use [CONFIRMED], [ASSUMPTION], [NEEDS CONFIRMATION], [RISK], and [RECOMMENDATION].

## Output Template
```markdown
# A/B Testing Output

## 1. Test Context
- Target market: [TARGET_MARKET]
- Target language: [TARGET_LANGUAGE]
- Target channel: [TARGET_CHANNEL]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Offer mechanic: [OFFER_MECHANIC]
- Offer value: [OFFER_VALUE]
- Test type:

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Test Objective and Hypothesis
- Objective:
- Hypothesis:

## 6. Test Design
- Variant A:
- Variant B:
- What changes:
- What stays the same:
- Audience:
- Randomisation:
- Control group:
- Measurement window:

## 7. Audience Eligibility and Suppressions
- Inclusion:
- Channel eligibility:
- Offer/product/account eligibility:
- RG eligibility:
- Self-exclusion:
- RG risk:
- Cooling-off:
- Channel opt-out:
- Compliance/account restrictions:
- Bonus abuse / sharp / arb restrictions:
- Recently heavy-losing users where relevant:

## 8. KPI Framework
- Primary KPI:
- Secondary KPIs:
- Commercial KPIs:
- RG/UX guardrails:
- Diagnostic metrics:

## 9. Tracking and Measurement Plan
- Assignment:
- Send/delivery:
- Click or offer view:
- Conversion:
- Bonus awarded/redeemed:
- GGR/NGR:
- Bonus cost:
- Opt-out:
- Complaint:
- RG flag:
- Exit reason if journey:
- Control comparison:

## 10. Decision Rule
- Winning condition:
- Guardrail failure condition:
- Inconclusive handling:
- Rollout rule:
- Retest rule:
- Stop rule:

## 11. RG, Compliance, Commercial, and Operational Review
- Suppression before assignment/contact:
- Variant risk difference:
- [T&CS] consistency:
- Bonus cost:
- Abuse/sharp/arb risk:
- Tracking readiness:
- Required approvals:

## 12. Post-Campaign Analysis Handoff
- Audience counts:
- Variant assignment:
- Delivery/engagement:
- Conversion:
- Bonus cost:
- GGR/NGR:
- Guardrails:
- Segment splits:
- Control group data:
- Anomalies:

## 13. Required Fixes Before Launch
| Issue | Risk type | Required fix | Owner | Blocking status |
|---|---|---|---|---|
|  |  |  |  |  |

## 14. Recommended Next Skills
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-journey-builder
- crm-sportsbook-post-campaign-analysis

## 15. Final Recommendation
- Ready for test setup / Needs missing inputs / Needs copy/localisation / Needs offer approval / Needs BI/statistics review / Needs specialist review / Not recommended:
- Rationale:
```

## Recommended Next Skills
Use RG/compliance review after final variants, journey builder for operational setup, and post-campaign analysis after completion.
