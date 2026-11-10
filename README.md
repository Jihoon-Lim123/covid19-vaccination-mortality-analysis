# COVID-19 Vaccination and Mortality: A Five-Country Data Visualization Study

**DATA 350 — Data Visualization | R / R Markdown | University of Maryland**

**Team:** Vaibhav Kulkarni, Jihoon Lim, Vikas Lokesh, and Dakshita Pal  
**Project date:** April 25, 2026

## Overview

This team project explores associations between COVID-19 vaccination coverage and subsequent mortality patterns in the **United States, United Kingdom, Germany, Brazil, and India**. The study uses country-level time-series visualizations to compare vaccination rollout, death rates, testing intensity, policy stringency, and broad variant-era periods.

The analysis is observational: relationships in the figures should **not** be interpreted as causal estimates of vaccine effectiveness.

## My contributions

**Jihoon Lim:** Data cleaning and preparation; **Visualization 1 (Vaccination vs. Later Death Rates)** and **Visualization 2 (Similar Vaccination Levels, Different Outcomes)**. The rest of the work is credited to teammates below.

## Methods

- Download public COVID-19 time-series records using the R `COVID19` package and aggregate selected country observations.
- Derive daily changes from cumulative counts and compute **7-day moving averages** and **weekly deaths per 100,000**.
- Compare full-vaccination coverage with **death rates 21 days later**; summarize monthly data for multi-variable visualization.
- Explore differences by vaccination period, testing volume, policy stringency, and approximate variant-era date intervals.
- Use a Pearson correlation heatmap, linear regression, and **1,000 bootstrap resamples** for coefficient uncertainty in the team's later visualizations.

## Visualization guide

| Figure | Focus | Contributor |
| --- | --- | --- |
| 1 | Vaccination coverage vs. mortality 21 days later | **Jihoon Lim** |
| 2 | Similar coverage with different mortality outcomes | **Jihoon Lim** |
| 3 | Mortality across vaccination stages | Vikas Lokesh |
| 4 | Policy stringency changes during rollout | Vikas Lokesh |
| 5 | Vaccination and stringency vs. mortality | Dakshita Pal |
| 6 | Correlation among vaccination, tests, deaths, and stringency | Dakshita Pal |
| 7 | Variant-era waves and vaccination rollout | Vaibhav Kulkarni |
| 8 | Bootstrap confidence intervals for adjusted associations | Vaibhav Kulkarni |

## Repository contents

- [`COVID19_Vaccination_Mortality_Analysis.Rmd`](COVID19_Vaccination_Mortality_Analysis.Rmd): Original R Markdown report, analysis code and explanations.
- `README.md`: Overview, methods, authorship, and reproduction notes.

## Reproduce the analysis

Install **R** and **RStudio**, then install the required packages:

```r
install.packages(c("COVID19", "tidyverse", "lubridate", "zoo", "dplyr", "boot", "rmarkdown", "knitr"))
```

Open `COVID19_Vaccination_Mortality_Analysis.Rmd` in RStudio and select **Knit**, or run:

```r
rmarkdown::render("COVID19_Vaccination_Mortality_Analysis.Rmd")
```

The report calls `COVID19::covid19(level = 2, verbose = FALSE)` to retrieve data. An internet connection and a functioning upstream data source may be needed. **This project has not been independently re-executed in a clean environment**; results and data availability can change with time or package versions. No data snapshot is checked into this repository.

## Interpretation and limitations

- Country-level comparisons are descriptive and observational; they do not isolate a causal effect of vaccination.
- Testing practices, reporting changes, country characteristics, policy choices, prior infections, and variant dynamics may confound associations.
- A 21-day lag is a modeling choice, not proof of a biological or causal relationship.
- The variant labels in the analysis approximate broad **calendar periods**, not sequencing-confirmed infections.
- The bootstrap analysis resamples rows; serial correlation in time-series observations may affect interval coverage.
- Country aggregation and population denominators should be reviewed before using the analysis for policy conclusions.

## Team attribution

- **Jihoon Lim** — Data cleaning, visualizations 1–2
- **Vikas Lokesh** — Visualizations 3–4
- **Dakshita Pal** — Visualizations 5–6
- **Vaibhav Kulkarni** — Visualizations 7–8

This is a course team project; any public distribution should respect the course's rules and teammates' rights.