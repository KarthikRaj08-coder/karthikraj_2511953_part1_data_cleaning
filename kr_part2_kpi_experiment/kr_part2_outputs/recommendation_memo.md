# Recommendation Memo

## Executive Summary
The new onboarding and activation campaign materially improved paid conversion rate versus the existing onboarding experience. Treatment conversion was 6.99% compared with Control conversion of 3.17%, an absolute lift of 3.82% and a relative lift of 120.28%. The hypothesis test shows this improvement is statistically significant with a p-value of 0.000573.

However, the Treatment group also showed guardrail concerns. Support ticket rate increased from 14.72% to 24.76%, and refund rate increased from 0.00% to 0.42%. Therefore, the recommended decision is: **Launch only for selected segment / phased rollout**, rather than an immediate full launch to all users.

## North Star Metric
The North Star metric is **Paid Conversion Rate**.

This is the right primary metric because the campaign is designed to convert users into paying subscribers. It directly connects onboarding success with revenue growth.

## KPI Tree Explanation
Paid conversion rate is driven by:
1. Acquisition quality
2. Activation journey
3. Monetization quality

Guardrail metrics include refund rate, support ticket rate, engagement score, days to convert, and segment-level decline.

## Experiment Result Summary

| Metric | Control | Treatment | Difference |
|---|---:|---:|---:|
| Users | 693 | 715 | 22 |
| Landing page visit rate | 63.64% | 72.59% | 8.95% |
| Trial start rate | 25.11% | 29.09% | 3.98% |
| Onboarding completion rate | 15.58% | 21.26% | 5.67% |
| Paid conversion rate | 3.17% | 6.99% | 3.82% |
| ARPU | ₹51.75 | ₹53.88 | ₹2.13 |
| Revenue per converted user | ₹1630.10 | ₹770.41 | ₹-859.69 |
| Refund rate | 0.00% | 0.42% | 0.42% |
| Support ticket rate | 14.72% | 24.76% | 10.04% |
| Engagement score | 57.0 | 62.9 | 5.9 |
| Days to convert | 8.9 | 6.4 | -2.5 |

## Hypothesis Test Interpretation
A one-tailed two-proportion z-test was used to compare Control and Treatment paid conversion rates. The p-value was 0.000573, below the 0.05 significance level. This means Treatment's conversion improvement is statistically significant.

## Guardrail Analysis
The campaign improves the main success metric, but guardrails create risk:

- Refund rate increased from 0.00% to 0.42%.
- Support ticket rate increased from 14.72% to 24.76%.
- Revenue per converted user fell from ₹1630.10 to ₹770.41, suggesting the campaign may be converting more lower-value users.
- Engagement score improved from 57.0 to 62.9.
- Days to convert improved from 8.9 to 6.4.

## Segment-Level Insight
Segment analysis should be used to identify where Treatment improves conversion without worsening support tickets, refunds, or revenue quality. The workbook includes segment cuts by region, device type, traffic source, and plan type.

## Final Recommendation
**Launch only for selected segment / phased rollout.**

The Treatment should not be blindly launched to all users immediately. The conversion improvement is strong and statistically significant, but support tickets and refunds increased. A phased rollout allows the business to capture upside while monitoring customer experience and revenue quality.

## Risks and Limitations
- The experiment measures only early 30-day outcomes.
- Long-term retention is not available.
- Revenue is zero-inflated because most users do not convert.
- Some converted users may generate unusually high revenue, affecting revenue averages.
- Segment-level sample sizes may be smaller and should be interpreted carefully.

## Next Steps
1. Roll out Treatment to the best-performing segments first.
2. Monitor support tickets and refunds daily after launch.
3. Investigate why support tickets increased.
4. Track 60-day and 90-day retention.
5. Refine the onboarding campaign to reduce confusion and refund risk.
