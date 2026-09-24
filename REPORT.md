# Bellabeat: Turning Sleep into the Gateway to Retention
## How smart device behavior reveals three marketing opportunities

*Analysis report — Marketing Analytics team*
*Prepared for: Urška Sršen (CCO), Sando Mur, executive team*

---

## 1. The question

Bellabeat sells holistic wellness to women — but most women who
buy a wellness product do not become wellness users. This analysis
asks: how do smart health device users actually behave, and what
behaviors should Bellabeat's marketing target to convert casual
consumers into engaged platform users?

The analysis covers the Bellabeat app as the convergence point of
all metrics, with the Leaf as the flagship hardware.

## 2. Method, in three paragraphs

We analyzed one month (April 12 - May 12, 2016) of fitness tracker
data from 33 US users, collected via Amazon Mechanical Turk and
distributed on Kaggle (CC0 license). Before any analysis, every
file was audited: user counts, duplicates, date ranges, and file
redundancy — documented in the notebook and its cleaning log.

The data has strict limits, declared upfront: 33 users is not a
population; gender is not documented; 2016 is not 2026. We
therefore did not use this data to describe the market. We used it
to identify DURABLE BEHAVIORAL STRUCTURES — user segments, wearing
patterns, engagement dynamics — which change slowly because they
are rooted in human nature, not in technology.

Every behavioral finding below is a FACT from this dataset. Every
market claim is sourced separately (see Sources) and every
recommendation is framed as a hypothesis to validate on Bellabeat's
own user data — never as a certainty.

## 3. What the data shows

### 3.1 Sleep tracking is the most abandoned feature — and its
abandonment predicts total disengagement

Of 33 users active by day:
- 9 (27%) never wore the device at night
- 9 (27%) tried sleep tracking and dropped it within ~a week
- 4 (12%) wore it irregularly
- 10 (30%) became regular night wearers

!Night wearing

The decisive finding is what happens AFTER abandonment. Users who
dropped sleep tracking saw their daily activity decay 35% in three
weeks, while all other segments held their level within ~10% over
the whole month.

!Weekly activity by segment

Night-wearing is an early marker of overall disengagement. The
users who never wore the device at night are NOT disengaged —
their daytime activity matches the regulars — they simply decline
night wearing (comfort, habit, charging are the plausible causes;
the data shows the gap, not the reason).

### 3.2 Four user segments, not one audience

| Segment | Share | Day behavior | Night behavior |
|---|---|---|---|
| Completes | 30% | most active, most structured | adopted sleep tracking |
| Engaged day-only | 27% | as active as completes | refuse night wearing |
| Inconsistent | 12% | active when present | intermittent |
| Decayers | 27% | lowest activity, decaying | abandoned early |

One marketing message cannot speak to all four. The decayers need
re-engagement; the day-only engaged need a reason to wear the
device at night; the completes are the platform's advocates.

### 3.3 Reality sits far below the benchmarks the industry promises

- Only 32% of user-days reach 10,000 steps for even the most
  engaged segment (6% for decayers).
- 44% of recorded nights are under 7 hours of sleep — and that
  counts only the motivated sleep-trackers.

!Promise vs reality

For most user-days, the promise "meet your goals" is not met. This
gap between marketing benchmarks and actual behavior is not a
failure of users — it is the industry's unaddressed tension.

### 3.4 Two natural contact windows exist in every day

!Contact windows

Activity peaks at 6 pm and collapses after 8 pm. Two windows
combine availability and low activity: the lunch plateau (12-14)
and the evening (20-22) — the natural moments for a daily recap
or a gentle prompt, not the moments of an aggressive push.

## 4. Three recommendations

### R1 — Make sleep the onboarding gateway, not a bonus feature

The behavior: sleep abandonment predicts total disengagement.
The market: sleep tracking is a USD 26.6B market (2024) projected
to USD 58-68B by 2030-2032 (double-digit growth); sleep quality
now outranks hour-counting.
The action: onboard every new Bellabeat app user through sleep
from day one — the Leaf as a night companion first, an activity
tracker second. Track night-wearing adoption as THE retention
KPI, ahead of daily steps.
The limit: 33 users, 2016, causality not established — validate
on Bellabeat's own longitudinal data.

### R2 — Target the engaged day-only user with night comfort

The behavior: 27% of users are fully engaged by day and decline
night wearing — the single largest conversion gap in the data.
The market: discreet form factors are winning structurally —
smart ring shipments up 49% in 2025 vs 6% for smartwatches (IDC);
Oura holds 74% of that market (Omdia).
The action: position the Leaf for this segment explicitly —
jewelry you sleep in, not a wristband you tolerate. Marketing
message: comfort and discretion at night, full insight in the
morning.
The limit: the data shows the behavior gap, not the product
preference; the market data shows the trend, not Bellabeat's
fit.

### R3 — Position against perfectionism

The behavior: most user-days miss every benchmark; the gap
between promise and reality is permanent for the majority.
The market: a documented tension exists between self-tracking
and anxiety (systematic reviews, NIH-indexed); the wellness
conversation is moving from performance to accompaniment. Add
the under-served perimenopause segment: ~1 billion women in
perimenopause by 2030, and ~70% do not know what perimenopause
is (Clue) — an educational gap no major brand owns.
The action: Bellabeat's voice should say "listen to your body,
we help you understand it" — not "hit your targets." Build the
perimenopause education content line: first-mover space, aligned
with the 29-31 year average age at first birth and rising.
The limit: positioning strength depends on brand execution;
the perimenopause data points are trend-level, not
Bellabeat-validated.

## 5. What this analysis does NOT claim

- It does not describe Bellabeat's actual customers — the sample
  is 33 US Mechanical Turk workers from 2016, gender undocumented.
- It does not establish causality — sleep abandonment and activity
  decay co-occur; a common cause is not excluded.
- It does not measure sleep quality — accelerometer sleep detects
  immobility; durations are overestimates by construction.
- It does not validate the 2026 market recommendations — each is
  a hypothesis to test on Bellabeat's own user data, and each
  carries its stated limit.

## 6. Appendix — full analytical chain

Every number in this report traces to an executed notebook cell:
- ASK.md — business question, analytical questions, scope
- PREPARE.md — source identification, expectations and verdicts
- CLEANING_LOG.md — audit results and cleaning decisions
- ANALYZE.md — findings, insights, segment definitions
- SOURCES.md — all market sources with origin and date
- Notebook — all executed cells, all figures

Data: FitBit Fitness Tracker Data (Möbius, Kaggle, CC0), 33 users
verified, 2016-04-12 to 2016-05-12.
