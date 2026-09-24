# Phase 2: Prepare — Data Sources and Credibility

## 1. Primary Source — Precise Identification
- Dataset: FitBit Fitness Tracker Data
- Platform: Kaggle (uploaded by Möbius):
  https://www.kaggle.com/datasets/arashnic/fitbit
- License: CC0 Public Domain — free use, including commercial
- Origin: survey distributed via Amazon Mechanical Turk, conducted
  between March 12, 2016 and May 12, 2016 (dates in US format,
  MM.DD.YYYY — ambiguity noted and resolved), with 30 consenting
  FitBit users
- Structure: 18 CSV files verified by inspection (the export folder
  04.12.16-05.12.16; an earlier unverified count of 29 has been
  corrected), across two export windows (03.12.16-04.11.16 and
  04.12.16-05.12.16)
- Content: physical activity, heart rate, sleep, calories, 
  intensity, steps, METs, manual weight logs
- Format: long format — records identified by user Id + timestamp

## 2. Measurement Validity (what each column actually measures)
Declared before analysis, because sensor limits bound what insights
may claim:
- Steps: wrist-accelerometer step detection — no swimming, cycling,
  or stroller-pushing steps are counted.
- Calories: algorithmic estimate from heart rate and activity, not a
  measurement.
- Sleep: accelerometer-based — detects immobility, not sleep; a
  motionless awake person is counted as asleep.
- Heart rate: optical sensor, second-level — reliable at rest,
  less so during high-intensity movement.
- Weight/BMI: manual entry — self-reported, not measured.

## 3. Files Selected for Analysis — and Why
| File | Content | Granularity |
|---|---|---|
| dailyActivity_merged.csv | Daily activity (steps, distances, calories, intensities) | 1 row/user/day |
| sleepDay_merged.csv | Daily sleep (time in bed, asleep time) | 1 row/user/day |
| hourlyIntensities_merged.csv | Hourly intensity | 1 row/user/hour |

Excluded, with proof from the Process audit:
- weightLogInfo_merged.csv: 8 users of 33 (24%) — cannot support any
  statistic. Retained only as an engagement finding.
- heartrate_seconds_merged.csv: 14 users, second-level granularity.
- minute-level Narrow/Wide files: Wide files duplicate Narrow content
  (identical 1,325,580 rows) — no information loss.

Decision documented; reversible if a question requires finer
granularity.

## 4. ROCCC Evaluation — With Consequences
| Criterion | Verdict | Consequence for this analysis |
|---|---|---|
| Reliable | Medium — 33 users (verified), not representative | No population-level claims; subgroups only |
| Original | Low — second-hand data via Mechanical Turk, not from Bellabeat customers | Selection bias disclosed; treated as behavior of engaged tracker users, not buyers |
| Comprehensive | Medium — activity/sleep/heart rate present; NO gender, age, cycle | Extrapolation to Bellabeat's female target is a hypothesis, never a finding |
| Current | Low — 2016 data, one month (2016-04-12 to 2016-05-12, verified) | Market descriptions forbidden; durable behavioral structures only |
| Cited | Good — attribution (Furberg, Brinton, Keating, Ortiz), license CC0 | Full sourcing in Share phase |

Overall consequence: the dataset is usable for STRUCTURE discovery,
not for MARKET description. This is the methodological decision
stated in the Ask phase, now grounded in verified evidence.

## 5. Completeness Audit (executed and confirmed in the notebook)
- Unique users per file: 33 activity / 24 sleep / 14 heart rate /
  8 weight — each gap is itself a finding, not a defect.
- The Kaggle description announces 30 users; the verified count is
  33. The discrepancy is documented; 33 is used throughout.
- Duplicates: 3 exact-duplicate rows in sleepDay removed and
  re-verified to zero. Activity and weight: zero duplicates.
- Date range: 2016-04-12 to 2016-05-12, 31 distinct days, US format
  confirmed by the data.
- Sleep coverage is the key behavioral gap: of 33 daily-active users,
  9 never wore the device at night, 9 tried and abandoned, 10 are
  regular night wearers. Missing sleep data is a finding about
  night wearing, not a defect to silently drop.

## 6. Selection Bias — Declared
Mechanical Turk participants are volunteers, potentially more
tech-engaged than the average consumer, and compensated. They are
also NOT Bellabeat customers and their gender is undocumented.
Every downstream insight inherits these three biases and will carry
them in its stated limits.

## 7. Privacy and Security
- CC0 license; user Ids are hashed, no directly identifying data.
- Residual risk noted: 31 days of second-level heart rate data is
  high-resolution behavioral data; re-identification of survey
  participants is theoretically possible — data will be reported
  only in aggregate, never per individual.

## 8. Data Integrity Verification Plan
Executed and documented in the Process phase of the notebook; full
results in CLEANING_LOG.md:
- unique Id counts per file: done
- duplicate Id+date checks: done (3 removed, verified to zero)
- date range checks per file: done (31 days confirmed)
- reconciliation of the two export windows: done (the 04.12-05.12
  export, 18 files, is used for analysis)
