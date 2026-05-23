# NFL Defensive Combine Analytics

Analyzing how NFL Combine measurables and draft position relate to career success for **defensive players**.

**Status:** In progress

---

## Research question

How well do combine measurables and draft capital predict NFL career success for defensive prospects?

---

## Data

| | |
|---|---|
| **Source** | Kaggle (`combine_data_since_2000_PROCESSED_2018-04-26.csv`) |
| **Scope** | Combine participants, **2000-2018** (all positions in raw data; analysis focuses on defensive positions) |
| **Size** | ~6,200 rows, 16 columns |
| **Outcome** | Pro Football Reference **Approximate Value (AV)** where players are linked via `Pfr_ID` |

**Columns (high level):** player info, position, height/weight, combine drills (40-yard, vertical, bench, broad jump, cone, shuttle), draft team/round/pick, year, PFR id, career AV.

**Known limitations:** Missing combine drills and draft fields are common; `AV` is only meaningful for rows with a valid `Pfr_ID`. Details documented in the analysis notebooks.

---

## Planned deliverables

- [ ] Cleaned defensive-player dataset  
- [ ] Exploratory and statistical analysis (Python)  
- [ ] Interactive dashboard (TBD: Power BI / Tableau / Streamlit)  
- [ ] Key findings and recommendations in this README  

---

## Tools

- Python, pandas  
- Jupyter Notebook  
- (Dashboard tool TBD)

---

## Repository structure

:data/ Raw/processed CSV :notebooks/ Analysis notebooks requirements.txt

---

## How to run (local)

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook

Open :notebooks/data_cleaning.ipynb to reproduce data loading and early exploration.

Author
Jorge Gonzalez — LinkedIn · GitHub

This project is for portfolio and educational purposes.

Replace `YOUR-PROFILE` and `YOUR-USERNAME` in the Author section, or delete that line if you prefer.
