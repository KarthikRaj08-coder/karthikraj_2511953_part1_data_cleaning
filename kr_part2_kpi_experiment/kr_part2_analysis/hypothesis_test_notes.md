# Hypothesis Test Notes

## Metric Being Tested
Paid conversion rate.

## Why This Metric Was Chosen
Paid conversion rate is the primary success metric because the new onboarding and activation campaign is meant to convert more users into paying subscribers.

## Null Hypothesis
H0: Treatment paid conversion rate is less than or equal to Control paid conversion rate.

## Alternate Hypothesis
H1: Treatment paid conversion rate is greater than Control paid conversion rate.

## Test Type
One-tailed two-proportion z-test.

This is one-tailed because the business question is directional: leadership wants to know whether the Treatment experience improves conversion versus Control.

## Significance Level
5% or 0.05.

## Test Inputs

| Input | Value |
|---|---:|
| Control users | 693 |
| Control converted users | 22 |
| Control conversion rate | 3.17% |
| Treatment users | 715 |
| Treatment converted users | 50 |
| Treatment conversion rate | 6.99% |
| Absolute lift | 3.82% |
| Relative lift | 120.28% |

## Test Output

| Output | Value |
|---|---:|
| Pooled conversion rate | 0.0511 |
| Standard error | 0.0117 |
| Z statistic | 3.2519 |
| One-tailed p-value | 0.000573 |

## Decision Rule
If p-value < 0.05, reject the null hypothesis.

## Statistical Interpretation
The p-value is 0.000573, which is below 0.05. Therefore, we reject the null hypothesis.

## Business Interpretation
The Treatment group shows a statistically significant improvement in paid conversion rate versus Control. However, the launch decision should also consider guardrail metrics such as refund rate, support ticket rate, engagement score, days to convert, and revenue quality.
