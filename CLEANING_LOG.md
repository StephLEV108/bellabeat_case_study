# Cleaning Log — Bellabeat Case Study

## Process Phase — Verification Results
Every number in this log comes from an executed notebook cell, not
from the Kaggle description.

- Dataset: Kaggle mount, two export folders (mturkfitbit_export_
  03.12.16-04.11.16 and mturkfitbit_export_04.12.16-05.12.16); analysis
  uses the 04.12.16-05.12.16 export — 18 CSV files, exact count
  machine-verified.
- Users: 33 in activity (Kaggle announces 30 — discrepancy documented;
  33 used throughout); 24 in sleep, 14 in heart rate, 8 in weight.
- Date range: 2016-04-12 to 2016-05-12, 31 distinct days, US date
  format confirmed by the data.
- Daily coverage: 940 rows / 33 users = 28.5 rows per user — engagement
  is irregular, days missing (behavioral fact, kept).

## Cleaning actions
- sleepDay: 3 exact-duplicate rows removed (identical values, export
  artifact): 413 → 410; re-checked to 0 duplicates.
- weightLogInfo: EXCLUDED — 8 users of 33 (24%) cannot support any
  statistic. Kept as engagement finding (manual logging collapses to a
  tiny minority).
- heart rate: excluded (14 users, second-level granularity).
- minute-level Wide files: excluded — redundant with Narrow (same
  content, no information loss).
- Users without sleep data: NOT removed — absence is a behavioral
  finding (night wearing), not a defect to silently drop.

## Aggregation discipline
- Mixed date/time formats detected across files; all day-level
  comparisons use normalized dates. An initial "56 distinct days" in
  the weight file was diagnosed as 56 timestamps, not days — corrected
  to 31.
- Weekly trajectory: study week 1 (days 1-7) vs study week 4 (days
  22-28), both full weeks; week 5 is partial (3 days) and excluded from
  trajectory claims. 4 of 33 users have no week-1 or week-4 data and
  therefore no measurable trajectory (excluded from trajectory means,
  kept in the data).

## Sleep-adoption classification — rules stated explicitly
The segmentation is ordered, exhaustive and auditable: every one of
the 33 users falls in exactly one class, and the rule is stated in
code:

| Class | Rule (in execution order) | Users | Share |
|---|---|---|---|
| never | zero recorded nights | 9 | 27% |
| regular | at least 25 of the 31 study nights tracked | 10 | 30% |
| abandoned | last recorded night at least 14 days before study end | 3 | 9% |
| irregular | every remaining night-wearer (2-24 nights, spread across the month) | 11 | 33% |

Sum: 33 of 33 users. The three abandoners tracked 1, 3 and 5 nights
respectively, then stopped permanently; their full per-user table is
printed by the notebook.

## Key structural finding (feeds Analyze)
Sleep adoption among 33 daily-active users:
- 9 never wore the device at night (27%)
- 3 tried and abandoned within days (9%)
- 11 irregular night wearers (33%)
- 10 regular night wearers, 25-31 of 31 nights (30%)
Of the 24 users who ever recorded a night, fewer than half became
regular night wearers. Sleep tracking is the most fragile metric of this
tracker — interest is common (73% try), the habit is rare (30% keep).

