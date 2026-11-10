# Pressure Player Rankings in T20 Cricket (2022–2026)

A data-driven cricket analytics project to evaluate batting and bowling performances in high- and medium-pressure situations using Python and ball-by-ball T20 data.

## Project Overview

This project investigates how batters and bowlers perform under different pressure conditions in T20 cricket.

It develops separate batting and bowling rankings using role-adjusted batting performance and pressure-category bowling wicket rates.

**Analysis period:** 2022–2026

## Objectives

- Identify batters who outperform expected runs in pressure situations.
- Evaluate bowlers based on wickets taken in different pressure categories.
- Compare performances across High and Medium pressure situations.
- Test ranking reliability using sample-size thresholds and shrinkage sensitivity analysis.

## Technologies Used

- Python
- Pandas
- NumPy
- Google Colab
- Matplotlib
- Jupyter Notebook

## Methodology

### 1. Batting Analysis

Batting pressure is classified using the number of wickets lost before a batter's first recorded appearance:

- Low Pressure: 0–2 wickets lost
- Medium Pressure: 3–5 wickets lost
- High Pressure: 6–9 wickets lost

Expected runs are estimated using a leave-one-out average for the same batting position and entry phase.

**Primary metric:** Runs Above Expected

Minimum sample threshold: 10 innings.

### 2. Bowling Analysis

Bowling pressure is classified using the number of wickets lost by the opposition before a recorded delivery:

- Low Pressure: 0–2 wickets lost
- Medium Pressure: 3–5 wickets lost
- High Pressure: 6–9 wickets lost

Bowling performance is evaluated using bowler-credited wickets per 100 recorded deliveries.

A category-specific baseline shrinkage adjustment is applied using 100 prior deliveries.

Minimum sample thresholds:
- 20 innings
- 200 recorded deliveries

Sensitivity tests were conducted using prior strengths of 50, 100 and 200 deliveries.

## Key Findings

### Batting — High Pressure

| Player | Innings | Average Runs Above Expected |
|---|---:|---:|
| Romario Shepherd | 25 | +8.23 |
| MS Dhoni | 17 | +7.59 |
| Jamie Overton | 10 | +5.96 |
| Corbin Bosch | 11 | +5.60 |
| Mark Adair | 18 | +4.32 |

### Batting — Medium Pressure

| Player | Innings | Average Runs Above Expected |
|---|---:|---:|
| Towhid Hridoy | 10 | +10.88 |
| Heinrich Klaasen | 44 | +9.92 |
| Nicholas Pooran | 43 | +7.81 |
| Matthew Wade | 19 | +7.62 |
| Tim David | 81 | +6.04 |

### Bowling — High Pressure

| Player | Innings | Adjusted Wickets per 100 Deliveries |
|---|---:|---:|
| Jason Holder | 41 | 11.12 |
| Kuldeep Yadav | 29 | 10.70 |
| Shaheen Afridi | 26 | 9.84 |
| Mustafizur Rahman | 34 | 9.40 |
| Rashid Khan | 44 | 8.96 |

### Bowling — Medium Pressure

| Player | Innings | Adjusted Wickets per 100 Deliveries |
|---|---:|---:|
| Mark Adair | 28 | 7.15 |
| Wanindu Hasaranga | 70 | 7.13 |
| Abrar Ahmed | 26 | 7.13 |
| Mohit Sharma | 26 | 6.97 |
| Khaleel Ahmed | 37 | 6.91 |

## Sample Sensitivity Analysis

Bowling rankings were tested using 50, 100 and 200 prior deliveries.

High-pressure Top 10 membership remained unchanged across all three settings. Medium-pressure rankings showed some changes in player ordering.

This supports greater ranking stability in the High-pressure bowling results.

## Repository Structure

```text
Pressure-Player-Rankings/
│
├── Pressure_Player_Rankings_in_T20_Cricket_(2022–2026).ipynb
├── batting_high.csv
├── batting_medium.csv
├── bowling_high.csv
├── bowling_medium.csv
├── Pressure_Player_Rankings_Research_Report.pdf
└── README.md
```

## Limitations

- Pressure categories are proxy measures based on wickets lost, not actual match situation or required run rate.
- Batting entry is approximated using the first recorded appearance as striker or non-striker.
- Expected runs are based on batting position and entry phase; this is not a causal estimate of pressure impact.
- Bowling deliveries are recorded deliveries, not necessarily official legal balls.
- Batter runs conceded do not represent complete bowler runs conceded because actual extras cannot be reliably reconstructed.
- Adjusted bowling rates are heuristic shrinkage estimates, not formal Bayesian estimates.
- Rankings are subject to sample-size and dataset coverage limitations.

## Conclusion

This project provides a structured, data-driven comparison of batting and bowling performance under proxy pressure situations in T20 cricket.

It demonstrates the use of data cleaning, feature engineering, statistical baselines, performance metrics and sensitivity analysis to investigate sports performance.

---

**Project:** Pressure Player Rankings in T20 Cricket  
**Tools:** Python, Pandas, NumPy, Google Colab
