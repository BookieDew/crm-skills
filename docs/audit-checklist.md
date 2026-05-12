# Audit Checklist

Run this checklist after creating or changing any file in the skill pack.

## Market-Agnostic Audit

- No hardcoded market references.
- No specific countries or regions.
- No specific local languages.
- No specific local leagues.
- No specific local payment methods.
- No specific operators.
- No invented regulation.
- No invented current fixtures, live events, or local sports calendars.
- All market-specific items use placeholders or labelled assumptions.

## Skill Structure Audit

- Every skill has `SKILL.md`.
- Every `SKILL.md` includes purpose, role, when to use, when not to use, required inputs, output, workflow, decision logic, dependencies, sportsbook considerations, market-agnostic rules, channel-aware rules, RG and compliance guardrails, commercial guardrails, brand and UX guardrails, assumption labels, output template, example request, and example output.
- `crm-sportsbook-shared-principles` remains the source of truth.
- Dependencies are coherent.
- Shared principles are referenced by every skill.
- `skill-manifest.json` is valid JSON and lists every skill.

## Capability Audit

- SMS skill is fully developed and remains SMS-specific.
- RG/compliance review produces `Pass`, `Needs Revision`, or `Do Not Launch`.
- Offer mechanics are sportsbook-specific and commercially constrained.
- Campaign brief supports end-to-end campaign creation.
- Journey builder includes suppression, exits, control group, frequency caps, and RG-safe reactivation.
- A/B testing includes hypothesis, variants, KPIs, split, control, measurement window, risk controls, and decision rule.
- Post-campaign analysis includes segment, offer, channel, bonus cost, GGR/NGR, RG observations, learnings, and recommendations.

## Git-Ready Audit

- Folder structure matches the requested layout.
- Files are readable Markdown or valid JSON.
- No temporary files are committed.
- No generated local audit output is required unless intentionally added.

