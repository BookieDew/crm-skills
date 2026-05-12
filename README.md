# Sportsbook CRM Skill Pack

This repository contains a market-agnostic AI skill pack for sportsbook CRM teams. It helps CRM managers create personalised sportsbook campaigns, offers, SMS copy, localisation guidance, campaign briefs, A/B tests, customer journeys, and post-campaign analysis.

The pack is designed for CRM, lifecycle, retention, VIP, trading-adjacent marketing, localisation, and compliance-review workflows where the target market is supplied at runtime.

## How to Use

Start with `skills/crm-sportsbook-skill-router/SKILL.md` when the request is broad or ambiguous. The router selects the right skill chain and identifies missing runtime inputs.

Recommended full campaign flow:

1. `crm-sportsbook-shared-principles`
2. `crm-sportsbook-skill-router`
3. `crm-sportsbook-market-context`
4. `crm-sportsbook-event-opportunity`
5. `crm-sportsbook-player-segmentation`
6. `crm-sportsbook-offer-mechanics`
7. `crm-sportsbook-campaign-brief`
8. `crm-sportsbook-sms-copy` when `[TARGET_CHANNEL]` is SMS
9. `crm-sportsbook-localisation`
10. `crm-sportsbook-rg-compliance-review`
11. `crm-sportsbook-journey-builder`
12. `crm-sportsbook-ab-testing`
13. `crm-sportsbook-post-campaign-analysis`

For narrower tasks, use the specific skill directly. For example, use `crm-sportsbook-sms-copy` for SMS-only copy, `crm-sportsbook-offer-mechanics` for offer design, and `crm-sportsbook-rg-compliance-review` before launch.

## Market-Agnostic Principle

The permanent skill files must not hardcode any specific country, region, language, local league, local sport preference, operator, local regulation, local payment method, or geo-specific behaviour.

The target market must always be supplied at runtime by the user through placeholders such as:

- `[TARGET_MARKET]`
- `[TARGET_LANGUAGE]`
- `[TARGET_CHANNEL]`
- `[TARGET_SEGMENT]`
- `[TARGET_EVENT]`
- `[TARGET_SPORT]`
- `[OFFER_MECHANIC]`
- `[OFFER_VALUE]`
- `[BRAND_TONE]`
- `[T&CS]`
- `[REGULATORY_NOTES]`

If market-specific knowledge is required, the AI must ask for the missing detail, mark it as `[NEEDS CONFIRMATION]`, state a labelled `[ASSUMPTION]`, or research it when approved tools are available.

## Responsible-Gaming Principle

Baseline responsible-gaming and suppression rules apply even where the runtime market notes are minimal. The pack must avoid targeting self-excluded users, users with responsible-gaming risk flags, or users selected because of recent heavy losses. It must avoid chasing-loss language, financial-solution claims, guaranteed-win language, aggressive urgency, unclear terms, emotional pressure, and manipulative win-back messaging.

## How to Extend

When adding a skill:

1. Keep the new skill market-agnostic.
2. Reference `crm-sportsbook-shared-principles`.
3. Use runtime placeholders for all market, language, channel, event, offer, brand, terms, and regulation details.
4. Keep channel-specific skills separate. SMS is implemented here; email and push should be added as distinct future skills.
5. Update `skill-manifest.json`.
6. Update `docs/usage-flow.md` if the routing changes.
7. Run the audit checklist in `docs/audit-checklist.md`.

