# Audit Checklist

Run this checklist after creating or changing any file in the skill pack.

## Market-Agnostic Audit
Check:
- No hardcoded countries
- No hardcoded regions
- No hardcoded local languages
- No hardcoded local leagues
- No hardcoded teams
- No hardcoded operators
- No hardcoded regulators
- No hardcoded local regulations
- No hardcoded payment methods
- No hardcoded cultural assumptions
- Examples use placeholders only

## Skill Architecture Audit
Check:
- Every skill has clear purpose
- Every skill has clear role in the skill pack
- Every skill has when to use / when not to use
- Every skill has required inputs
- Every skill has workflow
- Every skill has decision logic
- Every skill has dependencies
- Every skill has output template
- Every skill references shared principles
- Dependencies in skill files match `skill-manifest.json`

## Sportsbook Specificity Audit
Check that the pack includes sportsbook-specific treatment of:
- Sports/events
- Pre-match vs live betting
- Singles vs accumulators
- Bet builder
- Odds boosts
- Free bets
- Cashback
- Deposit/reload offers
- VIPs
- Bonus-sensitive users
- Sharp/arb-sensitive users
- Bonus abuse
- Margin protection
- Minimum odds
- Minimum stake
- Max bonus value
- Eligible markets
- GGR/NGR/bonus cost

## Responsible-Gaming Audit
Check:
- Self-excluded users suppressed
- RG-risk users suppressed
- Cooling-off users suppressed
- Opt-in required
- No chasing losses
- No financial-solution framing
- No guaranteed-win claims
- No unapproved risk-free wording
- No manipulative reactivation
- No excessive urgency
- T&Cs visible
- RG review before launch

## Channel Audit
Check:
- SMS skill is SMS-specific
- Email and push are future skills, not mixed into SMS
- SMS includes character count logic
- SMS requires T&C handling
- SMS avoids complex mechanics
- Channel opt-in is checked

## Commercial Audit
Check:
- Bonus cost controlled
- Max bonus defined where relevant
- Minimum odds considered
- Minimum stake considered
- Eligible markets considered
- Sharp/arb exposure considered
- Bonus abuse considered
- VIP exposure controlled
- Incrementality considered
- NGR/GGR/bonus cost considered

## Output Quality Audit
Check:
- Output templates are practical
- Examples are placeholder-only
- Assumption labels are used
- Missing inputs are handled
- Launch readiness is clear
- Recommended next skills are clear

## Final Repo Audit
Check:
- README is accurate
- AGENTS.md is clear
- Manifest is valid JSON
- Docs align with actual skills
- No stale references
- No missing skill paths
- No future skills described as existing
- Suggested commit message included
