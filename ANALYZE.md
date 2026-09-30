# Phase 4: Analyze — Bellabeat Case Study

## 1. Purpose and Method

This phase turns the verified data of the Process phase into findings.
Every number below comes from an executed notebook cell and traces back
to the CLEANING_LOG — none from the Kaggle description.

Two-layer discipline, restated: every statement in this document is a
FACT from this dataset (33 US users, 2016-04-12 to 2016-05-12). Market
interpretation, segment targeting and recommendations belong to the
Share phase, framed as sourced hypotheses — never as findings.

## 2. Analytical Questions

1. How does night-wearing relate to overall engagement?
2. How many distinct audiences does the data actually contain?
3. How far does real behavior sit from the benchmarks the industry promises?
4. When during the day are users actually available for contact?

## 3. Finding 1 — Sleep tracking is the most abandoned feature

Sleep adoption among the 33 daily-active users, from the Process audit:

| Night-wearing group | Users | Share |
|---|---|---|
| Never wore the device at night | 9 | 27% |
| Tried sleep tracking, abandoned within ~1 week | 9 | 27% |
| Irregular night wearers | 4 | 12% |
| Regular night wearers (25-31 of 31 nights) | 10 | 30% |

More than half of daily-active users either never adopted sleep
tracking or dropped it within a week. Sleep is the most abandoned
metric of this tracker — and, as Finding 2 shows, its abandonment
is not an isolated behavior.

## 4. Finding 2 — Sleep abandonment predicts total disengagement

The decisive result is what happens AFTER abandonment:

- Users who dropped sleep tracking saw their daily activity decay
  **35% over three weeks**.
- All other segments held their activity level within **~10%** across
  the whole month.

Two precisions, required by honesty:

- The never-night-wearers are NOT disengaged: their daytime activity
  matches the regular night wearers. They simply decline night
  wearing (comfort, habit, overnight charging are plausible causes —
  the data shows the gap, not the reason).
- Causality is not established: sleep abandonment and activity decay
  co-occur; a common cause is not excluded. Night-wearing is an early
  MARKER of disengagement — nothing more is claimed.

## 5. Finding 3 — Four user segments, not one audience

Segmentation built on two behavioral variables: night-wearing adoption
(nights tracked out of 31) and activity trajectory (weekly decay).

| Segment | Share | Day behavior | Night behavior |
|---|---|---|---|
| Completes | 30% | most active, most structured | adopted sleep tracking |
| Engaged day-only | 27% | as active as the completes | refuse night wearing |
| Inconsistent | 12% | active when present | intermittent |
| Decayers | 27% | lowest activity, decaying | abandoned early |

Insight: the "average user" does not exist in this data — one
marketing message cannot speak to all four. The decayers need
re-engagement; the engaged day-only need a reason to wear the device
at night; the completes are the platform's advocates. Segment
definitions feed every recommendation of the Share phase.

## 6. Finding 4 — Reality sits far below the industry benchmarks

- Only **32% of user-days** reach 10,000 steps for the most engaged
  segment — **6%** for the decayers.
- **44% of recorded nights** are under 7 hours of sleep — and that
  counts only the motivated sleep-trackers, not the 27% who never
  tracked sleep at all.

Insight: for most user-days, the "meet your goals" promise is not
met. This gap between marketing benchmarks and actual behavior is
not a failure of users; it is the industry's unaddressed tension.

## 7. Finding 5 — Two natural contact windows in every day

Hourly intensity (hourlyIntensities, 33 users): activity peaks at
**6 pm** and collapses after **8 pm**. Two windows combine
availability and low activity:

- the lunch plateau (12:00-14:00)
- the evening (20:00-22:00)

These are the natural moments for a daily recap or a gentle prompt —
not the moments of an aggressive push.

## 8. From Findings to Insights — Handoff to Share

| Finding (this file) | Insight | Feeds recommendation |
|---|---|---|
| Sleep abandonment precedes 35% activity decay | Night-wearing is the retention KPI | R1 — sleep as onboarding gateway |
| 27% engaged day-only refuse night wearing | Largest single conversion gap | R2 — night comfort positioning |
| Most user-days miss every benchmark | The perfectionist promise is unmet | R3 — position against perfectionism |
| Two low-activity daily windows | Contact timing is measurable | R1/R3 — gentle prompts at 12-14 and 20-22 |

Each recommendation in the Share phase quotes its behavioral basis
from this table and carries its stated limit.

## 9. What This Analysis Does NOT Claim

- It does not describe Bellabeat's actual customers — the sample is
  33 US Mechanical Turk workers from 2016, gender undocumented.
- It does not establish causality — markers and co-occurrence only.
- It does not measure sleep quality — accelerometer sleep detects
  immobility; durations are overestimates by construction.
- It does not describe the 2026 market — durable behavioral
  structures only; market claims are sourced separately in Share.

## 10. Deliverable Status

Success criteria from the Ask phase, checked: at least 3 behavioral
insights backed by a metric — 5 findings delivered; each insight
converts to one recommendation with its limit explicit — done in
Share; report written for a non-technical reader — done in the
main report.

Full analytical chain: ASK.md → PREPARE.md → CLEANING_LOG.md →
this file → Share report + SOURCES.md, with the notebook behind
every number.
