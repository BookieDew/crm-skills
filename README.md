# CRM Sportsbook Skill Pack

## Overview
This repository contains a market-agnostic AI skill pack for sportsbook CRM teams.

It helps with:
- Market context
- Event opportunity planning
- Player segmentation
- Offer mechanics
- Campaign briefs
- SMS copy
- Localisation
- Responsible-gaming and compliance pre-review
- Journey building
- A/B testing
- Post-campaign analysis

The pack is designed to help teams move from runtime campaign context to execution-ready CRM outputs while preserving responsible-gaming, commercial, UX, and market-agnostic guardrails.

## Who This Is For
This pack is for:
- CRM managers
- CRM operators
- Sportsbook product teams
- Lifecycle marketers
- Local market managers
- BI / analytics teams
- Risk / trading stakeholders
- Compliance / responsible-gaming reviewers

## Core Principle
The skill pack must remain market-agnostic.

No permanent skill or documentation should hardcode a specific country, region, language, local league, local payment method, operator, regulation, or cultural behaviour.

The target market must always be supplied at runtime by the user or marked as needing confirmation.

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

## Skill List
| Skill ID | Folder path | Purpose | Usually runs after | Usually feeds into |
|---|---|---|---|---|
| `crm-sportsbook-shared-principles` | `skills/crm-sportsbook-shared-principles/SKILL.md` | Defines shared market-agnostic, RG, commercial, channel, measurement, and assumption-label rules. | None | All other skills |
| `crm-sportsbook-skill-router` | `skills/crm-sportsbook-skill-router/SKILL.md` | Routes CRM requests to the right skill or skill chain. | Shared principles | Specialist skills |
| `crm-sportsbook-market-context` | `skills/crm-sportsbook-market-context/SKILL.md` | Structures runtime market, language, channel, regulatory, brand, and operational context. | Shared principles, router | Event opportunity, segmentation, offer mechanics, campaign brief, localisation, SMS copy, RG/compliance review |
| `crm-sportsbook-event-opportunity` | `skills/crm-sportsbook-event-opportunity/SKILL.md` | Evaluates supplied sports, events, fixtures, tournaments, and calendar moments for CRM opportunity. | Market context | Segmentation, offer mechanics, campaign brief, SMS copy, localisation, journey builder, A/B testing |
| `crm-sportsbook-player-segmentation` | `skills/crm-sportsbook-player-segmentation/SKILL.md` | Defines and evaluates sportsbook CRM player segments using lifecycle, value, behaviour, risk, and eligibility context. | Market context, event opportunity | Offer mechanics, campaign brief, SMS copy, localisation, RG/compliance review, journey builder, A/B testing |
| `crm-sportsbook-offer-mechanics` | `skills/crm-sportsbook-offer-mechanics/SKILL.md` | Designs and evaluates sportsbook offer mechanics with segment fit, exposure controls, and RG safeguards. | Market context, event opportunity, player segmentation | Campaign brief, SMS copy, localisation, RG/compliance review, journey builder, A/B testing |
| `crm-sportsbook-campaign-brief` | `skills/crm-sportsbook-campaign-brief/SKILL.md` | Synthesises campaign context, segment, offer, channel, commercial logic, measurement, and guardrails into a campaign blueprint. | Market context, event opportunity, player segmentation, offer mechanics | SMS copy, localisation, RG/compliance review, journey builder, A/B testing, post-campaign analysis |
| `crm-sportsbook-sms-copy` | `skills/crm-sportsbook-sms-copy/SKILL.md` | Creates short, clear, responsible-gaming-aware SMS copy variants with offer, CTA, T&C, and character-count checks. | Campaign brief, offer mechanics | Localisation, RG/compliance review, journey builder, A/B testing, post-campaign analysis |
| `crm-sportsbook-localisation` | `skills/crm-sportsbook-localisation/SKILL.md` | Adapts supplied campaign logic and customer-facing copy to supplied market, language, channel, and brand context. | Campaign brief, SMS copy, offer mechanics, market context | RG/compliance review, journey builder, A/B testing, post-campaign analysis |
| `crm-sportsbook-rg-compliance-review` | `skills/crm-sportsbook-rg-compliance-review/SKILL.md` | Performs structured pre-launch risk review for RG, compliance, segment, offer, copy, T&C, channel, localisation, commercial, and operational risks. | Campaign brief, offer mechanics, SMS copy, localisation | Journey builder, A/B testing, post-campaign analysis |
| `crm-sportsbook-journey-builder` | `skills/crm-sportsbook-journey-builder/SKILL.md` | Turns campaign strategy, copy, offer, segment, and RG review into operational CRM journey logic. | Campaign brief, SMS copy, localisation, RG/compliance review | A/B testing, post-campaign analysis |
| `crm-sportsbook-ab-testing` | `skills/crm-sportsbook-ab-testing/SKILL.md` | Designs safe, measurable A/B tests and experiment plans with KPIs, guardrails, control logic, and decision rules. | Campaign brief, journey builder, RG/compliance review | Post-campaign analysis |
| `crm-sportsbook-post-campaign-analysis` | `skills/crm-sportsbook-post-campaign-analysis/SKILL.md` | Analyses supplied campaign results, commercial outcomes, variants, journeys, and RG observations to produce learnings. | Campaign brief, journey builder, A/B testing | Future market context, segmentation, offers, campaign briefs, copy, localisation, RG review, journeys, and tests |

## Recommended Usage Flow
Standard full campaign flow:

1. Shared Principles
2. Skill Router
3. Market Context
4. Event Opportunity
5. Player Segmentation
6. Offer Mechanics
7. Campaign Brief
8. SMS Copy
9. Localisation
10. RG & Compliance Review
11. Journey Builder
12. A/B Testing
13. Post-Campaign Analysis

Not every request needs every skill. Use `crm-sportsbook-skill-router` when the required chain is unclear.

## Light Skill Versions
Full skills in `skills/` are the detailed production and reference versions. Light skills in `skills-light/` are compact execution versions with the same skill purposes, guardrails, dependencies, and output structures.

Use light skills when speed and shorter context are preferred. Use full skills for complex, high-risk, first-time, ambiguous, or specialist campaign design. Light skills must not weaken market-agnostic, responsible-gaming, compliance, commercial, channel, brand, UX, or sportsbook-specific guardrails.

## Common Workflows

### Full Campaign Creation
Market Context -> Event Opportunity -> Player Segmentation -> Offer Mechanics -> Campaign Brief -> SMS Copy -> Localisation -> RG/Compliance Review -> Journey Builder -> A/B Testing

Example request:
"Create a campaign plan for [TARGET_SEGMENT] in [TARGET_MARKET]. Objective is [CAMPAIGN_OBJECTIVE], channel is [TARGET_CHANNEL], event is [TARGET_EVENT], and offer direction is [OFFER_MECHANIC]."

### SMS-Only Copy Creation
Campaign Brief or Offer Input -> SMS Copy -> Localisation -> RG/Compliance Review

Example request:
"Write SMS variants for [TARGET_SEGMENT] in [TARGET_MARKET]. The offer is [OFFER_VALUE] via [OFFER_MECHANIC], CTA is linked to [T&CS_LINK], and tone is [BRAND_TONE]."

### Offer Review
Offer Mechanics -> RG/Compliance Review -> Campaign Brief

Example request:
"Review [OFFER_MECHANIC] for [TARGET_SEGMENT] in [TARGET_MARKET] and identify safer or lower-cost alternatives."

### Localisation Review
SMS Copy -> Localisation -> RG/Compliance Review

Example request:
"Localise this SMS for [TARGET_LANGUAGE] in [TARGET_MARKET] using [BRAND_TONE] and preserving [T&CS_LINK]."

### Journey Build
Campaign Brief -> SMS Copy -> Localisation -> RG/Compliance Review -> Journey Builder -> A/B Testing

Example request:
"Build a CRM journey for [TARGET_SEGMENT] in [TARGET_MARKET] using [TARGET_CHANNEL], [OFFER_MECHANIC], and [TARGET_EVENT]."

### Post-Campaign Learning
Post-Campaign Analysis -> A/B Testing -> revised Campaign Brief / Offer Mechanics / Segmentation

Example request:
"Analyse the completed campaign for [TARGET_SEGMENT] in [TARGET_MARKET] and recommend what to revise before the next campaign."

## Assumption Labels
Use these labels consistently:

- [CONFIRMED] - Information explicitly provided by the user or a supplied source
- [ASSUMPTION] - Reasonable but unconfirmed assumption
- [NEEDS CONFIRMATION] - Important detail that should be checked before launch or conclusion
- [RISK] - Compliance, RG, commercial, UX, brand, data-quality, or operational risk
- [RECOMMENDATION] - Proposed action

## Responsible-Gaming Principle
All skills must avoid:
- Targeting self-excluded users
- Targeting users with RG risk flags
- Encouraging chasing losses
- Loss-recovery language
- Guaranteed-win claims
- Misleading risk-free wording
- Financial-pressure framing
- Hidden T&Cs
- Excessive urgency
- Manipulative reactivation

## How to Add a New Skill
1. Read `README.md`.
2. Read `AGENTS.md`.
3. Read `skills/crm-sportsbook-shared-principles/SKILL.md`.
4. Read relevant existing upstream and downstream skills.
5. Create `skills/[skill-id]/SKILL.md`.
6. Create `skills-light/[skill-id]/SKILL.md` if a light version is part of the release.
7. Update `skill-manifest.json`.
8. Update `skill-manifest-light.json` if a light version is created or changed.
9. Update docs if the usage flow, inputs, audit rules, or extension guidance changes.
10. Run the audit checklist in `docs/audit-checklist.md`.

## Suggested Future Skills
Future extensions may include:
- `crm-sportsbook-email-copy`
- `crm-sportsbook-push-copy`
- `crm-sportsbook-vip-outreach`
- `crm-sportsbook-crm-calendar`
- `crm-sportsbook-landing-page-copy`
- `crm-sportsbook-terms-simplifier`

These future skills do not exist yet. Do not document them as active skills until they are created and added to the relevant manifest.

## Git Workflow
- Prefer one skill per commit when possible.
- Use a documentation update after several skill changes or when pack architecture changes.
- Run the audit checklist before merging.
- Keep unrelated edits out of the same commit.
