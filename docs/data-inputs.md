# Data Inputs

This pack works best when inputs are supplied at runtime. Do not infer market facts, customer behaviour, campaign performance, or local rules from memory.

## Customer Inputs
- [TARGET_MARKET]
- [TARGET_LANGUAGE]
- [CUSTOMER_LIFECYCLE_STAGE]
- [CUSTOMER_VALUE_SEGMENT]
- [VIP_STATUS]
- [BONUS_SENSITIVITY]
- [CHURN_RISK]
- [RG_RISK_STATUS]
- [SELF_EXCLUSION_STATUS]
- [COMMUNICATION_OPT_IN_STATUS]
- [PREFERRED_SPORT]
- [PREFERRED_LEAGUE]
- [PREFERRED_TEAM]
- [PREFERRED_BET_TYPE]
- [PRE_MATCH_OR_LIVE_PREFERENCE]
- [SINGLE_OR_ACCUMULATOR_PREFERENCE]
- [AVERAGE_STAKE]
- [DEPOSIT_BEHAVIOUR]
- [LAST_ACTIVE_DATE]
- [LAST_DEPOSIT_DATE]
- [BONUS_HISTORY]
- [SHARP_OR_ARB_RISK]

## Campaign Inputs
- [CAMPAIGN_OBJECTIVE]
- [TARGET_CHANNEL]
- [TARGET_SEGMENT]
- [TARGET_SPORT]
- [TARGET_EVENT]
- [TARGET_TOURNAMENT]
- [TARGET_FIXTURE]
- [OFFER_MECHANIC]
- [OFFER_VALUE]
- [MINIMUM_STAKE]
- [MINIMUM_ODDS]
- [MAX_BONUS_VALUE]
- [EXPIRY]
- [ELIGIBLE_MARKETS]
- [CTA]
- [T&CS]
- [T&CS_LINK]
- [BRAND_NAME]
- [BRAND_TONE]
- [REGULATORY_NOTES]
- [SUPPRESSION_RULES]
- [FREQUENCY_CAPS]

## Journey Inputs
- [JOURNEY_TRIGGER]
- [JOURNEY_STEPS]
- [EXIT_CRITERIA]
- [CONTROL_GROUP]
- [FREQUENCY_CAPS]
- [EVENT_DATE]
- [EVENT_START_TIME]

## Testing Inputs
- [TEST_HYPOTHESIS]
- [VARIANT_A]
- [VARIANT_B]
- [PRIMARY_KPI]
- [SECONDARY_KPIS]
- [GUARDRAIL_METRICS]
- [MEASUREMENT_WINDOW]
- [DECISION_RULE]
- [SAMPLE_SIZE]
- [SEGMENT_SIZE]

## Performance Inputs
- [DELIVERY_RATE]
- [OPEN_RATE]
- [CLICK_RATE]
- [OPT_OUT_RATE]
- [DEPOSIT_CONVERSION]
- [BET_CONVERSION]
- [OFFER_UPTAKE]
- [BONUS_UPTAKE]
- [TURNOVER]
- [GGR]
- [NGR]
- [BONUS_COST]
- [INCREMENTAL_REVENUE]
- [RETENTION_UPLIFT]
- [CHURN_REDUCTION]
- [COMPLAINTS]
- [POST_CAMPAIGN_RG_FLAGS]
- [CONTROL_GROUP_RESULTS]
- [VARIANT_RESULTS]
- [CAMPAIGN_RESULTS]

## Input Quality Rules
- Use [CONFIRMED] for user-supplied facts.
- Use [ASSUMPTION] for reasonable but unconfirmed assumptions.
- Use [NEEDS CONFIRMATION] for missing critical inputs.
- Use [RISK] for compliance, RG, commercial, UX, brand, data-quality, or operational concerns.
- Use [RECOMMENDATION] for proposed action.
- Do not invent market facts.
- Do not invent campaign performance.
- Do not infer local regulatory requirements without supplied [REGULATORY_NOTES] or confirmed research.
- Do not treat missing data as zero.
- Do not claim causality without valid comparison data.
