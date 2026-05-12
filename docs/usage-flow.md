# Usage Flow

Use `crm-sportsbook-shared-principles` as the baseline for every workflow. Use `crm-sportsbook-skill-router` when the CRM manager is unsure which skill chain to run.

Not every request needs every skill. Choose the shortest chain that can produce a safe, useful, and properly reviewed output.

## Full Campaign Creation Flow
1. `crm-sportsbook-market-context`
2. `crm-sportsbook-event-opportunity`
3. `crm-sportsbook-player-segmentation`
4. `crm-sportsbook-offer-mechanics`
5. `crm-sportsbook-campaign-brief`
6. `crm-sportsbook-sms-copy`
7. `crm-sportsbook-localisation`
8. `crm-sportsbook-rg-compliance-review`
9. `crm-sportsbook-journey-builder`
10. `crm-sportsbook-ab-testing`
11. `crm-sportsbook-post-campaign-analysis`

What each step contributes:
- `crm-sportsbook-market-context` separates confirmed market, channel, language, brand, and regulatory inputs from assumptions.
- `crm-sportsbook-event-opportunity` evaluates supplied sport, event, tournament, fixture, and timing context.
- `crm-sportsbook-player-segmentation` defines target audience, exclusions, risk flags, and segment rationale.
- `crm-sportsbook-offer-mechanics` designs or reviews the offer mechanic, value, constraints, and exposure controls.
- `crm-sportsbook-campaign-brief` combines market, event, segment, offer, channel, commercial, and measurement logic.
- `crm-sportsbook-sms-copy` creates SMS-specific copy variants when [TARGET_CHANNEL] is SMS.
- `crm-sportsbook-localisation` adapts supplied campaign material to [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], and [BRAND_TONE].
- `crm-sportsbook-rg-compliance-review` checks suppression, copy, offer, T&C, compliance, RG, commercial, UX, and operational risks.
- `crm-sportsbook-journey-builder` defines journey triggers, entry rules, steps, timing, suppressions, exits, frequency caps, measurement, and fallback logic.
- `crm-sportsbook-ab-testing` designs safe test logic, variants, control group, KPIs, guardrails, and decision rules.
- `crm-sportsbook-post-campaign-analysis` analyses supplied results and feeds learnings into future planning.

## Fast SMS Campaign Flow
Use when campaign strategy already exists:
1. Campaign Brief
2. SMS Copy
3. Localisation
4. RG/Compliance Review
5. Journey Builder, if more than one send
6. A/B Testing, if testing

Required runtime context should include [TARGET_MARKET], [TARGET_LANGUAGE], [TARGET_CHANNEL], [TARGET_SEGMENT], [CAMPAIGN_OBJECTIVE], [OFFER_MECHANIC], [OFFER_VALUE], [BRAND_TONE], [T&CS], and [T&CS_LINK].

## Offer-Only Flow
1. Player Segmentation
2. Offer Mechanics
3. RG/Compliance Review
4. Campaign Brief

Use when the CRM manager needs to design, compare, simplify, or risk-check [OFFER_MECHANIC] before full campaign planning.

## Event-Led Flow
1. Market Context
2. Event Opportunity
3. Player Segmentation
4. Offer Mechanics
5. Campaign Brief

Use when the campaign depends on [TARGET_SPORT], [TARGET_EVENT], [TARGET_TOURNAMENT], or [TARGET_FIXTURE]. Do not invent event facts or schedules.

## Reactivation Flow
1. Player Segmentation
2. Offer Mechanics
3. Campaign Brief
4. SMS Copy
5. RG/Compliance Review
6. Journey Builder

Reactivation flows require stronger RG suppression and careful non-manipulative language.

## A/B Testing Flow
1. Campaign Brief
2. SMS Copy / Localisation / Journey Builder
3. RG/Compliance Review
4. A/B Testing
5. Post-Campaign Analysis

Use this flow to compare message angle, CTA, offer value, offer mechanic, timing, journey step, localisation, or control group design.

## Post-Campaign Learning Flow
1. Post-Campaign Analysis
2. Update future segmentation, offer mechanics, SMS copy, journey, or A/B testing assumptions

Use supplied performance results only. Do not invent uplift, causality, market facts, statistical significance, or regulatory conclusions.

## Router Usage
Use `crm-sportsbook-skill-router` when:
- The user request is broad or ambiguous
- The user does not know which skill to run
- Required inputs are missing
- The request might require multiple skills
- The request should be redirected to a safer or more specialist workflow
