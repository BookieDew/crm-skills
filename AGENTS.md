# Agent Instructions

AI agents working in this repository must preserve the sportsbook CRM skill pack as market-agnostic, operational, and compliance-conscious.

## Non-Negotiable Rules

- Do not hardcode any specific country, region, language, local league, local sport preference, local operator, local regulation, local payment method, or geo-specific behaviour.
- Use placeholders such as `[TARGET_MARKET]`, `[TARGET_LANGUAGE]`, `[TARGET_CHANNEL]`, `[TARGET_SEGMENT]`, `[TARGET_EVENT]`, `[TARGET_SPORT]`, `[OFFER_MECHANIC]`, `[OFFER_VALUE]`, `[BRAND_TONE]`, `[T&CS]`, and `[REGULATORY_NOTES]`.
- Keep sportsbook specificity strong: segment by sport preference, event relevance, stake level, bet type preference, accumulator tendency, bet builder usage, bonus sensitivity, churn risk, VIP status, sharp or arb sensitivity, margin impact, and bonus abuse risk.
- Keep SMS separate from email and push. The SMS skill may acknowledge those as future skills, but it must not become a generic copywriting skill.
- Do not weaken responsible-gaming, suppression, compliance, UX, or commercial guardrails.
- Do not invent regulation, local sports calendars, live fixtures, local behaviours, or cultural facts.

## Change Process

After any change:

1. Check every edited file for market-specific leakage.
2. Confirm all assumptions are labelled with `[CONFIRMED]`, `[ASSUMPTION]`, `[NEEDS CONFIRMATION]`, `[RISK]`, or `[RECOMMENDATION]` where relevant.
3. Confirm all skills still reference `crm-sportsbook-shared-principles`.
4. Confirm `skill-manifest.json` is valid JSON and reflects any skill additions or dependency changes.
5. Run the checklist in `docs/audit-checklist.md`.

