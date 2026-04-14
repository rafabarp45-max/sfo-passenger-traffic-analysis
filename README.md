# SFO Passenger Traffic Analysis

Exploratory Data Analysis (EDA) of San Francisco International Airport (SFO) passenger traffic data using Python and Tableau.

Submitted as **CA1 — Data Analytical Tools** | L7 Diploma in Data Analytics | CCT College Dublin (2025)

---

## Overview

This project analyses over a decade of air traffic data from SFO (2006–2015) to uncover operational trends, airline dominance patterns, terminal utilisation, and international connectivity insights. The analysis was structured using the **CRISP-DM** framework and communicated through a Tableau dashboard and an academic poster.

**Dataset:** [Airlines Traffic Passenger Statistics](https://www.kaggle.com/datasets/thedevastator/airlines-traffic-passenger-statistics) — sourced from Kaggle, originally from the [SF Open Data portal](https://data.sfgov.org/Transportation/Air-Traffic-Passenger-Statistics/rkru-6vcg/about_data).

---

## Key Findings

- **40% passenger growth** between 2006 and 2015 (≈3.2M → 4.5M passengers per interval)
- **United Airlines** dominates SFO traffic — creating strategic concentration risk
- **Terminal 3** handles the largest domestic volume, revealing a retail gap opportunity
- **Summer peak seasonality** requires flexible workforce planning
- SFO's west-coast position makes it well-placed as a **transpacific transfer hub**

---

## Project Structure

```
sfo-passenger-traffic-analysis/
├── CA1_analytics_tools.ipynb                        # Python EDA notebook
├── Air_Traffic_Passenger_Statistics.csv             # Raw dataset
├── Air_Traffic_Passenger_Statistics_clean_tableau.csv  # Cleaned dataset (Tableau input)
├── CA1_Air_Traffic_PAX_Statistics.twb               # Tableau workbook
├── CA1_Poster_-_Rafael_Da_Rosa_Barp.pptx            # Academic poster
└── CA1_Report_-_Rafael_Da_Rosa_Barp.docx            # Written report (900 words)
```

---

## Python Workflow

The notebook covers the full EDA pipeline:

1. **Loading & inspection** — shape, dtypes, null counts
2. **Missing value handling** — 54 null IATA codes recategorised as `OTH` (non-scheduled operations)
3. **Deduplication** — confirmed zero duplicate rows
4. **Feature engineering:**
   - `Date` — converted `Activity Period` (YYYYMM) to datetime
   - `Market_Segment` — GEO regions grouped into macro-markets (Domestic, Americas, Asia & Middle East, Europe, Oceania)
   - `Is_International` — binary flag for quick filtering
5. **Standardisation** — airline name string cleaning; United Airlines pre/post-2013 merger unified
6. **Column pruning** — dropped redundant fields (`index`, `Activity Period`, `GEO Summary`)
7. **Export** — clean CSV saved for Tableau ingestion
8. **Visualisations** — bar charts and pie charts using `seaborn` and `matplotlib`

---

## Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3 | Data processing and EDA |
| pandas | Data manipulation |
| numpy | Numerical operations |
| seaborn / matplotlib | Visualisation |
| Tableau | Interactive dashboard and storytelling |

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/sfo-passenger-traffic-analysis.git
cd sfo-passenger-traffic-analysis

# Install dependencies
pip install pandas numpy seaborn matplotlib

# Open the notebook
jupyter notebook CA1_analytics_tools.ipynb
```

The notebook reads `Air_Traffic_Passenger_Statistics.csv` from the same directory and outputs `Air_Traffic_Passenger_Statistics_clean_tableau.csv`.

---

## Author

**Rafael Da Rosa Barp**  
Student No: SBA25079  
L7 Diploma in Data Analytics for Business — CCT College Dublin

---

## References

- Kaggle. (n.d.). *Airlines Traffic Passenger Statistics*. Available at: https://www.kaggle.com/datasets/thedevastator/airlines-traffic-passenger-statistics
- SF Gov. (2016). *Air Traffic Passenger Statistics*. Available at: https://data.sfgov.org/Transportation/Air-Traffic-Passenger-Statistics/rkru-6vcg/about_data
