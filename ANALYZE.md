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

## 3. Finding 1 — Sleep tracking is the most fragile feature

Sleep adoption among the 33 daily-active users, from the exhaustive
classification defined in the CLEANING_LOG:

| Night-wearing group | Users | Share | Definition (stated in code) |
|---|---|---|---|
| Never worn at night | 9 | 27% | zero recorded nights |
| Tried, then abandoned | 3 | 9% | 1-5 nights, then stopped permanently |
| Irregular night wearers | 11 | 33% | 2-24 nights, spread across the month |
| Regular night wearers | 10 | 30% | 25-31 of the 31 study nights |

Of the 24 users who ever recorded a night, fewer than half became
regular night wearers. Interest is common (73% try sleep tracking at
least once); the habit is rare (30% keep it). The four classes sum to
exactly 33 — the classification is exhaustive and auditable.

## 4. Finding 2 — Sleep abandonment marks the only declining users

The decisive result is what happens to the 3 abandoners:

- Their average daily activity is 2,718 steps — about a third of every
  other segment (7,683-8,474 steps).
- Their weekly trajectory fell from 3,592 steps/day in week 1 to 1,965
  in week 3 (-45% at the trough), stabilizing at -12% below their
  starting level by week 4.
- Every other segment held or grew its activity over the same window:
  Engaged day-only -3%, Completes +19%, Inconsistent +24%.

Three precisions, required by honesty:

- The never-night-wearers are NOT disengaged: their daytime activity
  (7,860 steps/day) is within 8% of the regular wearers (8,474). They
  simply decline night wearing (comfort, habit, overnight charging are
  plausible causes — the data shows the gap, not the reason).
- The declining pattern rests on 3 of 33 users: small-n, observational.
- Causality is not established: sleep abandonment and activity decay
  co-occur; a common cause is not excluded. Night-wearing abandonment
  is an early MARKER of disengagement — nothing more is claimed.

## 5. Finding 3 — Four user segments, not one audience

Segmentation built on two behavioral variables: night-wearing adoption
(nights tracked out of 31) and activity trajectory (week 4 vs week 1).

| Segment | Share | Day behavior | Night behavior |
|---|---|---|---|
| Completes | 30% | 8,474 steps/day, most structured, +19% trend | adopted sleep tracking |
| Inconsistent | 33% | 7,683 steps/day, active when present | 2-24 nights, intermittent |
| Engaged day-only | 27% | 7,860 steps/day — matches the completes | never worn at night |
| Decayers | 9% | 2,718 steps/day, declining | abandoned within days |

Insight: the "average user" does not exist in this data — one marketing
message cannot speak to all four. The largest single block (33%) is the
intermittent night-wearers: sustained interest, no habit — the
activation opportunity. The decayers need re-engagement; the engaged
day-only need a reason to wear the device at night; the completes are
the platform's advocates. Segment definitions feed every recommendation
of the Share phase.

## 6. Finding 4 — Reality sits far below the industry benchmarks

- Only **40% of user-days** reach 10,000 steps for the most engaged
  segment (Completes) — **2%** for the decayers (Inconsistent 36%,
  Engaged day-only 29%).
- **44% of recorded nights** are under 7 hours of sleep — and that
  counts only the motivated sleep-trackers, not the 27% who never
  tracked sleep at all.

Insight: for most user-days, the "meet your goals" promise is not met.
This gap between marketing benchmarks and actual behavior is not a
failure of users; it is the industry's unaddressed tension.

## 7. Finding 5 — Two natural contact windows in every day

Hourly intensity (hourlyIntensities, 33 users): activity peaks at
**6 pm** (mean intensity 21.7 across 17:00-19:59) and collapses **53%**
after 8 pm. Two windows sit outside the peak and combine availability
with comparatively low activity:

- the lunch plateau (12:00-14:00, intensity 19.3)
- the evening wind-down (20:00-22:00, intensity 13.2, close to the
  daily mean of 12.1)

These are the natural moments for a daily recap or a gentle prompt —
not the moments of an aggressive push.

## 8. From Findings to Insights — Handoff to Share

| Finding (this file) | Insight | Feeds recommendation |
|---|---|---|
| Only the 3 sleep-abandoners declined (-12%; -45% at trough); regulars rose +19% | Night-wearing is the retention KPI | R1 — sleep as onboarding gateway |
| 27% engaged day-only never wear the device at night | Cleanest single conversion gap | R2 — night comfort positioning |
| 60% of user-days miss 10k steps even for the top segment; 44% of nights < 7 h | The perfectionist promise is unmet | R3 — position against perfectionism |
| Two windows outside the activity peak (12-14, 20-22) | Contact timing is measurable | R1/R3 — gentle prompts at 12-14 and 20-22 |
| 33% are intermittent night-wearers | Interest exists, habit does not | R1 — habit-building content target |

Each recommendation in the Share phase quotes its behavioral basis from
this table and carries its stated limit.

## 9. What This Analysis Does NOT Claim

- It does not describe Bellabeat's actual customers — the sample is 33
  US Mechanical Turk workers from 2016, gender undocumented.
- It does not establish causality — markers and co-occurrence only;
  the declining pattern rests on 3 of 33 users.
- It does not measure sleep quality — accelerometer sleep detects
  immobility; durations are overestimates by construction.
- It does not describe the 2026 market — durable behavioral structures
  only; market claims are sourced separately in Share.

## 10. Deliverable Status

Success criteria from the Ask phase, checked: at least 3 behavioral
insights backed by a metric — 5 findings delivered; each insight
converts to one recommendation with its limit explicit — done in
Share; report written for a non-technical reader — done in the main
report.

Full analytical chain: ASK.md → PREPARE.md → CLEANING_LOG.md → this
file → Share report + SOURCES.md, with the notebook behind every
number.
