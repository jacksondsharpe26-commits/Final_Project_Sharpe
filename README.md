# QSS20 Final Project — Jackson Sharpe

## Immigration Policy, Economic Insecurity, and Public Attitudes Across Europe

**Research Question:** Do economically insecure Europeans hold more negative attitudes toward immigration in countries with restrictive immigration policies?

---

## Repository Structure

- `code/` — numbered analysis notebooks, run in order
- `data/` — input data files (ESS not included due to size/license; see below)
- `output/` — all generated figures

---

## Scripts

| Script | Inputs | What it does | Outputs |
|--------|--------|--------------|---------|
| `00_pull.ipynb` | `data/ESSQSS20.csv`, `data/migration_policy.xls` | Loads both raw datasets, inspects columns, prints diagnostics | None — inspection only |
| `01_merge.ipynb` | `data/ESSQSS20.csv`, `data/migration_policy.xls` | Cleans ESS, builds attitude index, builds policy panel using ESS fieldwork windows, merges on country-year | `data/merged_attitudes_policy.csv` |
| `02_analyze.ipynb` | `data/ESSQSS20.csv`, `data/merged_attitudes_policy.csv` | Descriptive stats, country-level correlations, fixed effects regressions (all policy, major only, non-major only) | `data/country_correlations.csv`, `data/regression_results.csv`, `data/regression_results_major.csv`, `data/regression_results_nonmajor.csv`, `data/major_policy_trend.csv`, `data/nonmajor_policy_trend.csv` |
| `03_visualize.ipynb` | All CSVs in `data/`, `data/migration_policy.xls` | Generates all 13 figures | `output/fig1_dotplot.png` through `output/fig13_all_interaction.png` |

---

## Data

- **European Social Survey (ESS):** Not included due to file size and license restrictions. Download the cumulative file from [europeansocialsurvey.org](https://www.europeansocialsurvey.org/data/) and place at `data/ESSQSS20.csv`.
- **DEMIG Policy Database:** Included at `data/migration_policy.xls`. Contains 7,600+ immigration policy changes across 31 European countries, hand-coded by restrictiveness and magnitude.

---

## Key Findings

- Economically dissatisfied respondents score 0.72 points lower on the immigration attitude index (0–10), p<0.001
- No significant interaction between overall policy restrictiveness and economic dissatisfaction
- Major policy changes specifically amplify anti-immigration attitudes among economically dissatisfied respondents (coef = -0.094, p<0.001)
- Non-major policy changes show no significant interaction effect
- Policy-attitude correlation varies geographically — negative in Western Europe, positive in Southern and Eastern Europe

---

## Requirements

```
pip install pandas numpy matplotlib geopandas scipy statsmodels
```
