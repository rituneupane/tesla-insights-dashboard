**Live dashboard:** https://rituneupane.github.io/tesla-insights-dashboard/

# Tesla 10-year operating dashboard

I pulled Tesla's public delivery reports and 10-K numbers from 2016 to 2025 and put them in one place. I wanted to see whether the Model 3 / Model Y ramp actually shows up in mix and margin.

**Ritu Neupane** · New York

This is my own compilation. Not Tesla. Not a stock pick.

## What I looked at

1. Did scale work after Model 3?
2. What does Tesla actually sell (3/Y vs everything else)?
3. What happened to margin after the price cuts?

## What I found

- Deliveries went from about **76,000** in 2016 to a peak of **1.81 million** in 2023, then **1.64 million** in 2025.
- In 2025, **about 97%** of deliveries were Model 3 and Model Y.
- Automotive gross margin peaked near **29% in 2021** and was around **18% in 2025**.
- Energy revenue grew from about **$2 billion (2020)** to **$12.8 billion (2025)** while auto slowed.

The 2018 and 2019 3/Y split is estimated. Tesla started reporting 3/Y as one bucket in 2020.

## Checks

`python analysis/build.py` runs the checks and rebuilds the dashboard data (`docs/data.js`). All 40 pass (`data/checks.csv`):

- Segment revenue (automotive + energy + services & other) adds to total revenue, every year.
- Model 3/Y + other = total deliveries, every year and every quarter.
- 2023 to 2025 quarters add up to the annual totals.

Corrected against the 10-K and IR releases (see `data/SOURCES.md`): 2016 to 2019 automotive revenue and gross margins, 2017 deliveries and production, 2018 production, and 2024-Q4 other-model deliveries.

## Dashboard

Live: https://rituneupane.github.io/tesla-insights-dashboard/ (source in `docs/`). Deliveries are in thousands of vehicles. Revenue is in $ billions. Margins are in %.

**Overview**

![Overview](screenshots/overview.png)

**Volume**

![Volume](screenshots/volume.png)

**Profitability**

![Profitability](screenshots/profitability.png)

## Files

```
data/tesla_annual.csv      10-year annual series
data/tesla_quarterly.csv   quarterly deliveries, 2023 to 2025
data/SOURCES.md            where the numbers came from
data/checks.csv            tie-out checks (generated)
analysis/build.py          runs checks, writes docs/data.js
docs/                      live dashboard (Chart.js)
analysis/notes.md          my takeaways
screenshots/               overview, volume, profitability
```

Open the CSVs in Excel if you want to check the math, or run `python analysis/build.py`.
