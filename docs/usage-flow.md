# Usage Flow

Use `crm-sportsbook-shared-principles` as the baseline for every workflow. If a request is unclear, start with `crm-sportsbook-skill-router`.

## Full Campaign

1. `crm-sportsbook-market-context`
2. `crm-sportsbook-event-opportunity`
3. `crm-sportsbook-player-segmentation`
4. `crm-sportsbook-offer-mechanics`
5. `crm-sportsbook-campaign-brief`
6. `crm-sportsbook-sms-copy` when `[TARGET_CHANNEL]` is SMS
7. `crm-sportsbook-localisation`
8. `crm-sportsbook-rg-compliance-review`
9. `crm-sportsbook-journey-builder`
10. `crm-sportsbook-ab-testing`

## SMS-Only

1. Confirm `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, `[TARGET_SEGMENT]`, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, `[BRAND_TONE]`, `[T&CS]`, and `[REGULATORY_NOTES]`.
2. Run `crm-sportsbook-sms-copy`.
3. Run `crm-sportsbook-localisation` if local adaptation is requested.
4. Run `crm-sportsbook-rg-compliance-review`.

## Offer-Only

1. Run `crm-sportsbook-player-segmentation`.
2. Run `crm-sportsbook-offer-mechanics`.
3. Run `crm-sportsbook-rg-compliance-review` for risk and constraint checks.

## Compliance Review

1. Run `crm-sportsbook-rg-compliance-review`.
2. If issues are found, route fixes to `crm-sportsbook-offer-mechanics`, `crm-sportsbook-sms-copy`, `crm-sportsbook-journey-builder`, or `crm-sportsbook-campaign-brief` as needed.

## Localisation

1. Run `crm-sportsbook-market-context`.
2. Run `crm-sportsbook-localisation`.
3. Run `crm-sportsbook-rg-compliance-review` for local risk notes supplied at runtime.

## Journey

1. Run `crm-sportsbook-campaign-brief`.
2. Run `crm-sportsbook-rg-compliance-review`.
3. Run `crm-sportsbook-journey-builder`.
4. Run `crm-sportsbook-ab-testing` if a test is needed.

## A/B Test

1. Run `crm-sportsbook-campaign-brief`.
2. Run `crm-sportsbook-ab-testing`.
3. Run `crm-sportsbook-rg-compliance-review` if any variant changes offer value, urgency, eligibility, or copy claims.

## Post-Campaign Analysis

1. Run `crm-sportsbook-post-campaign-analysis`.
2. Feed learnings into `crm-sportsbook-player-segmentation`, `crm-sportsbook-offer-mechanics`, and `crm-sportsbook-campaign-brief` for the next campaign.

