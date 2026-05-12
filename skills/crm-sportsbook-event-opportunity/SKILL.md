---
name: crm-sportsbook-event-opportunity
description: Identifies and evaluates market-agnostic sportsbook CRM opportunities around runtime-supplied sports events, fixtures, tournaments, seasonal moments, calendar moments, lifecycle moments, and betting moments without inventing event facts.
---

# CRM Sportsbook Event Opportunity

## Purpose

This skill helps CRM teams identify and evaluate sportsbook CRM opportunities around sports events, fixtures, tournaments, seasonal moments, calendar moments, lifecycle moments, and betting moments.

It helps the CRM team decide whether an event is worth activating, which segments may care, what type of campaign opportunity exists, and what risks should be checked before moving to offer design or campaign brief creation.

This skill must not invent current fixtures, tournament schedules, event dates, teams, market facts, or local sports preferences. The target market, sport, event, tournament, fixture, and calendar context must always be supplied at runtime by the user, confirmed through approved research, or marked `[NEEDS CONFIRMATION]`.

## Role in the Skill Pack

This skill usually runs after `crm-sportsbook-market-context`, and may be selected by `crm-sportsbook-skill-router` when the user asks for event ideas, calendar planning, fixture activation, tournament journeys, or event-led CRM opportunities.

It translates market and calendar context into campaign opportunities.

It informs:

- Player segmentation.
- Offer mechanics.
- Campaign brief.
- SMS copy direction.
- Journey timing.
- A/B testing.
- RG/compliance review.

It should not create the final campaign brief by itself. It identifies and prioritises event opportunities that downstream skills can use.

## When to Use

Use this skill when the CRM manager needs to:

- Find campaign opportunities around `[TARGET_EVENT]`.
- Assess whether `[TARGET_FIXTURE]` is worth activating.
- Build an event-led sportsbook CRM idea.
- Plan campaigns around `[TARGET_TOURNAMENT]`.
- Identify relevant sports moments for `[TARGET_MARKET]`.
- Evaluate timing for pre-match or live-betting CRM.
- Compare multiple event opportunities.
- Prioritise events for a CRM calendar.
- Turn sports calendar inputs into campaign ideas.
- Identify segment-event fit.
- Decide whether an event is suitable for SMS activation.
- Identify risks in event-led campaign planning.

## When Not to Use

Do not use this skill to:

- Invent current fixtures, tournament schedules, odds, teams, or event dates.
- Write final customer-facing SMS copy.
- Design the full offer mechanic.
- Build the full campaign brief.
- Perform legal review.
- Analyse post-campaign results.
- Create market context from scratch if no market input exists.

Route those requests to the appropriate skills:

- Routing or task selection: `crm-sportsbook-skill-router`.
- Market context: `crm-sportsbook-market-context`.
- Segment design: `crm-sportsbook-player-segmentation`.
- Offer design: `crm-sportsbook-offer-mechanics`.
- Campaign synthesis: `crm-sportsbook-campaign-brief`.
- SMS copy: `crm-sportsbook-sms-copy`.
- Localisation: `crm-sportsbook-localisation`.
- RG/compliance review: `crm-sportsbook-rg-compliance-review`.
- Journey design: `crm-sportsbook-journey-builder`.
- A/B testing: `crm-sportsbook-ab-testing`.
- Performance analysis: `crm-sportsbook-post-campaign-analysis`.

## Required Inputs

### Minimum required inputs

- `[TARGET_MARKET]`
- `[CAMPAIGN_OBJECTIVE]` if known.
- At least one of:
  - `[TARGET_SPORT]`
  - `[TARGET_EVENT]`
  - `[TARGET_TOURNAMENT]`
  - `[TARGET_FIXTURE]`
  - Event calendar data supplied by the user.

### Recommended inputs

- `[TARGET_CHANNEL]`
- `[TARGET_LANGUAGE]`
- `[TARGET_SEGMENT]`
- `[EVENT_DATE]`
- `[EVENT_START_TIME]`
- `[BRAND_TONE]`
- `[MARKET_CONTEXT_OUTPUT]`
- `[REGULATORY_NOTES]`
- `[CUSTOMER_SEGMENT_DATA]`

### Advanced optional inputs

- Full sports calendar.
- Fixture list.
- Local event calendar.
- Historical betting volumes by event.
- Historical CRM performance by sport/event.
- Segment-level sport preference.
- Segment-level league/team preference.
- Pre-match vs live betting split.
- Average stake by sport/event.
- Margin by sport/market.
- Competitor campaign examples.
- Bonus cost limits.
- VIP relevance.
- Local holiday or payday calendar.
- Broadcast schedule.
- Event popularity ranking.
- Odds or market availability.
- Product availability by sport/event.

## Output

The skill should produce:

- Event opportunity summary.
- Confirmed event inputs.
- Assumptions.
- Items needing confirmation.
- Event relevance assessment.
- Segment fit assessment.
- Channel fit assessment.
- Campaign angle options.
- Offer mechanic direction, not final mechanics.
- Timing considerations.
- Commercial considerations.
- RG/compliance considerations.
- Opportunity priority.
- Recommended next skills.

## Workflow

1. Identify `[TARGET_MARKET]` and any supplied market context.
2. Load and apply `crm-sportsbook-shared-principles`.
3. If the request is broad or ambiguous, use `crm-sportsbook-skill-router` routing logic.
4. Use `crm-sportsbook-market-context` output when available.
5. Identify the event, sport, tournament, fixture, or calendar moment.
6. Separate confirmed event facts from assumptions.
7. Mark missing event details as `[NEEDS CONFIRMATION]`.
8. Check whether the event is relevant to `[CAMPAIGN_OBJECTIVE]`.
9. Assess potential segment fit.
10. Assess whether `[TARGET_CHANNEL]` can explain the opportunity clearly.
11. Consider timing:
    - Pre-event.
    - Matchday.
    - Live/in-play.
    - Post-event.
    - Multi-day tournament.
    - Recurring league cycle.
12. Identify possible campaign angles.
13. Identify likely offer mechanic directions without finalising the offer.
14. Check commercial risks.
15. Check RG and compliance risks.
16. Prioritise the opportunity.
17. Recommend the next skill chain.

## Decision Logic

Apply these rules:

- If `[TARGET_EVENT]`, `[TARGET_TOURNAMENT]`, `[TARGET_FIXTURE]`, or event calendar data is missing, mark it as `[NEEDS CONFIRMATION]`.
- If current fixtures, event dates, or schedules are required, do not invent them.
- If research tools are available, instruct the AI to research or verify current event information.
- If no research tools are available, ask the user to provide the event calendar or mark it as `[NEEDS CONFIRMATION]`.
- If `[TARGET_MARKET]` is missing, ask for it or mark it as `[NEEDS CONFIRMATION]`.
- If market context has not been created, recommend running `crm-sportsbook-market-context`.
- If `[TARGET_CHANNEL]` is SMS, prioritise simple event-led angles that can be explained in one short message.
- If the event has broad appeal, consider mass or recreational segments, but still apply suppression rules.
- If the event has niche appeal, recommend targeting only players with relevant sport, league, team, or bet-type preference supplied at runtime.
- If the event is high-volatility or likely to attract bonus abuse, flag commercial risk.
- If the opportunity relies on live betting, flag operational timing and suspension-state risks.
- If the opportunity depends on specific odds, markets, or product availability, mark those as `[NEEDS CONFIRMATION]`.
- If the event is not clearly relevant to `[TARGET_SEGMENT]`, recommend either a different segment or a different event.
- If `[CAMPAIGN_OBJECTIVE]` is reactivation, avoid emotional pressure and do not frame the event as a reason to chase missed winnings.
- If `[CAMPAIGN_OBJECTIVE]` is retention, avoid over-incentivising users who would likely bet anyway.
- If `[CAMPAIGN_OBJECTIVE]` is activation, focus on simple first-action mechanics.
- If `[CAMPAIGN_OBJECTIVE]` is VIP engagement, recommend tighter personalisation and stronger manual review.

## Dependencies

- Normally run before this skill: `crm-sportsbook-shared-principles`, `crm-sportsbook-skill-router` when the request is broad or ambiguous, and `crm-sportsbook-market-context`.
- Normally run after this skill: `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, `crm-sportsbook-campaign-brief`, `crm-sportsbook-sms-copy`, `crm-sportsbook-localisation`, `crm-sportsbook-rg-compliance-review`, `crm-sportsbook-journey-builder`, and `crm-sportsbook-ab-testing`.
- Shared principles it must follow: market-agnostic rules, assumption labels, responsible-gaming baseline rules, suppression rules, commercial protection rules, channel communication principles, brand and UX principles, and measurement principles.

## Sportsbook-Specific Considerations

The skill should consider, without inventing local facts:

- Sport relevance in `[TARGET_MARKET]`.
- Event scale and expected betting interest.
- Fixture timing.
- Tournament stage.
- Local relevance of teams, players, leagues, or competitions if provided.
- Pre-match betting suitability.
- Live/in-play betting suitability.
- Single bet vs accumulator opportunity.
- Bet builder opportunity.
- Odds boost suitability.
- Free bet suitability.
- Cashback or stake-back suitability.
- Mission/challenge suitability.
- Accumulator insurance suitability.
- VIP relevance.
- Recreational player relevance.
- Sharp or arb-sensitive exposure.
- Bonus abuse risk.
- Margin protection.
- Product availability.
- Market availability.
- Communication timing.
- Frequency cap impact.
- Channel opt-in coverage.

## Event Opportunity Types

Support the following opportunity types.

### Major Event Activation

Use when `[TARGET_EVENT]` or `[TARGET_TOURNAMENT]` has broad audience relevance.

Assess:

- Mass appeal.
- Segment reach.
- Offer simplicity.
- Channel suitability.
- Risk of over-bonusing.

### Fixture-Specific Activation

Use when a specific `[TARGET_FIXTURE]` is supplied.

Assess:

- Team/player relevance.
- Timing.
- Eligible markets.
- Pre-match vs live angle.
- Segment fit.

### Tournament Journey

Use when the event spans multiple days, rounds, or stages.

Assess:

- Journey structure.
- Reminder timing.
- Fatigue risk.
- Frequency caps.
- Progressive offers.
- Exit criteria.

### Local Calendar Moment

Use when the campaign is tied to a payday, holiday, local event, or seasonal moment supplied by the user.

Assess:

- Relevance.
- Tone sensitivity.
- RG risk.
- Channel timing.
- Commercial logic.

### Lifecycle Event Opportunity

Use when the "event" is customer lifecycle-based rather than sports-calendar-based.

Examples using placeholders:

- `[FIRST_DEPOSIT_WINDOW]`
- `[FIRST_BET_WINDOW]`
- `[DORMANCY_THRESHOLD]`
- `[VIP_REVIEW_WINDOW]`
- `[BONUS_EXPIRY_WINDOW]`

Assess:

- Customer action relevance.
- RG safety.
- Offer value.
- Suppression rules.

### Betting Behaviour Opportunity

Use when the trigger is based on betting behaviour.

Examples using placeholders:

- `[PREFERRED_SPORT_ACTIVITY]`
- `[ACCUMULATOR_INTEREST]`
- `[LIVE_BETTING_ACTIVITY]`
- `[BET_BUILDER_INTEREST]`

Assess:

- Behavioural fit.
- Personalisation risk.
- Commercial risk.
- RG safety.

## Market-Agnostic Design Rules

The skill must never assume:

- Current fixture schedules.
- Current tournament calendars.
- Local sports popularity.
- Local teams.
- Local leagues.
- Local holidays.
- Local broadcast schedules.
- Local language.
- Local payment behaviour.
- Local regulation.
- Local cultural behaviour.
- Local competitor offers.

All event-specific and market-specific details must come from:

- User-provided inputs.
- Internal documents.
- Confirmed research.
- Runtime browsing or research tools, if available.

If a detail is not confirmed, label it:

- `[ASSUMPTION]`
- `[NEEDS CONFIRMATION]`
- `[RISK]`
- `[RECOMMENDATION]`

Do not present assumptions as facts.

## Channel-Aware Design Rules

The skill should consider `[TARGET_CHANNEL]` if supplied.

For SMS:

- Prefer one clear event angle.
- Prefer one simple offer concept.
- Avoid multi-step mechanics unless extremely simple.
- Avoid long event explanations.
- Avoid jargon.
- Make timing clear.
- Ensure terms and conditions can be linked or compressed.
- Flag complex event mechanics as UX risk.

For email:

- Note that detailed email execution should be handled by a future email-specific skill.
- Event storytelling, education, and multiple offer blocks may be possible, but should not be fully drafted here.

For push:

- Note that detailed push execution should be handled by a future push-specific skill.
- Event urgency must not become manipulative.

For onsite or inbox:

- Consider whether the event opportunity needs supporting landing page, banner, or inbox explanation.

For VIP outreach:

- Recommend stronger personalisation review, manual approval, and RG-safe language.

## Responsible Gaming & Compliance Guardrails

The skill must follow `crm-sportsbook-shared-principles` responsible-gaming rules.

It must flag event opportunities that:

- Target self-excluded users.
- Target users with RG risk flags.
- Encourage chasing losses.
- Use previous losses as an event trigger.
- Apply pressure around event timing.
- Suggest betting is necessary to enjoy an event.
- Suggest guaranteed profit.
- Overstate the chance of winning.
- Hide important offer restrictions.
- Use urgency in a way that could pressure vulnerable users.
- Target recently heavy-losing users with event-led incentives.

The skill must recommend suppression checks before moving to campaign brief or copy.

## Commercial Guardrails

The skill should identify event-context factors that could affect:

- Bonus cost.
- Margin exposure.
- Offer uptake.
- Segment size.
- Bonus abuse risk.
- Arbitrage sensitivity.
- Sharp-player exposure.
- VIP cost.
- Product availability.
- Eligible market availability.
- In-play suspension or settlement risk.
- Operational readiness.
- Terms and conditions complexity.
- Frequency cap impact.
- Opt-out risk.

Do not estimate commercial impact unless data is provided or the user explicitly asks for assumptions.

## Brand & UX Guardrails

The skill should help the CRM team understand:

- Whether the event angle is clear enough for `[TARGET_CHANNEL]`.
- Whether the customer value is obvious.
- Whether the event relevance is strong enough.
- Whether the message may feel forced.
- Whether personalisation may feel invasive.
- Whether the event requires educational explanation.
- Whether terms and conditions may be too complex.
- Whether urgency is appropriate or too aggressive.

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
# Event Opportunity Output

## 1. Opportunity Context
- Target market: [TARGET_MARKET]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport: [TARGET_SPORT]
- Event/tournament/fixture: [TARGET_EVENT] / [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Event date/time: [EVENT_DATE] / [EVENT_START_TIME]

## 2. Confirmed Inputs
- [CONFIRMED]

## 3. Working Assumptions
- [ASSUMPTION]

## 4. Needs Confirmation
- [NEEDS CONFIRMATION]

## 5. Event Relevance Assessment
- Audience relevance:
- Segment relevance:
- Timing relevance:
- Channel relevance:
- Product relevance:

## 6. Campaign Opportunity Angles
| Angle name | Description | Best-fit segment | Suitable channel | Offer direction | Main benefit | Main risk |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## 7. Segment Fit
- Sport preference:
- Event/team/league preference if provided:
- Pre-match bettors:
- Live bettors:
- Accumulator users:
- Bet builder users:
- Bonus-sensitive users:
- VIPs:
- Dormant or reactivation users:
- Recreational users:
- Sharp or arb-sensitive users:

## 8. Offer Direction
- Free bet direction:
- Odds boost direction:
- Bet-and-get direction:
- Accumulator insurance direction:
- Cashback direction:
- Mission/challenge direction:
- Bet builder boost direction:

## 9. Timing Plan
- Pre-event message timing:
- Matchday or event-day timing:
- Reminder logic if appropriate:
- Live/in-play caution:
- Post-event follow-up caution:
- Frequency cap considerations:

## 10. Channel Considerations
- [TARGET_CHANNEL]:
- SMS suitability if applicable:
- Complexity risk:
- Simple copy direction:

## 11. RG & Compliance Considerations
- [REGULATORY_NOTES]:
- [RISK]

## 12. Commercial Considerations
- [RISK]
- [RECOMMENDATION]

## 13. Opportunity Priority
- High priority / Medium priority / Low priority / Not recommended without more data:
- Rationale:

## 14. Recommended Next Skills
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 15. Launch Readiness
- Ready to proceed with assumptions / Needs event confirmation before offer design / Needs market/context confirmation before campaign design / Needs compliance/RG input before campaign design / Not recommended based on current information
```

## Example User Request

"Find campaign opportunities around `[TARGET_EVENT]` for `[TARGET_SEGMENT]` in `[TARGET_MARKET]`. The channel is `[TARGET_CHANNEL]` and the objective is `[CAMPAIGN_OBJECTIVE]`."

## Example Output

```markdown
# Event Opportunity Output

## 1. Opportunity Context
- Target market: [TARGET_MARKET]
- Campaign objective: [CAMPAIGN_OBJECTIVE]
- Target channel: [TARGET_CHANNEL]
- Target segment: [TARGET_SEGMENT]
- Sport: [TARGET_SPORT]
- Event/tournament/fixture: [TARGET_EVENT] / [TARGET_TOURNAMENT] / [TARGET_FIXTURE]
- Event date/time: [EVENT_DATE] / [EVENT_START_TIME]

## 2. Confirmed Inputs
- [CONFIRMED] Target market: [TARGET_MARKET]
- [CONFIRMED] Campaign objective: [CAMPAIGN_OBJECTIVE]
- [CONFIRMED] Target channel: [TARGET_CHANNEL]
- [CONFIRMED] Target segment: [TARGET_SEGMENT]
- [CONFIRMED] Target event: [TARGET_EVENT]

## 3. Working Assumptions
- [ASSUMPTION] No current fixture schedule, sport popularity, or segment-event affinity is assumed unless supplied by the user or confirmed research.

## 4. Needs Confirmation
- [NEEDS CONFIRMATION] [TARGET_LANGUAGE]
- [NEEDS CONFIRMATION] [TARGET_SPORT]
- [NEEDS CONFIRMATION] [TARGET_TOURNAMENT]
- [NEEDS CONFIRMATION] [TARGET_FIXTURE]
- [NEEDS CONFIRMATION] [EVENT_DATE]
- [NEEDS CONFIRMATION] [EVENT_START_TIME]
- [NEEDS CONFIRMATION] Product availability, eligible markets, channel opt-in coverage, suppression rules, and [REGULATORY_NOTES].

## 5. Event Relevance Assessment
- Audience relevance: [NEEDS CONFIRMATION] Requires event affinity, betting interest, or research.
- Segment relevance: [NEEDS CONFIRMATION] Validate [TARGET_SEGMENT] against sport, event, bet-type, and lifecycle data.
- Timing relevance: [NEEDS CONFIRMATION] Requires [EVENT_DATE] and [EVENT_START_TIME].
- Channel relevance: [RECOMMENDATION] If [TARGET_CHANNEL] is SMS, keep the event hook and offer concept simple.
- Product relevance: [NEEDS CONFIRMATION] Confirm available bet types, eligible markets, and product availability.

## 6. Campaign Opportunity Angles
| Angle name | Description | Best-fit segment | Suitable channel | Offer direction | Main benefit | Main risk |
|---|---|---|---|---|---|---|
| Event activation | Use [TARGET_EVENT] as the main hook for eligible customers with confirmed interest. | [TARGET_SEGMENT] with confirmed relevance | [TARGET_CHANNEL] | Simple event-led value direction | Clear event relevance | Event interest unconfirmed |
| Pre-event reminder | Contact eligible customers before [EVENT_START_TIME] when timing is confirmed. | Pre-match-oriented customers | [TARGET_CHANNEL] | Simple qualifying action direction | Timely activation | Urgency or frequency-cap risk |
| Tournament journey | Use staged messaging if [TARGET_TOURNAMENT] spans multiple confirmed stages. | Customers with confirmed tournament interest | Inbox, email, SMS only if simple | Progressive value direction | Repeat engagement | Fatigue and RG risk |

## 7. Segment Fit
- Sport preference: [NEEDS CONFIRMATION]
- Event/team/league preference if provided: [NEEDS CONFIRMATION]
- Pre-match bettors: [RECOMMENDATION] Consider if timing and sport preference are confirmed.
- Live bettors: [RISK] Requires operational readiness and careful timing.
- Accumulator users: [RECOMMENDATION] Consider only where accumulator preference is confirmed.
- Bet builder users: [RECOMMENDATION] Consider only where product use and event suitability are confirmed.
- Bonus-sensitive users: [RISK] Control cost and abuse risk.
- VIPs: [RISK] Require manual review and RG-safe personalisation.
- Dormant or reactivation users: [RISK] Avoid emotional pressure or chasing-loss framing.
- Recreational users: [RECOMMENDATION] Use simple event-led angles.
- Sharp or arb-sensitive users: [RISK] Avoid exploitable value.

## 8. Offer Direction
- Free bet direction: [RECOMMENDATION] Consider only with capped value and clear eligibility.
- Odds boost direction: [RISK] Confirm margin and sharp or arb-sensitive exposure.
- Bet-and-get direction: [RECOMMENDATION] Suitable if qualification can be explained simply.
- Accumulator insurance direction: [RISK] Use only for confirmed accumulator preference and capped exposure.
- Cashback direction: [RISK] Do not base on recent heavy losses.
- Mission/challenge direction: [RISK] Avoid excessive repeat-action pressure.
- Bet builder boost direction: [RECOMMENDATION] Use only if product availability and customer understanding are confirmed.

## 9. Timing Plan
- Pre-event message timing: [NEEDS CONFIRMATION] Requires event timing and frequency-cap rules.
- Matchday or event-day timing: [NEEDS CONFIRMATION] Confirm operational readiness.
- Reminder logic if appropriate: [RISK] Keep reminders neutral and limited.
- Live/in-play caution: [RISK] Account for suspension states, market availability, and short decision windows.
- Post-event follow-up caution: [RISK] Do not reference losses or missed winnings.
- Frequency cap considerations: [NEEDS CONFIRMATION]

## 10. Channel Considerations
- [TARGET_CHANNEL]: [RECOMMENDATION] Match event complexity to channel limits.
- SMS suitability if applicable: [RECOMMENDATION] SMS is suitable only for one clear event angle and one simple action.
- Complexity risk: [RISK] Multi-stage or rules-heavy event mechanics may be unsuitable for SMS.
- Simple copy direction: [RECOMMENDATION] Use a neutral event hook, clear value, simple CTA, and visible terms reference.

## 11. RG & Compliance Considerations
- [REGULATORY_NOTES]: [NEEDS CONFIRMATION]
- [RISK] Suppress self-excluded users, RG-risk users, cooling-off users, opted-out users, and users selected due to recent heavy losses.
- [RISK] Avoid urgency, loss references, guaranteed-profit claims, and pressure around event timing.

## 12. Commercial Considerations
- [RISK] Bonus cost, margin exposure, bonus abuse risk, eligible market availability, and sharp or arb-sensitive exposure need confirmation before offer design.
- [RECOMMENDATION] Prioritise capped, simple mechanics until segment fit and margin exposure are confirmed.

## 13. Opportunity Priority
- Not recommended without more data:
- Rationale: [NEEDS CONFIRMATION] Event timing, segment relevance, product availability, and compliance inputs are not yet confirmed.

## 14. Recommended Next Skills
- crm-sportsbook-player-segmentation
- crm-sportsbook-offer-mechanics
- crm-sportsbook-campaign-brief
- crm-sportsbook-rg-compliance-review

## 15. Launch Readiness
- Needs event confirmation before offer design.
```
