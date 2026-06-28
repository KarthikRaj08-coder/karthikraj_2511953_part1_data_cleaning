# Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

## Business Context
A subscription-based digital product company tested a new onboarding and activation campaign. Users were split into two groups:

- Control: Existing onboarding experience
- Treatment: New campaign experience

Leadership needs to decide whether the Treatment experience should be launched to all users.

## Dataset Description
The dataset contains 1408 users and includes experiment group, signup date, region, device type, traffic source, plan type, user journey flags, 30-day revenue, support tickets, refund requests, days to convert, and engagement score.

## Business Problem Statement
The company needs to decide whether the new onboarding and activation campaign should be launched to all users. This decision impacts new users, product teams, marketing teams, support teams, and revenue performance.

The main metric expected to improve is paid conversion rate. However, the company must monitor risks such as higher refund requests, more support tickets, lower engagement, slower conversion, or poor segment-level performance.

Before recommending launch, we need evidence that Treatment improves paid conversion meaningfully versus Control, and that guardrail metrics do not show serious negative impact.

## North Star Metric Selected
The selected North Star metric is **Paid Conversion Rate**.

Paid conversion rate was selected because the campaign is intended to move users from onboarding/trial into paid subscription. It directly connects campaign performance to business growth.

Other metrics such as landing page visit rate, trial start rate, onboarding completion rate, engagement score, and revenue are supporting metrics because they explain the journey but are not the final business outcome.

Optimizing only for paid conversion rate can be risky because it may create low-quality conversions, higher refunds, more support tickets, or poor long-term retention.

## KPI Tree Summary
The KPI tree breaks Paid Conversion Rate into three primary drivers:

1. Acquisition quality
2. Activation journey
3. Monetization quality

Guardrail metrics include refund rate, support ticket rate, engagement score, days to convert, and segment-level decline.

See:
- `outputs/kpi_tree.png`
- `screenshots/kpi_tree_preview.png`

## Experiment Analysis Approach
The analysis included:

- Missing value checks
- Group count checks
- Duplicate user ID checks
- Invalid binary value checks
- Revenue outlier checks
- Segment distribution checks
- Control vs Treatment metric comparison
- Segment-level analysis by region, device type, traffic source, and plan type

## Data Cleaning Notes
- Duplicate user IDs found: 8
- Invalid binary values found: 0
- `days_to_convert` is missing for non-converted users, which is expected.
- Missing engagement scores were excluded from engagement average calculation.
- Revenue outlier detection using the IQR rule flagged 72 records because revenue is zero-inflated. These were not removed because positive revenue is expected only for converted users and may represent genuine business outcomes.

## Hypothesis Test Summary
A one-tailed two-proportion z-test was used to test whether Treatment paid conversion rate is higher than Control.

| Metric | Value |
|---|---:|
| Control conversion rate | 3.17% |
| Treatment conversion rate | 6.99% |
| Absolute lift | 3.82% |
| Relative lift | 120.28% |
| Z statistic | 3.2519 |
| P-value | 0.000573 |

Since the p-value is below 0.05, the conversion improvement is statistically significant.

## Guardrail Metrics Considered
Guardrails considered:

- Refund rate
- Support ticket rate
- Engagement score
- Days to convert
- Revenue per converted user
- Segment-level decline

Guardrail concerns were found because support ticket rate increased and refund rate increased in Treatment.

## Final Recommendation
**Launch only for selected segment / phased rollout.**

Treatment significantly improves conversion, but a full launch is risky because support ticket rate increased from 14.72% to 24.76%, and refund rate increased from 0.00% to 0.42%.

## Assumptions and Limitations
- The analysis uses 30-day outcomes only.
- Long-term retention data is unavailable.
- Segment-level sample sizes may be smaller.
- Revenue is zero-inflated because most users did not convert.
- No external market or seasonality adjustment was applied.

## Screenshots Included
- `screenshots/summary_metrics.png`
- `screenshots/hypothesis_test_output.png`
- `screenshots/kpi_tree_preview.png`

## Repository Structure
```text
part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
├── outputs/
│   ├── kpi_tree.png
│   ├── experiment_summary.xlsx
│   └── recommendation_memo.md
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
└── README.md
```
