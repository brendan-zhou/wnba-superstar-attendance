# Do Superstars Move the Needle? Causal Estimates of Superstar Effects on WNBA Attendance

**MS Applied Economics capstone project (ECON 692), University of San Francisco — Spring 2025**

## Research question

How does the presence of superstar players impact game attendance across seasons and teams?

Motivated by the unprecedented public interest following the Indiana Fever's 2024 drafting of Caitlin Clark, this project estimates the causal effect of high-profile player arrivals on fan turnout — and tests whether all "superstars" move the needle equally.

## Methods

Three empirical strategies, all in Python (pandas, statsmodels, matplotlib/seaborn):

1. **Event study** — OLS with a post-draft indicator and trend break, estimating the immediate attendance shift around each draft event.
2. **Lead-lag analysis** — year-relative-to-draft dummies (years −2 to +5) tracing how effects evolve over time.
3. **Staggered difference-in-differences** — panel regression with team and year fixed effects and clustered standard errors, exploiting variation in superstar arrival timing across franchises.

Data: game-level WNBA attendance, 1997–2024, from [Across the Timeline](https://www.acrossthetimeline.com/wnba/data.html) (COVID-affected 2020 season excluded; missing 2021 Fever attendance documented in the paper).

## Key findings

| | Caitlin Clark (drafted 2024) | Kelsey Mitchell (drafted 2018) |
|---|---|---|
| Immediate effect (event study) | **+11,540 fans/game** (p < 0.001) | −3,956 fans/game (p < 0.001) |
| Year-0 effect (lead-lag) | **+12,970 fans/game** (p < 0.001) | no comparable surge |
| Dynamic DiD vs. baseline | 2022–23 significantly below 2024 levels | flat-to-declining through 2023 |

The impact of superstars is **heterogeneous**: Clark's arrival triggered an immediate, historic surge, while Mitchell's 2018 draft — despite strong on-court performance — produced no comparable bump. The results suggest media visibility, cultural relevance, and timing matter at least as much as athletic excellence for commercial impact.

## Repository structure

```
├── paper/          # Capstone paper (PDF)
├── presentation/   # Final presentation deck
├── notebooks/
│   ├── wnba-data.ipynb                  # Data cleaning and descriptive statistics
│   ├── event-study.ipynb                # Event study regressions
│   ├── lead-lag-analysis.ipynb          # Lead-lag regressions and visualizations
│   ├── difference-in-differences.ipynb  # Staggered DiD with fixed effects
│   └── scattered-treatment-timing/      # Team-by-team dynamic treatment estimates
│       # (Indiana Fever, Phoenix Mercury, Connecticut Sun, Minnesota Lynx,
│       #  Seattle Storm, Las Vegas Aces, Atlanta Dream, New York Liberty)
└── data/
    ├── wnba-game-attendance.csv         # Game-level attendance (source: Across the Timeline)
    ├── wnba-finals-tv-viewership.csv
    └── wnba-regular-season-tv-viewers.csv
```

## Notes

- The paper is presented as submitted for the capstone; see the PDF for the full literature review, methodology, and limitations.
- Attendance data courtesy of [Across the Timeline](https://www.acrossthetimeline.com/wnba/data.html).
