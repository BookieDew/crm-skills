---
name: crm-sportsbook-offer-mechanics
description: Designs, selects, evaluates, and refines market-agnostic sportsbook CRM offer mechanics with segment fit, event and channel suitability, commercial exposure controls, responsible-gaming safeguards, and clear constraints.
---

# CRM Sportsbook Offer Mechanics

## Purpose

This skill helps CRM teams design commercially realistic, customer-friendly, responsible-gaming-aware sportsbook offer mechanics.

It helps the CRM team decide:

- Which offer mechanic best fits `[CAMPAIGN_OBJECTIVE]`.
- Which mechanic best fits `[TARGET_SEGMENT]`.
- Which mechanic best fits `[TARGET_SPORT]`, `[TARGET_EVENT]`, `[TARGET_CHANNEL]`, and product context.
- Which constraints are needed to protect margin and bonus cost.
- Which risks need review before launch.
- Which alternative mechanics may be safer, cheaper, clearer, or more effective.

This skill creates the offer design layer. It does not write final customer-facing copy or create a full campaign brief by itself.

## Role in the Skill Pack

This skill usually runs after:

- `crm-sportsbook-market-context`
- `crm-sportsbook-event-opportunity`, if the campaign is event-led.
- `crm-sportsbook-player-segmentation`

It may be selected by `crm-sportsbook-skill-router` when the user asks for offer ideas, offer comparison, offer improvement, commercial risk reduction, or offer constraints.

It translates market, event, segment, and objective inputs into a practical offer structure.

It informs:

- Campaign brief.
- SMS copy direction.
- Localisation.
- RG/compliance review.
- Journey builder.
- A/B testing.
- Post-campaign analysis.

It should not write final campaign copy or the full campaign brief by itself. It should produce the offer recommendation, structure, rationale, constraints, risks, and next-skill guidance that downstream skills can use.

## When to Use

Use this skill when the CRM manager needs to:

- Create sportsbook offer ideas.
- Choose the best mechanic for `[TARGET_SEGMENT]`.
- Improve an existing offer.
- Compare several offer mechanics.
- Design qualification rules.
- Define `[MINIMUM_STAKE]`, `[MINIMUM_ODDS]`, `[EXPIRY]`, `[MAX_BONUS_VALUE]`, and `[ELIGIBLE_MARKETS]`.
- Reduce bonus abuse risk.
- Reduce margin exposure.
- Make an offer simpler for SMS.
- Adapt an offer to `[TARGET_SPORT]`, `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, or `[TARGET_FIXTURE]`.
- Create safer alternatives to an aggressive offer.
- Evaluate whether an offer is commercially sensible and responsible-gaming safe.
- Prepare offer logic for campaign brief creation.

## When Not to Use

Do not use this skill to:

- Write final SMS copy.
- Build the full campaign brief.
- Create market context from scratch.
- Define the player segment from scratch.
- Perform final legal approval.
- Analyse campaign results after launch.
- Override responsible-gaming suppressions.
- Invent local market facts.
- Create offers based on chasing losses or risky behaviour.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Event opportunity: `crm-sportsbook-event-opportunity`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- SMS copy: `crm-sportsbook-sms-copy`.
- Localisation: `crm-sportsbook-localisation`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_MARKET]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]` or segmentation output.
- `[OFFER_MECHANIC]` if already selected, or a request for recommendation.

### Recommended inputs

- `[TARGET_LANGUAGE]`
- `[TARGET_SPORT]`
- `[TARGET_EVENT]`
- `[TARGET_TOURNAMENT]`
- `[TARGET_FIXTURE]`
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[CUSTOMER_VALUE_SEGMENT]`
- `[PREFERRED_BET_TYPE]`
- `[PRE_MATCH_OR_LIVE_PREFERENCE]`
- `[SINGLE_OR_ACCUMULATOR_PREFERENCE]`
- `[VIP_STATUS]`
- `[BONUS_SENSITIVITY]`
- `[SHARP_OR_ARB_RISK]`
- `[CHURN_RISK]`
- `[OFFER_VALUE]`
- Budget limit supplied at runtime.
- Expected segment size supplied at runtime.
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`

### Advanced optional inputs

- Historical offer performance.
- Bonus cost history.
- Bonus abuse data.
- Margin by sport.
- Margin by market type.
- Player value model.
- Expected incremental value.
- GGR target.
- NGR target.
- Turnover target.
- Competitor offer examples supplied by the user.
- Product availability.
- Eligible sports or markets.
- Odds ladder or pricing constraints.
- Minimum odds policy.
- Minimum stake policy.
- Maximum exposure limits.
- Free bet rules.
- Cashback rules.
- VIP offer rules.
- Legal or compliance limitations supplied at runtime.
- Payment or deposit behaviour, if supplied by the user.
- Previous campaign results.
- Control group requirement.

## Output

The skill should produce:

- Offer mechanics recommendation.
- Confirmed inputs.
- Working assumptions.
- Items needing confirmation.
- Recommended mechanic.
- Offer structure.
- Qualification rules.
- Reward rules.
- Suggested constraints.
- Commercial rationale.
- Customer value proposition.
- Segment fit.
- Channel fit.
- RG/compliance risks.
- Commercial risks.
- UX clarity risks.
- Lower-cost alternative.
- Higher-impact alternative.
- Recommended next skills.

## Workflow

1. Identify `[CAMPAIGN_OBJECTIVE]`.
2. Load and apply `crm-sportsbook-shared-principles`.
3. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
4. Use `crm-sportsbook-market-context` output when available.
5. Use `crm-sportsbook-event-opportunity` output when the campaign is tied to `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, `[TARGET_FIXTURE]`, or `[TARGET_SPORT]`.
6. Identify `[TARGET_SEGMENT]` and use `crm-sportsbook-player-segmentation` output when available.
7. Identify `[TARGET_CHANNEL]`.
8. List all confirmed offer inputs as `[CONFIRMED]`.
9. Separate confirmed facts from assumptions.
10. Mark missing offer, product, market, segment, or compliance details as `[NEEDS CONFIRMATION]`.
11. Check mandatory suppression and RG constraints from shared principles.
12. Determine whether `[OFFER_MECHANIC]` has already been selected.
13. If no mechanic is selected, recommend the best-fit mechanic based on:
    - `[CAMPAIGN_OBJECTIVE]`
    - `[TARGET_SEGMENT]`
    - `[TARGET_CHANNEL]`
    - `[TARGET_SPORT]` or `[TARGET_EVENT]` relevance.
    - Commercial exposure.
    - Bonus abuse risk.
    - UX simplicity.
    - RG/compliance safety.
14. Define the offer structure:
    - Qualification action.
    - Reward.
    - `[MINIMUM_STAKE]`
    - `[MINIMUM_ODDS]`
    - `[ELIGIBLE_MARKETS]`
    - `[EXPIRY]`
    - `[MAX_BONUS_VALUE]`
    - Exclusions.
    - `[T&CS]` notes.
15. Check whether the mechanic is simple enough for `[TARGET_CHANNEL]`.
16. Identify commercial risks.
17. Identify responsible-gaming and compliance risks.
18. Provide lower-cost and higher-impact alternatives.
19. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[CAMPAIGN_OBJECTIVE]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_SEGMENT]` is missing, recommend running `crm-sportsbook-player-segmentation`.
- If `[TARGET_CHANNEL]` is missing, provide channel-neutral offer guidance and mark channel suitability as `[NEEDS CONFIRMATION]`.
- If `[TARGET_CHANNEL]` is SMS, prefer simple mechanics that can be explained in one short message.
- If the offer mechanic cannot be explained clearly in SMS, recommend simplifying it or moving details to `[T&CS]` or a support page.
- If `[CAMPAIGN_OBJECTIVE]` is activation, prefer simple first-action mechanics.
- If `[CAMPAIGN_OBJECTIVE]` is retention, avoid over-incentivising users who would likely bet anyway.
- If `[CAMPAIGN_OBJECTIVE]` is reactivation, avoid emotional pressure and exclude users with recent heavy-loss or RG-risk signals.
- If the campaign is event-led, match the mechanic to event relevance and player interest.
- If `[CAMPAIGN_OBJECTIVE]` is VIP engagement, allow richer value only with manual review and exposure caps.
- If `[BONUS_SENSITIVITY]` is high, use tighter qualification rules and lower-exposure mechanics.
- If `[SHARP_OR_ARB_RISK]` is present, recommend exclusion, low-value mechanics, restricted `[ELIGIBLE_MARKETS]`, or manual approval.
- If `[TARGET_SEGMENT]` is broad recreational, use simple mechanics with clear caps.
- If the offer has open-ended exposure, add `[MAX_BONUS_VALUE]` or other caps.
- If the offer depends on market availability, odds, product availability, or settlement logic, mark those items as `[NEEDS CONFIRMATION]`.
- If the offer uses "risk-free" wording, flag it as `[RISK]` unless explicitly approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- If the offer encourages chasing losses, reject or redesign the mechanic.
- If the offer targets users because of recent losses, mark it as `[RISK]` and recommend suppression or redesign.
- If `[T&CS]` are too complex for `[TARGET_CHANNEL]`, recommend a simpler mechanic or clearer support page.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, `crm-sportsbook-market-context`, `crm-sportsbook-event-opportunity` when event-led, and `crm-sportsbook-player-segmentation`.
- Normally run after this skill: `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, `crm-sportsbook-ab-testing`, and `crm-sportsbook-post-campaign-analysis`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, offer mechanic safety rules, channel communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Sport preference.
- Event relevance.
- Bet type preference.
- Pre-match versus live betting.
- Single versus accumulator preference.
- Odds boost suitability.
- Free bet suitability.
- Cashback suitability.
- Bet builder suitability.
- Deposit behaviour.
- Bonus history.
- Bonus sensitivity.
- VIP status.
- Recreational versus sharp behaviour.
- Arb-sensitive users.
- Churn risk.
- Stake level.
- Margin protection.
- Event timing.
- Bonus abuse risk.
- Product availability.
- Settlement rules.
- Eligible market availability.
- Channel clarity.
- Frequency caps.
- Control group needs.

## Supported Offer Mechanics

Use the following mechanics as the core sportsbook offer menu. Do not assume any mechanic is locally permitted or product-supported unless confirmed by the user, internal policy, `[REGULATORY_NOTES]`, `[T&CS]`, or approved research.

### Free Bet

- Description: A capped bonus bet or token issued after eligibility, opt-in, or a qualifying action.
- Best use case: Activation, reactivation, event engagement, or reward mechanics where bonus cost can be capped.
- Best segment fit: Eligible customers with safe RG profile, clear customer value band, and no high bonus-abuse or sharp/arb risk.
- Weak segment fit: Bonus-abuse risk users, sharp or arb-sensitive users, already highly active users with low incrementality, and users with RG risk.
- Commercial benefit: Clear perceived value with controllable max exposure.
- Commercial risk: Bonus cost without incremental betting; misuse if eligibility is too broad.
- RG/compliance risk: Can pressure reactivation users if framed as an urgent reason to return.
- Recommended constraints: `[MAX_BONUS_VALUE]`, `[MINIMUM_ODDS]`, `[ELIGIBLE_MARKETS]`, `[EXPIRY]`, one use per eligible customer, suppression rules, and clear `[T&CS]`.
- Channel suitability: Strong for SMS if the value, action, and CTA are simple.
- Example structure: `[OFFER_MECHANIC]` worth `[OFFER_VALUE]` for eligible customers in `[TARGET_SEGMENT]` on `[TARGET_SPORT]` or `[TARGET_EVENT]`; `[T&CS]` apply.

### Bet-and-Get

- Description: A customer completes a qualifying bet action before receiving `[OFFER_VALUE]`.
- Best use case: Activation, retention, or event activation where the CRM team wants action before reward.
- Best segment fit: Customers with confirmed eligibility and reasonable intent for `[TARGET_SPORT]`, `[TARGET_EVENT]`, or `[PREFERRED_BET_TYPE]`.
- Weak segment fit: Low-intent users, users with unclear event relevance, users who need extensive explanation, and users with RG or bonus-abuse risk.
- Commercial benefit: Reward is issued only after a qualifying action.
- Commercial risk: Can overpay customers who would likely bet anyway.
- RG/compliance risk: Qualification language may create pressure if the time window is aggressive.
- Recommended constraints: `[MINIMUM_STAKE]`, `[MINIMUM_ODDS]`, `[MAX_BONUS_VALUE]`, `[ELIGIBLE_MARKETS]`, clear qualifying window, reward issue timing, and one reward per eligible customer.
- Channel suitability: Good for SMS only when the qualification and reward fit in one sentence.
- Example structure: Place a qualifying bet of `[MINIMUM_STAKE]` at `[MINIMUM_ODDS]` on `[TARGET_EVENT]` and receive `[OFFER_VALUE]`; `[T&CS]` apply.

### Odds Boost

- Description: A controlled price enhancement on selected eligible markets, events, or bet types.
- Best use case: Event engagement, perceived value, or market excitement with controlled exposure.
- Best segment fit: Recreational customers with confirmed interest in `[TARGET_SPORT]`, `[TARGET_EVENT]`, or eligible bet types.
- Weak segment fit: Sharp or arb-sensitive users, high-stake users without caps, and users with unclear product relevance.
- Commercial benefit: Can drive event engagement without issuing a broad bonus credit.
- Commercial risk: Margin erosion, pricing exposure, and arbitrage sensitivity.
- RG/compliance risk: Boost terms can mislead if not clear; wording must not imply certainty of winning.
- Recommended constraints: Max qualifying stake, boost cap, eligible market, `[MINIMUM_ODDS]`, `[EXPIRY]`, exclusion of restricted users, and operational approval.
- Channel suitability: Good for SMS when one boost is promoted clearly; poor if multiple boosted selections need explanation.
- Example structure: Eligible customers can use `[OFFER_MECHANIC]` on `[TARGET_EVENT]` up to `[MAX_BONUS_VALUE]` exposure; `[T&CS]` apply.

### Accumulator Insurance

- Description: A capped refund, bonus, or stake-back mechanic for qualifying accumulator bets that meet defined conditions.
- Best use case: Accumulator-oriented segments where the product wants to encourage a multi-leg bet type with capped refund exposure.
- Best segment fit: Customers with confirmed `[SINGLE_OR_ACCUMULATOR_PREFERENCE]` showing accumulator interest and safe engagement profile.
- Weak segment fit: Single-bet users, low-engagement users, users with RG risk, and sharp or bonus-abuse risk users.
- Commercial benefit: Encourages a specific bet type and can lift turnover where accumulator preference is confirmed.
- Commercial risk: Refund exposure, customer confusion, and over-incentivising complex betting behaviour.
- RG/compliance risk: Must not imply the bet is safe or loss-free; avoid encouraging excessive leg counts.
- Recommended constraints: Minimum legs, `[MINIMUM_ODDS]` per leg or total odds, `[MAX_BONUS_VALUE]`, `[ELIGIBLE_MARKETS]`, clear settlement rules, and frequency caps.
- Channel suitability: Often too complex for SMS unless the rule is very simple and `[T&CS]` carry the detail.
- Example structure: Qualifying accumulator bets on `[TARGET_SPORT]` may receive stake back up to `[OFFER_VALUE]` if all `[T&CS]` conditions are met.

### Cashback

- Description: A capped promotional return on eligible settled bets or qualifying activity.
- Best use case: Carefully controlled retention or structured return mechanics where the trigger is not based on recent heavy losses.
- Best segment fit: Eligible recreational users with stable engagement, low RG risk, and clear segment value.
- Weak segment fit: Recently heavy-losing users, RG-risk users, bonus abusers, and users selected because of loss behaviour.
- Commercial benefit: Flexible perceived value that can be capped and targeted.
- Commercial risk: Can reward unprofitable behaviour or become expensive if qualification is broad.
- RG/compliance risk: High sensitivity if framed as recovery from losses or targeted based on loss patterns.
- Recommended constraints: `[MAX_BONUS_VALUE]`, eligible bets, qualifying window, reward type, customer eligibility, suppression rules, and clear calculation method.
- Channel suitability: Usable in SMS only if the concept is short, capped, and not loss-framed.
- Example structure: Eligible customers in `[TARGET_SEGMENT]` can receive `[OFFER_VALUE]` cashback on qualifying activity in `[ELIGIBLE_MARKETS]`; `[T&CS]` apply.

### Bet Builder Boost

- Description: A controlled boost or voucher for eligible bet builder activity.
- Best use case: Product engagement for users with confirmed bet builder interest and event relevance.
- Best segment fit: Customers with confirmed bet builder usage or clear product eligibility for `[TARGET_EVENT]`.
- Weak segment fit: Users unfamiliar with bet builder, SMS-only campaigns requiring complex education, and sharp or arb-sensitive users.
- Commercial benefit: Drives engagement with a specific product feature.
- Commercial risk: Margin exposure, complexity, settlement disputes, and combinability issues.
- RG/compliance risk: Complexity may mislead if qualification or settlement rules are unclear.
- Recommended constraints: Product availability, eligible event, eligible markets, max stake, max boost, `[MINIMUM_ODDS]`, settlement rules, and one use per customer.
- Channel suitability: Good for SMS only when the product and boost are familiar to `[TARGET_SEGMENT]`; otherwise use a richer support channel.
- Example structure: Use `[OFFER_MECHANIC]` on eligible bet builder bets for `[TARGET_EVENT]` up to `[OFFER_VALUE]`; `[T&CS]` apply.

### Deposit Bonus

- Description: A capped bonus linked to a qualifying deposit and eligible betting activity.
- Best use case: Activation or reload campaigns only when deposit incentives are appropriate, permitted, and compliant.
- Best segment fit: Eligible users with safe RG profile, confirmed deposit intent or activation need, and no financial stress indicators.
- Weak segment fit: RG-risk users, users with cooling-off restrictions, users with deposit stress signals, and bonus-abuse risk users.
- Commercial benefit: Can support first-action or reload objectives when incrementality is credible.
- Commercial risk: Bonus cost, wagering complexity, abuse risk, and low incrementality if targeted too broadly.
- RG/compliance risk: Must not imply betting solves financial problems or pressure customers to deposit.
- Recommended constraints: Deposit minimum supplied at runtime, bonus percentage or value supplied at runtime, `[MAX_BONUS_VALUE]`, `[MINIMUM_ODDS]`, `[ELIGIBLE_MARKETS]`, `[EXPIRY]`, frequency caps, and clear `[T&CS]`.
- Channel suitability: Use SMS only if the deposit action and bonus cap are simple and not high pressure.
- Example structure: Eligible customers in `[TARGET_SEGMENT]` who complete the qualifying deposit action receive `[OFFER_VALUE]` for eligible bets; `[T&CS]` apply.

### Reload Offer

- Description: A deposit-related or wallet activity incentive for eligible active or lapsing customers.
- Best use case: Retention or controlled re-engagement where deposit behaviour and incrementality support the incentive.
- Best segment fit: Eligible active or lapsing users with safe RG profile, controlled bonus history, and valid channel consent.
- Weak segment fit: Recently heavy-losing users, RG-risk users, bonus abusers, and customers who would likely deposit without incentive.
- Commercial benefit: Can restore wallet activity or support event engagement.
- Commercial risk: Low incrementality, repeated bonus dependency, and deposit pressure.
- RG/compliance risk: Must avoid manipulative win-back framing and financial-pressure messaging.
- Recommended constraints: `[MAX_BONUS_VALUE]`, deposit or action threshold supplied at runtime, frequency cap, `[EXPIRY]`, `[ELIGIBLE_MARKETS]`, and suppression rules.
- Channel suitability: SMS can work only if the offer is simple and the tone is neutral.
- Example structure: Eligible `[TARGET_SEGMENT]` customers can receive `[OFFER_VALUE]` reload value for qualifying activity before `[EXPIRY]`; `[T&CS]` apply.

### Mission or Challenge

- Description: A multi-step or goal-based mechanic where customers complete defined qualifying actions to earn a reward.
- Best use case: Engagement journeys or product education where actions are limited, clear, and RG-safe.
- Best segment fit: Recreational users with stable engagement and clear product familiarity.
- Weak segment fit: Users with RG risk, low-engagement users, reactivation users sensitive to pressure, and users who may over-engage.
- Commercial benefit: Can focus behaviour on target products or events and pace reward cost.
- Commercial risk: Complexity, fatigue, repeated reward cost, and operational tracking issues.
- RG/compliance risk: Can encourage excessive frequency or grind-style behaviour if not tightly limited.
- Recommended constraints: Low action count, capped reward, safe timeframe, clear progress logic, `[MAX_BONUS_VALUE]`, opt-out path, and frequency caps.
- Channel suitability: Usually poor for SMS unless it is a single simple challenge; better suited to channels with room for explanation.
- Example structure: Complete the qualifying action linked to `[TARGET_SPORT]` or `[TARGET_EVENT]` to earn `[OFFER_VALUE]`; `[T&CS]` apply.

### Loyalty Points

- Description: A points-based reward mechanic for eligible activity, redemption, or retention.
- Best use case: Softer retention, lower-cost engagement, or non-urgent relationship building.
- Best segment fit: Broad eligible customers with ongoing activity and low RG risk.
- Weak segment fit: Users needing immediate simple value, users who do not understand point value, and users with RG restrictions.
- Commercial benefit: Can reduce direct bonus cost and support longer-term engagement.
- Commercial risk: Low perceived value, point liability, and unclear redemption cost.
- RG/compliance risk: Earning rules must not encourage excessive play or hidden value claims.
- Recommended constraints: Earning cap, redemption rules, point value clarity, `[EXPIRY]`, eligible actions, and frequency controls.
- Channel suitability: SMS only if point value and next action are clear; otherwise use a channel with more explanation.
- Example structure: Earn `[OFFER_VALUE]` loyalty points for eligible activity on `[TARGET_SPORT]` or `[TARGET_EVENT]`; `[T&CS]` apply.

### VIP Bespoke Offer

- Description: A personalised high-touch offer for approved VIP engagement.
- Best use case: Relationship-managed VIP engagement where customer value, RG profile, and commercial exposure are manually reviewed.
- Best segment fit: Confirmed `[VIP_STATUS]` users with safe engagement profile and approved value limits.
- Weak segment fit: Unreviewed users, RG-risk users, sharp or arb-sensitive users, and customers whose value comes from risky behaviour.
- Commercial benefit: Can support retention and relationship quality for high-value customers.
- Commercial risk: High cost, margin exposure, inconsistent treatment, and manual process risk.
- RG/compliance risk: Requires enhanced review because high value can mask harm risk.
- Recommended constraints: Manual approval, `[MAX_BONUS_VALUE]`, customer value check, RG check, eligible activity, `[EXPIRY]`, frequency controls, and monitoring.
- Channel suitability: Prefer VIP manager outreach or controlled inbox; SMS only if approved and concise.
- Example structure: Approved `[VIP_STATUS]` customers may receive `[OFFER_MECHANIC]` worth `[OFFER_VALUE]` for `[TARGET_EVENT]`; `[T&CS]` apply.

### Event-Specific Voucher

- Description: A capped reward or voucher tied to `[TARGET_EVENT]`, `[TARGET_SPORT]`, `[TARGET_TOURNAMENT]`, or `[TARGET_FIXTURE]`.
- Best use case: Event-led activation where the event hook is confirmed and the reward is fixed.
- Best segment fit: Customers with confirmed event, sport, product, or betting interest and valid channel eligibility.
- Weak segment fit: Users with no confirmed event relevance, users with RG risk, and users where event interest is inferred too aggressively.
- Commercial benefit: Fixed cost, clear event hook, and strong fit for calendar-led CRM.
- Commercial risk: Low uptake if event relevance is weak; operational risk if event details change.
- RG/compliance risk: Event timing must not create pressure or misleading urgency.
- Recommended constraints: `[MAX_BONUS_VALUE]`, event eligibility, `[ELIGIBLE_MARKETS]`, `[EXPIRY]`, product availability, one use per customer, and suppression rules.
- Channel suitability: Strong for SMS when the event and voucher value are simple.
- Example structure: Eligible `[TARGET_SEGMENT]` customers can claim `[OFFER_VALUE]` voucher for `[TARGET_EVENT]`; `[T&CS]` apply.

### Personalised Stake-Back Offer

- Description: A capped stake-back mechanic aligned to eligible activity and safe customer value bands.
- Best use case: Carefully controlled retention or reactivation where a capped stake-back value creates a clear value proposition without "risk-free" wording.
- Best segment fit: Users with known stake band, safe RG profile, and no recent heavy-loss or bonus-abuse signals.
- Weak segment fit: Recently heavy-losing users, RG-risk users, bonus abusers, sharp or arb-sensitive users, and customers with unstable stake behaviour.
- Commercial benefit: Can align reward exposure to normal stake behaviour.
- Commercial risk: Can become expensive or exploitable if caps and eligible markets are weak.
- RG/compliance risk: High sensitivity if framed as protection from loss or "risk-free".
- Recommended constraints: `[MAX_BONUS_VALUE]`, qualifying stake cap, `[MINIMUM_ODDS]`, `[ELIGIBLE_MARKETS]`, reward type, `[EXPIRY]`, and suppression rules.
- Channel suitability: SMS-suitable only with simple, non-loss-framed wording and clear `[T&CS]`.
- Example structure: Eligible customers can receive stake back up to `[OFFER_VALUE]` on a qualifying bet for `[TARGET_EVENT]`; `[T&CS]` apply.

## Segment-to-Mechanic Fit

Use this guidance to match mechanics to `[TARGET_SEGMENT]`. Treat every fit as provisional unless backed by segmentation data.

### Newly Registered / No Deposit

Potential fit:

- Deposit bonus.
- First-action free bet.
- Simple bet-and-get.

Avoid:

- Complex missions.
- High-pressure urgency.
- VIP-style value.

### Deposited / No Bet

Potential fit:

- First-bet free bet.
- Bet-and-get.
- Event-specific voucher.

Avoid:

- Complex accumulator insurance.
- Heavy reload offers.
- Any mechanic that requires advanced product knowledge.

### Active Recreational Users

Potential fit:

- Odds boost.
- Free bet.
- Loyalty points.
- Event-specific voucher.

Avoid:

- Over-incentivising frequent natural bettors.
- Complex mechanics where customer value is unclear.

### Accumulator Users

Potential fit:

- Accumulator insurance.
- Accumulator-focused bet-and-get.
- Capped free bet linked to qualifying accumulator activity.

Avoid:

- Mechanics that encourage excessive leg counts without controls.
- Broad refund exposure.

### Live Bettors

Potential fit:

- Event-specific odds boost.
- Live-betting token, if product support is confirmed at runtime.

Avoid:

- Timing-sensitive SMS that may arrive too late.
- Mechanics dependent on unstable in-play availability.
- Offers that create pressure during short decision windows.

### Bet Builder Users

Potential fit:

- Bet builder boost.
- Event-specific bet builder voucher.

Avoid:

- Generic offers that do not reflect confirmed product use.
- Mechanics requiring long explanation in SMS.

### Dormant / Reactivation Users

Potential fit:

- Simple capped free bet.
- Simple bet-and-get.
- Soft event-led voucher.

Avoid:

- Emotional pressure.
- Loss-recovery framing.
- Recently heavy-losing users.
- Aggressive expiry language.

### VIP Users

Potential fit:

- VIP bespoke offer.
- Higher-value capped free bet.
- Personalised event voucher.

Avoid:

- Fully automated high-value offers without review.
- Users with RG risk.
- Open-ended exposure.

### Bonus-Sensitive Users

Potential fit:

- Lower-value capped offers.
- Loyalty points.
- Restricted eligibility offers.

Avoid:

- Rich, broad, easy-to-abuse offers.
- Uncapped cashback.
- High-value boosts without controls.

### Sharp / Arb-Sensitive Users

Potential fit:

- Exclusion.
- Low-exposure offers.
- Manual approval only.

Avoid:

- Odds boosts with exploitable pricing.
- Broad free bets.
- High-value cashback.
- Weak eligible-market restrictions.

## Campaign Objective-to-Mechanic Fit

### Activation

Prioritise:

- First-action free bet.
- Bet-and-get.
- Deposit bonus, if appropriate and approved.
- Event-specific voucher.

### Retention

Prioritise:

- Odds boost.
- Loyalty points.
- Event-led free bet.
- Low-cost personalised reward.

Avoid:

- Over-incentivising customers with strong natural activity.
- Rich offers without incrementality logic.

### Reactivation

Prioritise:

- Simple capped free bet.
- Soft event-led bet-and-get.
- Low-pressure voucher.

Avoid:

- Loss recovery language.
- Aggressive expiry.
- Heavy deposit pressure.
- Users with recent heavy-loss or RG-risk indicators.

### Event Activation

Prioritise:

- Odds boost.
- Event-specific voucher.
- Bet builder boost.
- Free bet.
- Accumulator insurance, if segment fit is strong.

### Cross-Sell Within Sportsbook

Prioritise:

- Product-specific voucher.
- Bet builder boost.
- Free bet for eligible new sport or product use.
- Low-risk mission.

Avoid:

- Complex mechanics for low-engagement users.
- Product nudges without RG and product-suitability review.

### VIP Engagement

Prioritise:

- Bespoke reward.
- Personalised event offer.
- Higher-value capped mechanic.

Require:

- Manual review.
- RG check.
- Exposure cap.
- Clear commercial rationale.

## Market-Agnostic Design Rules

The skill must never assume:

- Local sport preferences.
- Local betting habits.
- Local channel preferences.
- Local language.
- Local payment methods.
- Local regulations.
- Local cultural tone.
- Local competitor behaviour.
- Local player value thresholds.
- Local bonus rules.
- Current event schedules.
- Product availability in `[TARGET_MARKET]`.

All offer-specific and market-specific details must come from:

- User-provided inputs.
- Internal data.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts. Do not invent hard market facts.

## Channel-Aware Design Rules

The skill should consider `[TARGET_CHANNEL]` if supplied.

For SMS:

- Prefer mechanics that can be explained in one sentence.
- Avoid multi-step mechanics unless very simple.
- Recommend short qualification language.
- Recommend clear CTA.
- Recommend `[T&CS]` link or short `[T&CS]` cue.
- Flag complex `[T&CS]` as UX risk.
- Avoid aggressive urgency.
- Feed into `crm-sportsbook-sms-copy`.

For email:

- Note that detailed email execution should be handled by a future email-specific skill.
- Email may support more explanation, but this skill should still keep the offer mechanic clear.

For push:

- Note that detailed push execution should be handled by a future push-specific skill.
- Push should only use very simple mechanics.

For onsite/inbox:

- Consider whether supporting explanation is needed.
- Consider whether the offer needs logged-in visibility, banner support, or inbox detail.

For VIP outreach:

- Recommend manual review and careful tone.
- Avoid automated pressure based on value or inactivity alone.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag or reject offer mechanics that:

- Target self-excluded users.
- Target users with RG risk flags.
- Target users in cooling-off periods.
- Encourage chasing losses.
- Frame the offer as a way to recover losses.
- Use recent losses as the reason for the incentive.
- Imply guaranteed profit.
- Imply betting can solve financial problems.
- Use "risk-free" unless approved in `[REGULATORY_NOTES]` and `[T&CS]`.
- Hide important restrictions.
- Use aggressive pressure or manipulative urgency.
- Encourage excessive bet frequency.
- Encourage excessive accumulator leg counts without controls.
- Push inactive users with emotionally manipulative wording.

The skill must recommend suppression checks before campaign brief or copy creation.

## Commercial Guardrails

The skill should protect against:

- Excessive bonus cost.
- Open-ended exposure.
- Bonus abuse.
- Arbitrage exploitation.
- Sharp-player exploitation.
- Low incrementality.
- Over-incentivising natural activity.
- High VIP cost without review.
- Ineligible market settlement issues.
- Operational risk.
- Unclear qualification rules.
- Unclear reward rules.
- `[T&CS]` complexity.

The skill should recommend constraints such as:

- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- Maximum qualifying stake supplied at runtime.
- Eligible sports.
- `[ELIGIBLE_MARKETS]`
- `[EXPIRY]`
- One use per customer.
- Segment restrictions.
- Exclusion of restricted users.
- Manual review for VIP or high-value users.
- Control group for incrementality testing.

Do not estimate commercial impact unless data is provided or the user explicitly asks for assumptions.

## Brand & UX Guardrails

The skill should help the CRM team understand:

- Whether the offer can be explained clearly.
- Whether the value proposition is obvious.
- Whether the mechanic feels fair.
- Whether the offer sounds too complicated.
- Whether the offer creates customer confusion.
- Whether the copy may become misleading.
- Whether the offer relies too heavily on `[T&CS]`.
- Whether the personalisation may feel invasive.
- Whether the offer feels spammy or overly aggressive.

Do not stereotype `[TARGET_MARKET]`. Do not imply certainty of winning. Do not use fake personalisation.

## Assumption Labels

Use these labels consistently:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important detail that should be checked before launch.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

## Output Template

Use this response format when the skill is activated:

```markdown
# Offer Mechanics Output

## 1. Offer Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Proposed mechanic: [OFFER_MECHANIC]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Recommended Offer Mechanic
- Mechanic name:
- Why this mechanic fits:
- Best-fit segment:
- Campaign objective fit:
- Channel fit:
- Customer value:
- Commercial rationale:

## 6. Offer Structure
- Qualification action:
- Reward:
- Minimum stake: [MINIMUM_STAKE]
- Minimum odds: [MINIMUM_ODDS]
- Eligible sports/markets: [TARGET_SPORT] / [ELIGIBLE_MARKETS]
- Expiry: [EXPIRY]
- Max bonus/reward: [MAX_BONUS_VALUE]
- Usage limits:
- Exclusions:
- T&C notes: [T&CS]

## 7. Customer Value Proposition
- Simple customer-language explanation:
- Do not write final SMS copy unless explicitly requested.

## 8. Commercial Rationale
- Incrementality:
- Cost control:
- Margin protection:
- Abuse prevention:
- Segment fit:

## 9. Lower-Cost Alternative
- Mechanic:
- Why it may be safer:
- Trade-off:

## 10. Higher-Impact Alternative
- Mechanic:
- Why it may perform better:
- Additional risks or controls needed:

## 11. Segment-to-Offer Fit
- Strong fit / Usable with constraints / Weak fit / Not recommended:
- Rationale:

## 12. Channel Considerations
- [TARGET_CHANNEL]:
- SMS suitability if applicable:
- Complexity risk:
- Recommended simplification:

## 13. RG & Compliance Considerations
- [REGULATORY_NOTES]:
- [RISK]
- [RECOMMENDATION]

## 14. Commercial Risk Review
- Bonus cost risk:
- Abuse risk:
- Sharp/arb risk: [SHARP_OR_ARB_RISK]
- Margin risk:
- Low incrementality risk:
- Operational risk:

## 15. UX Clarity Review
- Clear / Clear with T&C support / Too complex for selected channel / Not recommended without simplification:
- Rationale:

## 16. Recommended Next Skills
- crm-sportsbook-campaign-brief
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 17. Launch Readiness
- Ready to proceed with assumptions / Needs offer constraints before campaign brief / Needs commercial approval before campaign brief / Needs RG/compliance input before campaign design / Not recommended based on current information
```

## Example User Request

"Recommend an offer mechanic for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The objective is `[CAMPAIGN_OBJECTIVE]`, the channel is `[TARGET_CHANNEL]`, and the campaign is linked to `[TARGET_EVENT]`."

## Example Output

```markdown
# Offer Mechanics Output

## 1. Offer Context
- Target market: [TARGET_MARKET]
- Language: [TARGET_LANGUAGE]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport/event: [TARGET_SPORT] / [TARGET_EVENT]
- Target tournament/fixture: [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Proposed mechanic: [OFFER_MECHANIC]

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Target segment: [TARGET_SEGMENT]
- [CONFIRMED] Event context: [TARGET_EVENT]

## 3. Working Assumptions
- [ASSUMPTION] No local offer rules, product availability, sport preference, event schedule, or customer value threshold is assumed unless supplied by the user or confirmed through approved research.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_TOURNAMENT]
- [NEEDS CONFIRMATION] [TARGET_FIXTURE]
- [NEEDS CONFIRMATION] [CUSTOMER_LIFECYCLE_STAGE]
- [NEEDS CONFIRMATION] [CUSTOMER_VALUE_SEGMENT]
- [NEEDS CONFIRMATION] [PREFERRED_BET_TYPE]
- [NEEDS CONFIRMATION] [PRE_MATCH_OR_LIVE_PREFERENCE]
- [NEEDS CONFIRMATION] [SINGLE_OR_ACCUMULATOR_PREFERENCE]
- [NEEDS CONFIRMATION] [VIP_STATUS]
- [NEEDS CONFIRMATION] [BONUS_SENSITIVITY]
- [NEEDS CONFIRMATION] [SHARP_OR_ARB_RISK]
- [NEEDS CONFIRMATION] [CHURN_RISK]
- [NEEDS CONFIRMATION] [OFFER_VALUE]
- [NEEDS CONFIRMATION] [MINIMUM_STAKE]
- [NEEDS CONFIRMATION] [MINIMUM_ODDS]
- [NEEDS CONFIRMATION] [MAX_BONUS_VALUE]
- [NEEDS CONFIRMATION] [EXPIRY]
- [NEEDS CONFIRMATION] [ELIGIBLE_MARKETS]
- [NEEDS CONFIRMATION] [T&CS]
- [NEEDS CONFIRMATION] [REGULATORY_NOTES]

## 5. Recommended Offer Mechanic
- Mechanic name: [OFFER_MECHANIC]
- Why this mechanic fits: [RECOMMENDATION] Use a simple, capped mechanic that can be explained clearly in [TARGET_CHANNEL] and aligned to [CAMPAIGN_OBJECTIVE].
- Best-fit segment: [TARGET_SEGMENT] with confirmed channel eligibility, no suppression flags, and confirmed relevance to [TARGET_EVENT] or [TARGET_SPORT].
- Campaign objective fit: [CAMPAIGN_OBJECTIVE]
- Channel fit: [RECOMMENDATION] If [TARGET_CHANNEL] is SMS, keep the qualification action and reward in one sentence.
- Customer value: [OFFER_VALUE]
- Commercial rationale: [RECOMMENDATION] Use [MAX_BONUS_VALUE], [MINIMUM_STAKE], [MINIMUM_ODDS], [ELIGIBLE_MARKETS], and [EXPIRY] to control exposure.

## 6. Offer Structure
- Qualification action: Eligible customer completes the approved qualifying action for [TARGET_EVENT] or [TARGET_SPORT].
- Reward: [OFFER_VALUE]
- Minimum stake: [MINIMUM_STAKE]
- Minimum odds: [MINIMUM_ODDS]
- Eligible sports/markets: [TARGET_SPORT] / [ELIGIBLE_MARKETS]
- Expiry: [EXPIRY]
- Max bonus/reward: [MAX_BONUS_VALUE]
- Usage limits: One use per eligible customer unless confirmed otherwise.
- Exclusions: Self-excluded users, RG-risk users, cooling-off users, channel opt-outs, restricted accounts, bonus-abuse risk users where relevant, and sharp or arb-sensitive users where the mechanic is exploitable.
- T&C notes: [T&CS]

## 7. Customer Value Proposition
- Simple customer-language explanation: Eligible customers can receive [OFFER_VALUE] when they complete the qualifying action for [TARGET_EVENT], subject to [T&CS].
- Do not write final SMS copy unless explicitly requested.

## 8. Commercial Rationale
- Incrementality: [NEEDS CONFIRMATION] Validate that [TARGET_SEGMENT] would not likely complete the action without incentive.
- Cost control: [RECOMMENDATION] Cap exposure with [MAX_BONUS_VALUE] and usage limits.
- Margin protection: [RECOMMENDATION] Confirm [MINIMUM_ODDS] and [ELIGIBLE_MARKETS].
- Abuse prevention: [RISK] Review [BONUS_SENSITIVITY] and [SHARP_OR_ARB_RISK].
- Segment fit: [NEEDS CONFIRMATION] Confirm customer value and event relevance.

## 9. Lower-Cost Alternative
- Mechanic: Loyalty points or lower-value capped [OFFER_MECHANIC].
- Why it may be safer: Lower direct bonus exposure and reduced abuse value.
- Trade-off: May reduce perceived customer value.

## 10. Higher-Impact Alternative
- Mechanic: Higher-value capped [OFFER_MECHANIC] or VIP bespoke offer for approved [VIP_STATUS] users.
- Why it may perform better: Greater perceived value for high-value eligible users.
- Additional risks or controls needed: Manual review, [MAX_BONUS_VALUE], RG check, and commercial approval.

## 11. Segment-to-Offer Fit
- Usable with constraints:
- Rationale: [TARGET_SEGMENT] needs confirmed value, bonus sensitivity, channel opt-in, suppression status, and event relevance before launch.

## 12. Channel Considerations
- [TARGET_CHANNEL]: [RECOMMENDATION] Match complexity to channel.
- SMS suitability if applicable: [RECOMMENDATION] Use only if the mechanic can be explained in one short sentence with clear [T&CS] reference.
- Complexity risk: [RISK] If qualification or reward rules require long explanation, simplify or use a richer support channel.
- Recommended simplification: One offer, one action, one reward, clear expiry.

## 13. RG & Compliance Considerations
- [REGULATORY_NOTES]: [NEEDS CONFIRMATION]
- [RISK] Do not target self-excluded users, RG-risk users, cooling-off users, or users selected because of recent heavy losses.
- [RECOMMENDATION] Route to crm-sportsbook-rg-compliance-review before launch.

## 14. Commercial Risk Review
- Bonus cost risk: [RISK] [OFFER_VALUE] and [MAX_BONUS_VALUE] require confirmation.
- Abuse risk: [RISK] [BONUS_SENSITIVITY] requires confirmation.
- Sharp/arb risk: [RISK] [SHARP_OR_ARB_RISK] requires confirmation.
- Margin risk: [RISK] [MINIMUM_ODDS] and [ELIGIBLE_MARKETS] require confirmation.
- Low incrementality risk: [NEEDS CONFIRMATION] Compare against control group or historical behaviour.
- Operational risk: [NEEDS CONFIRMATION] Confirm product availability, settlement logic, and reward fulfilment.

## 15. UX Clarity Review
- Clear with T&C support:
- Rationale: The value proposition is simple, but qualification details must be confirmed and referenced through [T&CS].

## 16. Recommended Next Skills
- crm-sportsbook-campaign-brief
- crm-sportsbook-sms-copy
- crm-sportsbook-localisation
- crm-sportsbook-rg-compliance-review
- crm-sportsbook-ab-testing

## 17. Launch Readiness
- Needs offer constraints before campaign brief.
```
