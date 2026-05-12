---
name: crm-sportsbook-journey-builder
description: Turns sportsbook CRM campaigns into customer journeys with single-message, multi-step SMS journey, reminder logic, suppression logic, exit criteria, control group, frequency caps, and RG-safe reactivation logic.
---

# CRM Sportsbook Journey Builder

## Purpose

Turn a sportsbook CRM campaign into a customer journey with message timing, reminder logic, suppression logic, exit criteria, control group, frequency caps, and RG-safe reactivation handling.

## Role in the Skill Pack

This skill operationalises the campaign brief after offer and compliance checks. It feeds A/B testing and post-campaign analysis.

## When to Use

- A campaign needs a launch journey.
- A single-message campaign needs send rules and exits.
- A multi-step SMS journey needs reminders and suppression logic.
- A reactivation campaign needs safe contact logic.
- A campaign needs frequency caps, control group, or measurement routing.

## When Not to Use

- Do not create the initial offer mechanic; use `crm-sportsbook-offer-mechanics`.
- Do not write final SMS copy; use `crm-sportsbook-sms-copy`.
- Do not approve compliance; use `crm-sportsbook-rg-compliance-review`.
- Do not invent local send-time rules or market requirements.

## Required Inputs

### Minimum required inputs

- Campaign objective.
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- Offer and CTA.
- Suppression rules or statement that they are missing.

### Recommended inputs

- Campaign brief.
- SMS copy variants if `[TARGET_CHANNEL]` is SMS.
- `[TARGET_EVENT]`
- Event timing.
- `[T&CS]`
- `[REGULATORY_NOTES]`
- Frequency caps.
- Control-group rules.
- Exit criteria.

### Advanced optional inputs

- Customer lifecycle stage.
- Predicted churn risk.
- Deposit and bet recency.
- Bonus history.
- Channel engagement.
- Journey orchestration platform limits.
- Previous journey performance.

## Output

This skill produces a journey map covering single message or multi-step sequence, timing, trigger, message purpose, eligibility, suppression, exit criteria, control group, measurement events, and risk controls.

## Workflow

1. Load `crm-sportsbook-shared-principles` and campaign brief.
2. Confirm launch objective, audience, offer, event timing, and channel.
3. Check that RG/compliance review has passed or list pending fixes.
4. Choose journey type: single message, multi-step SMS journey, reminder logic, or reactivation flow.
5. Define entry criteria, suppressions, and frequency caps.
6. Define message steps, timing, and stop conditions.
7. Add exit criteria for conversion, opt-out, RG flag, self-exclusion, complaint, frequency cap, or expiry.
8. Add control group and measurement events.
9. Mark open confirmations and risks.

## Decision Logic

- Use a single message when the offer is simple, event window is short, or frequency risk is high.
- Use multi-step SMS only when reminders add value and remain non-pressuring.
- For reactivation, use cautious language and limit reminders.
- Suppress immediately on self-exclusion, RG flag, opt-out, channel ineligibility, frequency cap, or campaign expiry.
- Exit customers who convert, become ineligible, receive the offer, or hit frequency limits.
- Do not send reminders based on losses.
- Do not escalate incentive value automatically after non-response unless approved and reviewed.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-rg-compliance-review`, optionally `crm-sportsbook-sms-copy`.
- Skills that should normally run after this one: `crm-sportsbook-ab-testing`, `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, channel principles, and measurement principles.

## Sportsbook-Specific Considerations

Design journeys around sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market, local send-time requirement, local event schedule, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If local journey rules are needed, ask for them, label assumptions `[ASSUMPTION]`, mark missing details `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt journey design to `[TARGET_CHANNEL]`.

For SMS:

- Keep each message short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.
- Use reminders sparingly and only when they are useful and non-pressuring.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules even if the user says the market has no strict rules. The journey must suppress self-excluded users, RG-risk users, users selected due to recent heavy losses, users with no valid consent, and users who opt out or show risk signals after entry.

Avoid chasing-loss triggers, loss-based reminders, financial-solution claims, guaranteed-win language, misleading risk-free claims unless approved, aggressive urgency, unclear T&Cs, emotional pressure, and manipulative win-back journeys.

## Commercial Guardrails

Protect margin and bonus cost. Do not increase incentive value automatically without a business rule and review. Cap exposure, use minimum odds, minimum stake, max bonus value, eligible markets, clear expiry, and objective fit. Hold out a control group where possible.

## Brand & UX Guardrails

Make the journey easy to understand. Be direct, avoid jargon, explain value quickly, make the next action obvious, avoid misleading terms, avoid fake personalisation, avoid stereotypes, and do not imply certainty of winning.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

```markdown
## Journey Plan

### Journey Type
- Single message / Multi-step SMS / Reminder / Reactivation:

### Entry Criteria
- [CONFIRMED]

### Suppressions
- Self-exclusion:
- RG flags:
- Marketing consent:
- Channel eligibility:
- Frequency caps:

### Steps
| Step | Trigger | Timing | Message purpose | Exit check | Risk control |
|---|---|---|---|---|---|
| 1 |  |  |  |  |  |

### Exit Criteria
- Conversion:
- Opt-out:
- RG flag:
- Expiry:

### Control Group
- [RECOMMENDATION]

### Open Items
- [NEEDS CONFIRMATION]
```

## Example User Request

Build an SMS journey for `[TARGET_SEGMENT]` in `[TARGET_MARKET]` around `[TARGET_EVENT]` with `[OFFER_MECHANIC]` worth `[OFFER_VALUE]`.

## Example Output

```markdown
## Journey Plan

- [RECOMMENDATION] Journey Type: Single SMS plus one neutral reminder only if `[TARGET_EVENT]` timing and frequency caps allow it.
- [CONFIRMED] Entry: `[TARGET_SEGMENT]` with valid `[TARGET_CHANNEL]` consent.
- [RISK] Suppress self-excluded, RG-risk, frequency-capped, bonus abuse risk, and ineligible-channel users.
- [NEEDS CONFIRMATION] Event timing, journey expiry, control-group percentage, and final `[T&CS]`.
```

