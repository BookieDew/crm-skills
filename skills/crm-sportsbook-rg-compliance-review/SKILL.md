---
name: crm-sportsbook-rg-compliance-review
description: Reviews sportsbook CRM campaigns, offers, journeys, and copy for responsible-gaming, compliance, UX, brand, and commercial risk with Pass, Needs Revision, or Do Not Launch outcome.
---

# CRM Sportsbook RG Compliance Review

## Purpose

Review a sportsbook CRM campaign, offer, journey, or copy for responsible-gaming, compliance, UX, brand, and commercial risk. Produce a launch recommendation: `Pass`, `Needs Revision`, or `Do Not Launch`.

## Role in the Skill Pack

This skill is the formal review gate before launch and after major changes. It feeds fixes back to campaign brief, offer mechanics, SMS copy, journey builder, and A/B testing.

## When to Use

- Before launching a campaign.
- After writing SMS copy.
- After designing an offer mechanic.
- After building a journey or reminder sequence.
- When a user asks whether a campaign is compliant or safe.
- When performance analysis reveals complaints, RG interactions, or unexpected behaviour.

## When Not to Use

- Do not write the full campaign brief; use `crm-sportsbook-campaign-brief`.
- Do not create initial offer ideas; use `crm-sportsbook-offer-mechanics`.
- Do not localise text; use `crm-sportsbook-localisation`.
- Do not replace qualified legal review where required by the business.

## Required Inputs

### Minimum required inputs

- Campaign, offer, journey, or copy to review.
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[OFFER_MECHANIC]` and `[OFFER_VALUE]` if an offer exists.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[T&CS]`
- `[REGULATORY_NOTES]`
- Suppression rules.
- Eligibility criteria.
- Frequency caps.
- Segment definition.
- Journey timing.

### Advanced optional inputs

- Approved claims list.
- Prohibited wording list.
- Bonus-cost model.
- Customer complaints history.
- RG interaction history.
- Previous compliance decisions supplied at runtime.
- QA checklist from internal teams.

## Output

This skill produces a launch decision, risk summary, suppression checks, copy risks, offer risks, T&C risks, recommended fixes, and open confirmations.

## Workflow

1. Load `crm-sportsbook-shared-principles`.
2. Identify review object: campaign, offer, SMS, journey, test, or analysis recommendation.
3. Confirm runtime market, channel, segment, offer, terms, and regulatory notes.
4. Check mandatory suppressions and channel eligibility.
5. Check copy for prohibited claims and pressure.
6. Check offer for exposure, abuse risk, clarity, and suitability.
7. Check T&Cs for visibility and consistency with copy.
8. Check journey timing, reminders, exits, and frequency caps.
9. Check measurement and control group for responsible evaluation.
10. Return `Pass`, `Needs Revision`, or `Do Not Launch` with fixes.

## Decision Logic

- `Do Not Launch` if self-excluded users or RG-risk users may be targeted.
- `Do Not Launch` if the campaign targets users because of recent heavy losses.
- `Do Not Launch` if T&Cs are missing for a material offer.
- `Do Not Launch` if copy implies guaranteed winning, financial solution, or chasing losses.
- `Needs Revision` if offer constraints are unclear, channel consent is missing, urgency is too strong, or terms are not visible enough.
- `Needs Revision` if commercial exposure is uncapped or bonus abuse risk is not handled.
- `Pass` only when suppressions, terms, copy, offer, channel, journey, and measurement are coherent and labelled.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, and whichever skill produced the reviewed item.
- Skills that should normally run after this one: `crm-sportsbook-campaign-brief`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-sms-copy`, `crm-sportsbook-journey-builder`, or `crm-sportsbook-ab-testing` when revisions are required.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, offer safety, channel principles, and final campaign quality checklist.

## Sportsbook-Specific Considerations

Review sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market. Do not hardcode country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If market-specific compliance knowledge is needed, ask for `[REGULATORY_NOTES]`, label it `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt review standards to `[TARGET_CHANNEL]`.

For SMS:

- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.
- Check character pressure does not hide material terms.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline responsible-gaming rules even if the user says the market has no strict rules.

The review must avoid approving:

- Targeting self-excluded users.
- Targeting users with responsible-gaming risk flags.
- Encouraging chasing losses.
- Referring to previous losses as a reason to bet again.
- Saying or implying betting solves financial problems.
- Guaranteed-win language.
- Misleading risk-free claims unless approved.
- Aggressive urgency.
- Hidden or unclear T&Cs.
- Emotional pressure.
- Offers based on recent heavy losses.
- Manipulative win-back language.

## Commercial Guardrails

Protect margin and bonus cost. Confirm value-to-customer fit, avoid over-incentivising active users, avoid rich offers to bonus abusers, avoid open-ended exposure, require minimum odds where relevant, minimum stake where relevant, max bonus value where relevant, eligible markets where relevant, clear expiry, and objective fit.

## Brand & UX Guardrails

Review whether the customer communication is direct, jargon-free, clear on customer value, clear on next action, not misleading, not fake-personalised, not stereotyped, and not implying certainty of winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## RG & Compliance Review

### Launch Decision
- Pass / Needs Revision / Do Not Launch:

### Risk Summary
- [RISK] RG:
- [RISK] Compliance:
- [RISK] Commercial:
- [RISK] UX/Brand:

### Suppression Checks
- Self-exclusion:
- RG flags:
- Marketing consent:
- Channel eligibility:
- Frequency caps:

### Copy Risks
- Finding:
- Recommended fix:

### Offer Risks
- Finding:
- Recommended fix:

### T&C Risks
- Finding:
- Recommended fix:

### Required Fixes
- [RECOMMENDATION]
```

## Example User Request

Review this `[TARGET_CHANNEL]` campaign for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`: `[CAMPAIGN_OR_COPY]`. Offer: `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`; `[T&CS]`; `[REGULATORY_NOTES]`.

## Example Output

```markdown
## RG & Compliance Review

- Launch Decision: Needs Revision.
- [RISK] T&C visibility is incomplete because `[T&CS]` are not final.
- [RISK] Suppression checks must confirm self-exclusion, RG flags, marketing consent, channel eligibility, and frequency caps.
- [RECOMMENDATION] Add clear terms reference, cap `[OFFER_VALUE]`, confirm eligible markets, and remove any urgency stronger than neutral timing.
```

