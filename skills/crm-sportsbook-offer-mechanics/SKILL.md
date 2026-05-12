---
name: crm-sportsbook-offer-mechanics
description: Designs sportsbook offer mechanics including free bet, bet-and-get, odds boost, accumulator insurance, cashback, bet builder boost, deposit bonus, reload offer, mission or challenge, loyalty points, VIP bespoke offer, event-specific voucher, and personalised stake-back offer.
---

# CRM Sportsbook Offer Mechanics

## Purpose

Design sportsbook offer mechanics that fit the target segment, event, channel, commercial objective, and responsible-gaming constraints.

## Role in the Skill Pack

This skill sits between segmentation and campaign brief creation. It supplies the offer structure, suitability, risks, constraints, and example placeholder terms used by SMS, journey, testing, and compliance skills.

## When to Use

- A CRM manager needs offer ideas.
- A campaign needs `[OFFER_MECHANIC]` and `[OFFER_VALUE]`.
- A segment needs the safest and most commercially sensible incentive.
- A campaign needs terms, caps, minimum odds, stake, expiry, or eligible markets.
- An existing offer needs risk review or improvement.

## When Not to Use

- Do not write final SMS copy; use `crm-sportsbook-sms-copy`.
- Do not make final launch decisions; use `crm-sportsbook-rg-compliance-review`.
- Do not invent local regulations or market-specific offer limits.
- Do not choose an offer without segment, value, and risk context.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[TARGET_SEGMENT]`
- Campaign objective.
- Intended `[OFFER_MECHANIC]` or request for options.

### Recommended inputs

- `[OFFER_VALUE]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- Lifecycle stage.
- Customer value band.
- Bonus sensitivity.
- Bonus history.
- Stake level.
- Margin or bonus-cost limit.
- `[T&CS]`
- `[REGULATORY_NOTES]`

### Advanced optional inputs

- Product availability.
- Eligible bet types.
- Minimum odds policy.
- Minimum stake policy.
- Maximum bonus value policy.
- Trading restrictions.
- Sharp or arb sensitivity.
- Bonus abuse risk.
- Historic offer performance.

## Output

This skill produces a mechanic recommendation table with best use case, segment fit, weak segment fit, commercial benefit, commercial risk, RG/compliance risk, recommended constraints, and example structure using placeholders.

## Workflow

1. Load `crm-sportsbook-shared-principles`.
2. Confirm objective, target segment, target event, target sport, channel, offer value, T&Cs, and regulatory notes.
3. Exclude any mechanic that conflicts with RG, compliance, product availability, or channel clarity.
4. Score each viable mechanic for segment fit, incremental value, cost, margin exposure, abuse risk, and UX clarity.
5. Select the recommended mechanic and one fallback.
6. Define constraints: eligible customers, eligible markets, minimum odds, minimum stake, max bonus value, expiry, opt-in if required, and control-group logic.
7. Flag risks and required confirmations.
8. Provide a placeholder example structure.

## Decision Logic

- Activation: prefer simple mechanics with clear first action and capped exposure.
- Retention: use value that rewards desired behaviour without over-incentivising already active users.
- Reactivation: use cautious, RG-safe value and avoid emotionally manipulative win-back framing.
- Event activation: match mechanic to event timing and customer event affinity.
- Cross-sell: use simple education-friendly mechanics only where eligibility and product fit are confirmed.
- VIP engagement: use bespoke value with clear review, margin protection, and RG checks.
- High bonus sensitivity or bonus abuse risk: reduce value, add constraints, or exclude.
- Sharp or arb-sensitive users: avoid exploitable boosts and open-ended value.
- SMS channel: avoid mechanics too complex to explain clearly.

## Dependencies

- Skills that should normally run before this one: `crm-sportsbook-shared-principles`, `crm-sportsbook-market-context`, `crm-sportsbook-player-segmentation`, optionally `crm-sportsbook-event-opportunity`.
- Skills that should normally run after this one: `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`.
- Shared principles it must follow: market-agnostic rules, assumption labels, RG baseline, suppression rules, commercial protection, offer mechanic safety rules, channel communication principles, and measurement principles.

## Sportsbook-Specific Considerations

Consider sport preference, event relevance, bet type preference, pre-match versus live betting, single versus accumulator preference, odds boost suitability, free bet suitability, cashback suitability, bet builder suitability, deposit behaviour, bonus history, bonus sensitivity, VIP status, recreational versus sharp behaviour, arb-sensitive users, churn risk, stake level, margin protection, event timing, and bonus abuse risk.

## Market-Agnostic Design Rules

Never assume a market. Do not hardcode country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.

If market-specific offer rules are needed, ask for `[REGULATORY_NOTES]` or `[T&CS]`, label an assumption `[ASSUMPTION]`, mark it `[NEEDS CONFIRMATION]`, or instruct research if tools are available. Do not invent hard market facts.

## Channel-Aware Design Rules

Adapt offer complexity to `[TARGET_CHANNEL]`.

For SMS:

- Prefer simple mechanics.
- Keep copy short.
- Make the offer clear in one sentence.
- Use a simple CTA.
- Avoid complex mechanics.
- Avoid aggressive urgency.
- Include or reference T&Cs clearly.
- Avoid jargon.

Email and push should be future channel-specific skills and not blended into SMS.

## Responsible Gaming & Compliance Guardrails

Apply baseline RG rules even if the user says the market has no strict rules. Do not target self-excluded users, RG-risk users, users selected due to recent heavy losses, or users lacking channel eligibility.

Avoid mechanics or copy that encourage chasing losses, reference losses, imply financial solutions, promise guaranteed wins, use misleading risk-free claims unless approved, apply aggressive urgency, hide T&Cs, pressure emotionally, or use manipulative win-back language.

## Commercial Guardrails

Protect margin and bonus cost by matching `[OFFER_VALUE]` to customer value, avoiding over-incentivising active users, avoiding rich offers to bonus abusers, avoiding open-ended exposure, using minimum odds, minimum stake, maximum bonus value, eligible markets, clear expiry, and objective fit.

## Brand & UX Guardrails

Make the customer value clear quickly. Avoid jargon, misleading terms, fake personalisation, stereotypes, and certainty-of-winning claims. State the next action plainly.

## Assumption Labels

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Supported Mechanics Matrix

| Mechanic | Best use case | Segment fit | Weak segment fit | Commercial benefit | Commercial risk | RG/compliance risk | Recommended constraints | Example structure |
|---|---|---|---|---|---|---|---|---|
| Free bet | Activation, reactivation, event activation | Low-to-mid value eligible users with controlled bonus history | Bonus abuse risk, sharp or arb-sensitive users, already highly active users | Clear value, capped cost | Bonus cost without incremental betting | May pressure reactivation if framed poorly | Max bonus value, eligible markets, expiry, minimum odds, one per customer | Bet `[MIN_STAKE]` on `[TARGET_EVENT]` and get `[OFFER_VALUE]` free bet; `[T&CS]` apply. |
| Bet-and-get | Event activation and retention | Users likely to place a qualifying bet | Users with low intent or unclear sport affinity | Pays only after action | Can overpay active users | Must not imply guaranteed return | Minimum stake, minimum odds, eligible bet types, max reward, expiry | Place a qualifying bet on `[TARGET_SPORT]` and get `[OFFER_VALUE]`; `[T&CS]` apply. |
| Odds boost | Event activation for engaged users | Recreational users with confirmed sport or event affinity | Sharp or arb-sensitive users, low-margin events | Drives event engagement with limited fixed value | Margin erosion, arb exposure | Boost terms must be clear | Boost cap, eligible market, max stake, minimum odds, expiry | Boost available on `[TARGET_EVENT]` up to `[MAX_STAKE]`; `[T&CS]` apply. |
| Accumulator insurance | Retention for accumulator-preferring users | Users with confirmed accumulator preference | Single-bet users, sharp or bonus abuse risk | Encourages target bet type | Cost can rise if broad | Must not imply bet is safe | Minimum legs, minimum odds per leg, max refund, eligible markets | Get stake back up to `[OFFER_VALUE]` if qualifying accumulator meets `[T&CS]`. |
| Cashback | Retention with capped downside | Recreational users with steady activity | Users selected due to losses, high RG risk | Flexible value and easy concept | Can reward loss-heavy behaviour if poorly targeted | High RG sensitivity; never base on recent heavy losses | Cap, qualifying period, eligible markets, exclude loss-triggered targeting | Get `[OFFER_VALUE]` cashback on eligible settled bets; `[T&CS]` apply. |
| Bet builder boost | Event activation for bet builder users | Users with confirmed bet builder usage | Users unfamiliar with bet builder, SMS-only complex journeys | Product engagement and differentiated value | Complexity and margin exposure | Must explain simply and avoid jargon | Eligible event, max stake, minimum odds, selection rules, expiry | Add a `[OFFER_VALUE]` boost to eligible bet builder bets on `[TARGET_EVENT]`; `[T&CS]` apply. |
| Deposit bonus | Activation or reload where appropriate | Users with deposit intent and low RG risk | RG-risk users, users with deposit stress signals | Funds betting wallet and can drive action | Bonus cost, abuse, wagering complexity | Must not pressure deposits or imply financial benefit | Deposit limit, bonus cap, eligible users, clear terms, expiry | Deposit `[MIN_DEPOSIT]` and receive `[OFFER_VALUE]` bonus for eligible bets; `[T&CS]` apply. |
| Reload offer | Retention for dormant or light users with safe profile | Users with controlled bonus history and valid consent | Recent heavy-loss users, RG-risk users, bonus abusers | Reactivates wallet activity | Can overpay churn-risk users without incrementality | Avoid manipulative win-back framing | Cap, frequency limit, eligible markets, expiry | Add funds and get `[OFFER_VALUE]` reload bonus; `[T&CS]` apply. |
| Mission/challenge | Engagement over a defined period | Recreational users who respond to goals | Users at risk of over-engagement or RG flags | Drives repeated target behaviour | Can increase frequency too much | High RG scrutiny for repeat-betting tasks | Low count, capped reward, safe timeframe, clear opt-out | Complete `[MISSION_ACTION]` to earn `[OFFER_VALUE]`; `[T&CS]` apply. |
| Loyalty points | Retention and softer value | Broad eligible users with ongoing activity | Users needing immediate simple value | Lower direct cost and long-term engagement | Low perceived value | Must not pressure excessive play | Earning cap, eligible actions, expiry, redemption rules | Earn `[OFFER_VALUE]` loyalty points on eligible bets; `[T&CS]` apply. |
| VIP bespoke offer | VIP engagement | High-value eligible users with managed account review | Unreviewed users, RG-risk users, sharp or arb-sensitive users | Personalised value and relationship management | High cost and margin exposure | Requires enhanced review | Manual approval, cap, eligibility, expiry, monitoring | Your bespoke `[OFFER_MECHANIC]` is available for `[TARGET_EVENT]`; `[T&CS]` apply. |
| Event-specific voucher | Event activation | Users with confirmed event affinity | Users with no event interest | Fixed cost and clear event hook | Low uptake if event relevance weak | Must avoid pressure around event timing | Voucher cap, event eligibility, expiry, one per customer | Claim `[OFFER_VALUE]` voucher for eligible bets on `[TARGET_EVENT]`; `[T&CS]` apply. |
| Personalised stake-back offer | Retention or reactivation with capped value | Users with known stake band and safe profile | Recent heavy-loss users, RG-risk users, bonus abusers | Aligns value to normal stake | Can be seen as loss-linked if framed poorly | Must not reference losses | Stake cap based on safe value band, eligible markets, expiry | Get stake back up to `[OFFER_VALUE]` on eligible `[TARGET_EVENT]` bet; `[T&CS]` apply. |

## Output Template

```markdown
## Offer Mechanics Recommendation

### Recommended Mechanic
- [RECOMMENDATION] [OFFER_MECHANIC]:
- [CONFIRMED] [OFFER_VALUE]:
- [CONFIRMED] Objective:

### Suitability
- Segment fit:
- Weak fit:
- Commercial benefit:
- Commercial risk:
- RG/compliance risk:

### Recommended Constraints
- Minimum odds:
- Minimum stake:
- Max bonus value:
- Eligible markets:
- Expiry:
- Suppressions:

### Example Structure
- [OFFER_MECHANIC] for `[TARGET_SEGMENT]` on `[TARGET_EVENT]`: `[OFFER_VALUE]`, subject to `[T&CS]`.
```

## Example User Request

Recommend the best `[OFFER_MECHANIC]` for `[TARGET_SEGMENT]` around `[TARGET_EVENT]` in `[TARGET_MARKET]`.

## Example Output

```markdown
## Offer Mechanics Recommendation

- [RECOMMENDATION] Use `[OFFER_MECHANIC]` because it fits `[TARGET_SEGMENT]` and keeps exposure capped.
- [NEEDS CONFIRMATION] Confirm `[OFFER_VALUE]`, minimum odds, minimum stake, max bonus value, eligible markets, expiry, and `[T&CS]`.
- [RISK] Exclude RG-risk, self-excluded, bonus abuse risk, and sharp or arb-sensitive users where the mechanic is exploitable.
- Example: `[OFFER_MECHANIC]` worth `[OFFER_VALUE]` for eligible bets on `[TARGET_EVENT]`; `[T&CS]` apply.
```

