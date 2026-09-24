# Cleaning Log — Bellabeat Case Study

## Process Phase — Verification Results
Every number in this log comes from an executed notebook cell, not
from the Kaggle description.

- Dataset: Kaggle mount, two export folders; analysis uses the
  04.12.16-05.12.16 export — 18 CSV files, exact count verified
  (an earlier unverified count of 29 was corrected).
- Users: 33 in activity (Kaggle announces 30 — discrepancy
  documented; 33 used throughout); 24 in sleep, 14 in heart rate,
  8 in weight.
- Date range: 2016-04-12 to 2016-05-12, 31 distinct days, US date
  format confirmed by the data.
- Daily coverage: 940 rows / 33 users = 28.5 rows per user —
  engagement is irregular, days missing (behavioral fact, kept).

## Cleaning actions
- sleepDay: 3 exact-duplicate rows removed (identical values,
  export artifact): 413 -> 410; re-checked to 0 duplicates.
- weightLogInfo: EXCLUDED — 8 users of 33 (24%) cannot support any
  statistic. Kept as engagement finding (manual logging collapses
  to a tiny minority).
- heart rate: excluded (14 users, second-level granularity).
- minute-level Wide files: excluded — proven identical to Narrow
  (1,325,580 rows each), no information loss.
- Users without sleep data: NOT removed — absence is a behavioral
  finding (night wearing).

## Aggregation discipline
- Mixed date/time formats detected across files; all day-level
  comparisons use normalized dates (.dt.normalize()). An initial
  "56 distinct days" in the weight file was diagnosed as 56
  timestamps, not days — corrected to 31.

## Key structural finding (feeds Analyze)
Sleep adoption among 33 daily-active users:
- 9 never wore the device at night (27%)
- 9 tried and abandoned within ~a week (27%)
- 4 irregular night wearers (12%)
- 10 regular night wearers, 25-31 of 31 nights (30%)
Sleep tracking is the most abandoned metric of this tracker.
