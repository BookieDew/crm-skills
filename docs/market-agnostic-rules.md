# Market-Agnostic Rules

The permanent skill files must remain market-agnostic. The AI must not invent or hardcode any market fact.

## Do Not Hardcode

- Specific countries.
- Specific regions.
- Specific languages.
- Specific local leagues.
- Specific local sports preferences.
- Specific operators.
- Specific local regulations.
- Specific local payment methods.
- Geo-specific behaviour.
- Current fixtures or live sports calendars.
- Cultural assumptions.

## Required Placeholder Pattern

Use runtime placeholders such as:

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

## Handling Missing Detail

When market-specific detail is needed:

- Ask the user for the missing input.
- Mark the point `[NEEDS CONFIRMATION]`.
- State any provisional logic as `[ASSUMPTION]`.
- Research it only when research tools are available and the task allows research.

## Allowed Generic Sportsbook Concepts

The skills may discuss generic sportsbook CRM concepts such as pre-match betting, live betting, single bets, accumulator preference, bet builder suitability, free bets, odds boosts, cashback, bonus sensitivity, stake level, churn risk, VIP status, margin protection, and bonus abuse risk.

