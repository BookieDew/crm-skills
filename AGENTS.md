# Agent Instructions

AI agents working in this repository must preserve the sportsbook CRM skill pack as market-agnostic, operational, sportsbook-specific, and responsible-gaming-aware.

## Always Read First
Agents must read:
- `README.md`
- `AGENTS.md`
- `skill-manifest.json`
- `skills/crm-sportsbook-shared-principles/SKILL.md`
- `docs/market-agnostic-rules.md`
- `docs/responsible-gaming-rules.md`
- `docs/audit-checklist.md`

Before editing a specific skill, agents must also read related upstream and downstream skills.

## Non-Negotiable Rules
Agents must:
- Preserve market-agnostic design
- Use placeholders
- Avoid hardcoded countries, regions, languages, leagues, teams, operators, regulations, payment methods, or cultural assumptions
- Preserve responsible-gaming guardrails
- Preserve sportsbook specificity
- Preserve channel separation
- Keep SMS separate from future email and push skills
- Reference shared principles rather than duplicating them excessively
- Run self-audit after changes

## No Market Leakage
Agents must search their changes for accidental hardcoded:
- Countries
- Regions
- Local languages
- Local leagues
- Local tournaments
- Local teams
- Local operators
- Local payment methods
- Local regulators
- Local laws
- Local slang
- Local cultural assumptions

Use placeholders such as:
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
- [BRAND_TONE]
- [REGULATORY_NOTES]
- [T&CS]
- [T&CS_LINK]

## Skill Editing Rules
When editing a skill:
- Keep structure consistent
- Keep dependencies accurate
- Keep output templates practical
- Keep examples placeholder-only
- Preserve assumption labels
- Preserve RG/compliance guardrails
- Preserve commercial guardrails
- Preserve brand and UX guardrails
- Keep channel-specific responsibilities separate
- Do not weaken sportsbook specificity

## Documentation Editing Rules
When editing docs:
- Keep docs aligned with actual skills
- Do not document skills that do not exist as if they exist
- Future skills may be listed as future extensions only
- Keep examples placeholder-only
- Keep workflow chains consistent with `skill-manifest.json`
- Keep responsible-gaming and market-agnostic wording consistent across docs

## Manifest Editing Rules
When editing `skill-manifest.json`:
- Keep valid JSON
- Include every active skill once
- Use the required fields: `id`, `name`, `path`, `purpose`, `depends_on`, `feeds_into`, `status`
- Use `status: "active"` for current skills
- Keep dependency and feedback links coherent
- Confirm every listed path exists

## Self-Audit Requirement
After changes, agents must report:
1. Files changed
2. Summary of changes
3. Market-agnostic check
4. RG/compliance check
5. Dependency check
6. Any risks
7. Suggested commit message
