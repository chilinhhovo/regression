# The Hidden Shift in Black Home Loans: Mortgage Approvals and Anti-DEI Laws (2021–2023)

## Overview

This project investigates whether anti-DEI (Diversity, Equity, and Inclusion) laws passed in U.S. states between 2021–2023 affected mortgage approval rates for Black borrowers. It combines Home Mortgage Disclosure Act (HMDA) data, U.S. Census demographic data, and presidential election results to explore political and policy-driven shifts in access to credit.

We use regression modeling, comparative trends, and data visualization to analyze:
- Racial disparities in mortgage approval rates over time
- State-level timing and content of anti-DEI laws
- The intersection of race, politics, and geography in financial access

## Files and Notebooks

| Notebook | Purpose |
|----------|---------|
| `process_data.ipynb` | Loads and processes raw HMDA data, cleans column types, and tags racial groups and key approval actions |
| `connect-to-census.ipynb` | Connects to U.S. Census and ACS APIs to merge demographic indicators (income, race, education, etc.) with mortgage data |
| `hdma+demo+elections_merge.ipynb` | Merges processed HMDA and census datasets with presidential election results at the county level |
| `elections-hdma-21-23.ipynb` | Runs exploratory data analysis comparing mortgage trends across politically leaning counties |
| `21-23_anti-dei+elections.ipynb` | Analyzes differences in approval rates before and after anti-DEI legislation, incorporating county-level partisanship and year fixed effects |

## Data Sources

- **HMDA (2021–2023):** Federal dataset tracking mortgage applications and decisions  
- **U.S. Census / ACS (5-year estimates):** Demographic indicators at county level  
- **Election Data:** County-level results from the 2020 and 2024 U.S. presidential elections  
- **State Legislation:** Custom-compiled list of anti-DEI laws, including passage dates  
- **Download the data used in this project:** [Google Drive Folder](https://drive.google.com/drive/folders/1H4_idZ3cvX4cABoN4YuCRKmwIG8wNGza?usp=drive_link)

## Methods

- Fixed-effect logistic regression to control for year and geography
- Difference-in-differences (DiD) framework to test policy impact
- Placebo tests and robustness checks (e.g., using 2021 as a false “treatment year”)
- Visualization using `ggplot2` (R) and `matplotlib/seaborn` (Python)

## Key Findings

- In some anti-DEI states, approval rates for Black applicants increased slightly after legislation — potentially due to heightened scrutiny or reputational risk.
- In other states, approval gaps persisted or widened, especially in Republican counties with low media attention.
- Approval rate trends are uneven and often decoupled from the intent of anti-DEI legislation, suggesting other forces — like public pressure or institutional commitments — may be at play.

## How to Reproduce

1. Clone this repository and set up your environment with the required Python and R packages:
    - Python: `pandas`, `numpy`, `matplotlib`, `seaborn`
    - R: `tidyverse`, `fixest`, `scales`
2. Run notebooks in order:
    - `process_data.ipynb`
    - `connect-to-census.ipynb`
    - `hdma+demo+elections_merge.ipynb`
    - `elections-hdma-21-23.ipynb`
    - `21-23_anti-dei+elections.ipynb`
3. Ensure you have access to the Census API and county-level shapefiles or election data as needed
