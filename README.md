# Will the Customer Accept the Coupon?
### Practical Application Assignment 5.1 — UC Berkeley ML & AI Program

---

## Overview

This project investigates: **when a coupon is pushed to a driver, will they accept it?**

Using 12,684 real survey responses (Amazon Mechanical Turk / UCI Machine Learning Repository), we apply exploratory data analysis, probability distributions, and statistical hypothesis testing to distinguish coupon acceptors from rejectors across five coupon types.

📓 [View the Jupyter Notebook](prompt_II.ipynb)

---

## The Data

Each row represents one driving scenario. Features include:

- **Driving context**: destination, time of day, weather, temperature, passenger type
- **Coupon details**: type (5 categories), expiration window (2h or 1d)
- **Demographics**: age, gender, income, marital status, education, occupation
- **Behavioral history**: visit frequency for bars, coffee houses, restaurants

**Target variable**: `Y` — 1 = accepted, 0 = rejected

---

## Overall Results

| Metric | Value |
|--------|-------|
| Total observations (after cleaning) | ~12,079 |
| Overall acceptance rate | **56.8%** |
| Highest acceptance coupon | Carry out & Take away |
| Lowest acceptance coupon | Bar |

---

## Key Findings

### What drives acceptance across all coupons?

| Factor | Effect |
|--------|--------|
| ☀️ Sunny weather | ↑ Higher acceptance |
| 👫 Riding with friends or partner | ↑ Higher acceptance |
| 📅 1-day expiration | ↑ Materially higher vs. 2-hour |
| 🕑 2PM or 6PM time slot | ↑ Peak acceptance windows |
| 🏝️ No urgent destination | ↑ More open to detours |
| 🌧️ Rain or snow | ↓ Lower acceptance |
| 🧒 Kids in the car | ↓ Lowest of any passenger type |
| 🌅 7AM offers | ↓ Lowest of any time slot |

---

### Bar Coupon Deep-Dive

Bar coupons have the lowest acceptance rate, but a highly targetable segment exists.

**Finding 1 — Bar visit frequency is the #1 predictor:**
Drivers who visit bars >1×/month accept bar coupons ~30 percentage points higher than non-bar-goers (p < 0.0001).

**Finding 2 — Frequent bar-goers over 25:**
This combined segment accepts at a significantly elevated rate vs. all others (p < 0.05).

**Finding 3 — Same-direction routing matters:**
Venues on the driver's current route see meaningfully higher acceptance.

**Finding 4 — Family context suppresses acceptance:**
Drivers with children and kids as passengers show the lowest bar coupon acceptance.

---

## Recommendations

1. **Segment bar coupon recipients by visit history** — target frequent bar-goers, suppress for families
2. **Weather-triggered delivery** — push on sunny days, switch to carry-out during rain
3. **Default to 1-day expiration** — 2-hour windows hurt acceptance
4. **Concentrate pushes at 2PM and 6PM** — peak acceptance windows
5. **Integrate routing data** — prioritize venues on the driver's current route

---

## Repository Contents

```
├── prompt_II.ipynb     # Full executed Jupyter notebook
├── coupons.csv         # Dataset (UCI In-Vehicle Coupon Recommendation)
└── README.md           # This file
```

## Libraries Used

`pandas` · `numpy` · `matplotlib` · `seaborn` · `scipy.stats`

---
*Dataset: Wang, Rudin et al. (2017). UCI Machine Learning Repository. https://doi.org/10.24432/C5GS4P*
