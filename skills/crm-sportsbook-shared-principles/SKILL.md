---
name: crm-sportsbook-shared-principles
description: Foundational market-agnostic operating principles for sportsbook CRM skills. Defines common guardrails, runtime context, assumption labels, responsible-gaming rules, suppression rules, commercial protection, offer safety, channel communication principles, measurement standards, and campaign quality checks. Do not use this skill to create campaign output directly.
---

# CRM Sportsbook Shared Principles

## Purpose

This skill defines the shared operating principles for all sportsbook CRM skills in this pack.

It is not a campaign creation skill. Do not use it to create campaign briefs, offers, SMS copy, journeys, A/B tests, localisation, or post-campaign analysis directly. Use it as the foundation that all specialist skills must follow when producing those outputs.

This skill establishes:

- Market-agnostic rules.
- Runtime input standards.
- Assumption labels.
- Responsible-gaming baseline rules.
- Suppression rules.
- Commercial protection rules.
- Offer mechanic safety rules.
- Channel communication principles.
- Brand and UX principles.
- Measurement principles.
- Final campaign quality standards.

## Scope

This skill applies to every specialist skill and workflow in the sportsbook CRM skill pack, including:

- Market context.
- Player segmentation.
- Event opportunity.
- Offer mechanics.
- Campaign briefs.
- SMS copy.
- Localisation.
- Responsible gaming and compliance review.
- Journey building.
- A/B testing.
- Post-campaign analysis.

When another skill is used, it must apply the rules in this shared-principles skill before producing recommendations or customer-facing output.

## Market-Agnostic Rule

No skill should assume a specific market unless the user provides it at runtime.

No skill should invent local facts.

Do not hardcode any specific country, region, language, league, operator, payment method, regulation, local sport preference, local customer behaviour, local event calendar, or geo-specific requirement.

If market-specific knowledge is required, the AI must:

- Ask for the missing information, or
- Mark the item as `[NEEDS CONFIRMATION]`, or
- Use `[ASSUMPTION]` if making a reasonable but unconfirmed assumption, or
- Research if current browsing or research tools are available.

Market-specific details must be supplied at runtime through placeholders such as:

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[OFFER_MECHANIC]`

## Runtime Context Model

Skills may request or consume the following runtime inputs. Missing inputs should be labelled, not invented.

### Customer context

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[CUSTOMER_LIFECYCLE_STAGE]`
- `[CUSTOMER_VALUE_SEGMENT]`
- `[VIP_STATUS]`
- `[BONUS_SENSITIVITY]`
- `[CHURN_RISK]`
- `[RG_RISK_STATUS]`
- `[SELF_EXCLUSION_STATUS]`
- `[COMMUNICATION_OPT_IN_STATUS]`
- `[PREFERRED_SPORT]`
- `[PREFERRED_LEAGUE]`
- `[PREFERRED_TEAM]`
- `[PREFERRED_BET_TYPE]`
- `[PRE_MATCH_OR_LIVE_PREFERENCE]`
- `[SINGLE_OR_ACCUMULATOR_PREFERENCE]`
- `[AVERAGE_STAKE]`
- `[DEPOSIT_BEHAVIOUR]`
- `[LAST_ACTIVE_DATE]`
- `[LAST_DEPOSIT_DATE]`
- `[BONUS_HISTORY]`

### Campaign context

- `[CAMPAIGN_OBJECTIVE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- `[MINIMUM_STAKE]`
- `[MINIMUM_ODDS]`
- `[MAX_BONUS_VALUE]`
- `[EXPIRY]`
- `[ELIGIBLE_MARKETS]`
- `[T&CS]`
- `[BRAND_TONE]`
- `[REGULATORY_NOTES]`
- `[EXCLUSION_RULES]`
- `[SUCCESS_METRICS]`

### Performance context

- `[DELIVERY_RATE]`
- `[OPEN_RATE]`
- `[CLICK_RATE]`
- `[OPT_OUT_RATE]`
- `[DEPOSIT_CONVERSION]`
- `[BET_CONVERSION]`
- `[BONUS_UPTAKE]`
- `[TURNOVER]`
- `[GGR]`
- `[NGR]`
- `[BONUS_COST]`
- `[INCREMENTAL_REVENUE]`
- `[RETENTION_UPLIFT]`
- `[CHURN_REDUCTION]`
- `[COMPLAINTS]`
- `[POST_CAMPAIGN_RG_FLAGS]`

## Assumption Labels

All skills must use these labels when handling inputs, risks, and recommendations:

- `[CONFIRMED]` - Information explicitly provided by the user.
- `[ASSUMPTION]` - Reasonable but unconfirmed assumption.
- `[NEEDS CONFIRMATION]` - Important item that should be checked before launch.
- `[RISK]` - Compliance, RG, commercial, UX, or brand risk.
- `[RECOMMENDATION]` - Proposed action.

Use labels visibly in outputs when a decision depends on incomplete information. Do not present assumptions as facts.

## Responsible Gaming Baseline Rules

All skills must apply baseline responsible-gaming safeguards, even when `[REGULATORY_NOTES]` are missing, incomplete, or described as permissive.

The skills must avoid:

- Targeting self-excluded users.
- Targeting users with RG risk flags.
- Targeting users who have cooling-off restrictions.
- Encouraging chasing losses.
- Using loss-based triggers in customer-facing copy.
- Saying or implying betting can solve financial problems.
- "Guaranteed win" language.
- Misleading "risk-free" wording unless approved.
- High-pressure language aimed at vulnerable users.
- Emotionally manipulative win-back language.
- Offers based on recent heavy losses.
- Suppressing or hiding T&Cs.
- Personalised pressure based on losses, debt, or financial stress.

If any of these risks are present, mark the item `[RISK]` and route to the responsible-gaming and compliance review skill before launch.

## Suppression Rules

Skills should normally exclude the following users from sportsbook CRM campaigns:

- Self-excluded users.
- Users with active RG restrictions.
- Users with active cooling-off periods.
- Users with unresolved account verification issues where promotional contact is not allowed.
- Users who opted out of the target channel.
- Users recently flagged for risky gambling behaviour.
- Users with bonus abuse restrictions, where relevant.
- Users restricted by compliance, fraud, AML, or risk teams.

If suppression data is unavailable, mark the launch state `[NEEDS CONFIRMATION]`. Do not treat missing suppression data as approval to launch.

## Commercial Protection Rules

All skills must protect margin and bonus cost. Commercial recommendations should be proportionate to customer value, expected incrementality, offer exposure, and risk.

Rules:

- Match offer value to customer value.
- Avoid over-incentivising users who would likely bet anyway.
- Avoid giving rich offers to bonus abusers.
- Avoid giving open-ended value without max exposure.
- Use minimum odds where relevant.
- Use minimum stake where relevant.
- Use max bonus value where relevant.
- Use eligible markets where relevant.
- Use clear expiry.
- Consider whether the offer fits retention, activation, reactivation, cross-sell, event activation, or VIP engagement.
- Consider recreational, VIP, sharp, arb-sensitive, and bonus-sensitive behaviour differently.

If commercial exposure cannot be capped or estimated, mark the offer `[RISK]` and require revision before launch.

## Offer Mechanic Safety Rules

Offer mechanics must be selected based on campaign objective, segment fit, product suitability, responsible-gaming safety, and commercial exposure. The following rules apply to common sportsbook offer types.

| Offer type | Best use case | Main commercial risk | Main RG/compliance risk | Recommended constraints |
|---|---|---|---|---|
| Free bet | Activation, event activation, controlled reactivation | Bonus cost without incremental betting | Can pressure inactive or vulnerable users if framed poorly | Cap `[OFFER_VALUE]`, define `[MINIMUM_ODDS]`, `[MINIMUM_STAKE]`, `[ELIGIBLE_MARKETS]`, `[EXPIRY]`, and one-use eligibility |
| Bet-and-get | Event activation or retention where a qualifying action is desired | Overpaying customers who would already qualify | Misleading value if qualification is unclear | Clear qualifying bet, `[MINIMUM_STAKE]`, `[MINIMUM_ODDS]`, max reward, eligible market, expiry |
| Odds boost | Event-led engagement for eligible recreational users | Margin erosion and sharp or arb exposure | Boost claims may imply better chance of winning if worded badly | Max stake, boost cap, eligible selection or market, expiry, sharp or arb-sensitive exclusions |
| Accumulator insurance | Retention for customers with confirmed accumulator preference | High refund cost if broad or poorly priced | May imply the bet is safer than it is | Minimum legs, minimum odds per leg, max refund, eligible markets, expiry |
| Cashback | Retention or soft value for eligible users | Rewarding loss-making patterns or high cost | High risk if based on losses or recent heavy losses | Never target from recent heavy losses, cap value, define period, eligible markets, and safe eligibility |
| Bet builder boost | Event activation for users with confirmed bet builder interest | Complexity and margin exposure | Customer may misunderstand qualification | Simple eligibility, max stake, minimum odds, eligible event, clear construction rules |
| Mission or challenge | Structured engagement over a limited period | Encouraging excessive frequency | Repeat-action mechanics may increase risky behaviour | Low action count, capped reward, safe timeframe, clear opt-out, no loss-based triggers |
| Deposit offer | Activation or reload where deposit behaviour is safe and eligible | Bonus cost, abuse, and wagering complexity | Can pressure depositing or imply financial benefit | Deposit cap, bonus cap, eligibility checks, clear T&Cs, no pressure language |
| Reload offer | Retention or reactivation for safe eligible profiles | Paying non-incremental or high-risk users | Manipulative win-back risk | Frequency cap, max bonus, eligibility, expiry, no loss-triggering |
| Loyalty points | Broad retention and lower-friction value | Low perceived value or unclear economics | Can encourage excessive repeat play if uncapped | Earning cap, eligible actions, redemption rules, expiry, RG monitoring |
| VIP bespoke offer | VIP engagement with manual review | High bonus cost and margin exposure | Higher duty of care and personalisation risk | Manual approval, RG review, commercial cap, eligible markets, expiry, documented rationale |

If a mechanic is too complex for `[TARGET_CHANNEL]`, the specialist skill should simplify it, choose a safer mechanic, or mark it `[NEEDS CONFIRMATION]`.

## Channel Communication Principles

Detailed channel execution belongs in channel-specific skills. This section defines only shared channel principles.

### SMS

- Short.
- Clear.
- One message, one offer.
- Simple CTA.
- Avoid complex mechanics.
- Include or link to T&Cs.
- Avoid aggressive urgency.
- Avoid jargon.

### Email

- Use only when a future email-specific skill or runtime brief defines structure, length, legal footer, content hierarchy, and creative requirements.
- Keep value, eligibility, and T&Cs easy to find.
- Do not hide material terms in dense copy.

### Push

- Use only when a future push-specific skill or runtime brief defines character limits and interaction behaviour.
- Keep the proposition simple and avoid pressure.
- Do not rely on push alone for complex terms.

### Onsite/inbox

- Use for more persistent, reviewable information where the user can inspect details.
- Keep offer status, eligibility, CTA, expiry, and T&Cs visible.
- Avoid making onsite or inbox messages more permissive than outbound channels.

### VIP manager outreach

- Use only with appropriate customer eligibility, manual review, and documented rationale.
- Keep wording respectful and factual.
- Avoid personalised pressure, loss references, or claims that imply certainty of winning.

## Brand and UX Principles

All customer communication should be easy to understand and safe to act on.

Rules:

- Be direct.
- Be understandable.
- Avoid misleading terms.
- Avoid overpromising.
- Make the next action clear.
- Respect local tone when provided.
- Do not stereotype markets.
- Do not use fake personalisation.
- Do not imply certainty of winning.

If a message relies on information not confirmed by the user, label it `[ASSUMPTION]` or `[NEEDS CONFIRMATION]`.

## Measurement Principles

Every campaign should define success before launch. Use control groups or holdouts where possible, especially when measuring incrementality or bonus cost efficiency.

Baseline campaign metrics:

- Delivery.
- Engagement.
- Conversion.
- Bonus uptake.
- Turnover.
- GGR.
- NGR.
- Bonus cost.
- Incremental uplift.
- Retention.
- Opt-out rate.
- Complaint rate.
- RG flags after campaign.

Use performance placeholders where needed:

- `[DELIVERY_RATE]`
- `[OPEN_RATE]`
- `[CLICK_RATE]`
- `[OPT_OUT_RATE]`
- `[DEPOSIT_CONVERSION]`
- `[BET_CONVERSION]`
- `[BONUS_UPTAKE]`
- `[TURNOVER]`
- `[GGR]`
- `[NGR]`
- `[BONUS_COST]`
- `[INCREMENTAL_REVENUE]`
- `[RETENTION_UPLIFT]`
- `[CHURN_REDUCTION]`
- `[COMPLAINTS]`
- `[POST_CAMPAIGN_RG_FLAGS]`

Do not claim incremental success without a valid comparison method.

## Final Campaign Quality Checklist

Every campaign should pass this checklist before launch:

- Market context: `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[REGULATORY_NOTES]`, and local requirements are confirmed or clearly labelled.
- Segment logic: `[TARGET_SEGMENT]` is defined with clear eligibility, exclusions, and rationale.
- Offer logic: `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, qualification rules, and customer value are clear.
- Commercial exposure: `[MAX_BONUS_VALUE]`, `[MINIMUM_STAKE]`, `[MINIMUM_ODDS]`, `[ELIGIBLE_MARKETS]`, `[EXPIRY]`, and cost controls are defined where relevant.
- RG suppression: self-exclusion, RG restrictions, cooling-off periods, risky behaviour flags, and channel opt-outs are suppressed.
- Compliance notes: `[REGULATORY_NOTES]`, `[EXCLUSION_RULES]`, account restrictions, and internal risk restrictions are applied.
- Channel suitability: `[TARGET_CHANNEL]` is appropriate for the offer, audience, message complexity, and timing.
- Copy clarity: customer value, next action, eligibility, and major constraints are understandable.
- T&Cs clarity: `[T&CS]` are visible, linked, or clearly referenced.
- Localisation: `[TARGET_LANGUAGE]`, `[BRAND_TONE]`, local style, and uncertain local points are handled without invented facts.
- Measurement: `[SUCCESS_METRICS]`, primary KPI, secondary KPIs, control group, and measurement window are defined.
- A/B test plan: hypothesis, variants, split, decision rule, and risk controls are defined where testing is required.
- Post-campaign review plan: performance, bonus cost, GGR, NGR, retention, opt-outs, complaints, and post-campaign RG flags will be reviewed.

If any checklist item fails, label it `[RISK]` or `[NEEDS CONFIRMATION]` and route the work to the relevant specialist skill before launch.
