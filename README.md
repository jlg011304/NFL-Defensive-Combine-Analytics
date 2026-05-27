# NFL Defensive Combine Analytics

Analyzing how NFL Combine measurables and draft position relate to career success for **defensive players**.

**Status:** In progress (analysis and Tableau dashboard complete)

---

## Research question

How well do combine measurables and draft capital predict NFL career success for defensive prospects?

---

## Data

| | |
|---|---|
| **Source** | Kaggle (`combine_data_since_2000_PROCESSED_2018-04-26.csv`) |
| **Scope** | Combine participants, **2000–2018** (all positions in raw data; analysis focuses on defensive positions) |
| **Size** | ~6,200 rows, 16 columns (raw); **~2,780** defensive rows in `defensive_combine_clean.csv` |
| **Analysis cohort** | **~2,298** defensive players with a valid `Pfr_ID` (career AV is reliable for this group) |
| **Outcome** | Pro Football Reference **Approximate Value (AV)** |

**Columns (high level):** player info, position, height/weight, combine drills (40-yard, vertical, bench, broad jump, cone, shuttle), draft team/round/pick, year, PFR id, career AV.

**Known limitations:** Missing combine drills and draft fields are common; `AV` is only meaningful for rows with a valid `Pfr_ID`. Recent combine classes (e.g. 2016–2018) may have incomplete career AV. Details documented in the analysis notebook.

---

## Key findings (so far)

**Phase 2 — Draft round vs career AV** (PFR-linked defensive players, drafted only for the chart):

| Draft round | Mean career AV | Players |
|-------------|----------------|---------|
| 1 | 16.3 | 292 |
| 7 | 3.5 | 189 |

- Mean AV **declines steadily** from earlier to later rounds.
- **Undrafted** players in the analysis cohort (n = 506) average **1.6** career AV — well below Round 1.

**Phase 3 — 40-yard dash vs career AV for cornerbacks** (PFR-linked CBs with a recorded 40-yard time):

| Position group | Combine metric | Players | Correlation with AV |
|----------------|----------------|---------|---------------------|
| CB | 40-yard dash | 517 | -0.24 |

- The relationship is **weakly negative**: faster 40-yard times (lower seconds) are associated with higher career AV, but the scatter is wide.
- Draft round appears to separate career outcomes more clearly than forty time alone.

**Phase 4 — 40-yard dash vs career AV by defensive group** (PFR-linked defenders with a recorded 40-yard time):

| Defensive group | Players | Mean 40-yard time | Mean career AV | Correlation with AV |
|-----------------|---------|-------------------|----------------|---------------------|
| DB | 880 | 4.51 | 5.99 | -0.186 |
| DL/EDGE | 785 | 4.95 | 6.92 | -0.104 |
| LB | 589 | 4.70 | 7.48 | -0.274 |

- The 40-yard dash has a negative relationship with career AV across all three groups.
- The relationship is strongest for linebackers and weakest for defensive line / edge players, suggesting speed matters differently by defensive role.

---

## Dashboard

View the interactive Tableau dashboard: [NFL Defensive Combine Analytics](https://public.tableau.com/views/NFLDefensiveCombineAnalytics/NFLDefensiveCombineDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## Planned deliverables

- [x] Cleaned defensive-player dataset (`:data/defensive_combine_clean.csv`)
- [x] Draft round vs career AV analysis (`:notebooks/data_cleaning.ipynb`, Phase 2)
- [x] Cornerback 40-yard dash vs career AV (Phase 3)
- [x] Defensive group 40-yard dash vs career AV comparison (Phase 4)
- [x] Interactive Tableau dashboard
- [x] Key findings in this README (updated as analysis progresses)

---

## Tools

- Python, pandas, matplotlib
- Jupyter Notebook
- Tableau Public

---

## Repository structure

```
:data/              Raw CSV, cleaned defensive dataset, and Tableau summary CSV
:notebooks/         Analysis notebook (Phases 1–4)
requirements.txt
```

---

## How to run (local)

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Open `:notebooks/data_cleaning.ipynb` and run cells in order:

1. **Phase 1** — Load data, filter defenders, add flags, save `defensive_combine_clean.csv`
2. **Phase 2** — Mean career AV by draft round (bar chart)
3. **Phase 3** — Cornerback 40-yard dash vs career AV (scatter plot and correlation)
4. **Phase 4** — 40-yard dash vs career AV by defensive group (correlation table and bar chart)

---

## Author

Jorge Gonzalez — [LinkedIn](https://www.linkedin.com/in/jorge-gonzalez-0a61aa2a2/) · [GitHub](https://github.com/jlg011304)

---

*This project is for portfolio and educational purposes.*
