
# QSS20 Final Project — Public Attitudes on Immigration and Migration Policy

Examines the relationship between European public attitudes toward immigration (European Social Survey, 2002–2023) and migration policy actions (DEMIG POLICY database, 1990–2020).

## Structure

- `code/` — analysis notebooks (run in numerical order)
- `data/` — input data files
- `output/` — generated figures

## Scripts

| Script | Inputs | What it does | Outputs |
|---|---|---|---|
| `00_pull.ipynb` | `data/ESSQSS20.csv` | Loads ESS cumulative file, selects relevant columns | ESS dataframe |
| `01_clean.ipynb` | ESS dataframe | Recodes missing values, filters to native-born respondents, builds pro-immigration attitude index | Cleaned dataframe |
| `02_analyze.ipynb` | Cleaned dataframe | Aggregates to country-round means, generates figures of attitudes over time and across countries | `output/*.png` |

## Data

- **European Social Survey (ESS):** Not included due to file size and license restrictions. Download from [europeansocialsurvey.org](https://www.europeansocialsurvey.org/data/) and place at `data/ESSQSS20.csv`.
- **DEMIG POLICY:** Migration policy database, 31 European countries, 1990–2020. Committed as `data/migration_policy.xls`

## Next steps

Merge ESS country-round attitude panel with DEMIG country-year policy panel to analyze how policy environment relates to public attitudes.
