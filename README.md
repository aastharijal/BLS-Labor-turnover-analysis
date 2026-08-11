# U.S. Labor Turnover: Analyzing 15 Years of Change (2009–2024)

Statistical analysis of U.S. labor turnover across 10 major industries using 15 years of monthly data from the Bureau of Labor Statistics' Job Openings and Labor Turnover Survey (JOLTS), with a focus on how COVID-19 disrupted hiring, quits, layoffs, and job openings across sectors.

## Key Findings

- **Quits rose ~35%** post-pandemic (1.58% average 2009–2019 vs. 2.13% average 2020–2024), consistent with the "Great Resignation."
- **Every one of the 10 sectors** showed statistically significant shifts in labor-demand pressure (openings − layoffs) across 2019–2021 (ANOVA, p < 0.01 in all sectors).
- **Retail Trade** consistently posted the highest turnover; **State & Local Government** was the most stable sector throughout the full 15-year window.
- **Healthcare** showed the widest and most persistent labor-demand gap (openings exceeding hires by up to ~5 percentage points in 2021–2022), signaling sustained staffing shortages.
- The structural break in the data occurred **not during the 2020 shutdown itself, but in the 2021 rebound** — Tukey comparisons show 2021 differs significantly from both 2019 and 2020, while 2019 and 2020 do not differ significantly from each other.

## Research Questions

1. How do turnover patterns vary across industries over the last fifteen years?
2. How did COVID-19 alter the relationship between openings, hiring, layoffs, and quits in each sector?
3. Which industries experienced sustained workforce shortages or replacement challenges?

## Methods

- Assembled a 1,920-row panel dataset (10 sectors × 4 metrics × 192 months) manually from individual BLS JOLTS data files
- Constructed derived measures: **net workforce change** (quits + layoffs − hires) and **labor demand gap** (openings − hires)
- One-way ANOVA + Tukey HSD post-hoc tests to evaluate significance of year-over-year shifts across 2019–2021, run independently per sector
- Full descriptive and visual analysis (monthly and yearly trends) across all 10 sectors, 2009–2024

## Tech Stack

R (tidyverse, ggplot2), statistical testing (ANOVA, Tukey HSD)

## Repo Structure

```
├── analysis.Rmd        # Full R Markdown analysis (data prep, visualizations, ANOVA/Tukey tests)
├── data/                # Raw JOLTS data (see data/README.md for sourcing)
└── README.md
```

## Data Source

Bureau of Labor Statistics, Job Openings and Labor Turnover Survey (JOLTS): https://www.bls.gov/jlt/

## Reproducing This Analysis

1. Download monthly JOLTS rates (hires, quits, layoffs, openings) for the 10 sectors listed in `data/README.md` from the BLS
2. Combine into `data/main_data.csv` with columns: `sector`, `Year`, `month`, `hires`, `quits`, `layoffs`, `openings`
3. Open `analysis.Rmd` in RStudio and knit

## Limitations

This analysis uses sector-level aggregates, which mask variation across regions, occupations, and firm sizes. The descriptive/ANOVA approach identifies patterns but does not establish causality — see the full report for discussion.

---
*Author: Aastha Rijal — [LinkedIn](http://www.linkedin.com/in/aastha-rijal)*
