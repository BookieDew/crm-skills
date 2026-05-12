# Market-Agnostic Rules

## Core Rule
No skill or documentation should permanently assume a specific market.

The target market must be supplied at runtime.

## Do Not Hardcode
Do not hardcode:
- Countries
- Regions
- Local languages
- Local leagues
- Local teams
- Local tournaments
- Local operators
- Local regulators
- Local laws
- Local payment methods
- Local holidays
- Local sport preferences
- Local betting habits
- Local channel preferences
- Local slang
- Local cultural behaviour
- Local competitor examples

## Use Placeholders
Use:
- [TARGET_MARKET]
- [TARGET_LANGUAGE]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT]
- [TARGET_SPORT]
- [TARGET_EVENT]
- [TARGET_TOURNAMENT]
- [TARGET_FIXTURE]
- [CAMPAIGN_OBJECTIVE]
- [OFFER_MECHANIC]
- [OFFER_VALUE]
- [REGULATORY_NOTES]
- [BRAND_TONE]
- [T&CS]
- [T&CS_LINK]

## Market Fact Handling
If a market-specific detail is needed:
1. Ask the user.
2. Use provided internal data.
3. Use confirmed research if available.
4. Mark as [NEEDS CONFIRMATION].
5. Use [ASSUMPTION] only if clearly labelled.

## Examples Must Be Placeholder-Only
All examples in skill files and docs must use placeholders only.

Do not include real country, region, language, league, tournament, team, operator, payment method, regulation, regulator, slang, or cultural references in permanent examples.

## Compliance Caveat
No skill should claim local compliance unless local regulatory notes or approved research are supplied.

Use [REGULATORY_NOTES] for runtime compliance context. If [REGULATORY_NOTES] are missing, mark compliance conclusions as [NEEDS CONFIRMATION].
