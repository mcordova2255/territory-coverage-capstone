# Territory Coverage Capstone — UK & Ireland Enterprise Sales

**Author:** Maria Cordova  
**Tools:** Python · pandas · matplotlib · Excel  
**Dataset:** [Kaggle — territory-coverage-capstone](https://www.kaggle.com/datasets/mariacordova/territory-coverage-capstone)  
**Notebook:** [Kaggle — territory-coverage-capstone-analysis](https://www.kaggle.com/code/mariacordova/territory-coverage-capstone-analysis)

---

## Business Problem

Enterprise sales organisations depend on clean territory coverage to assign accounts correctly, protect active bids, and set fair quotas. When territory data becomes messy — through duplicate ownership, wrong segment assignments, orphaned accounts, or closed entities still marked active — the business risks losing revenue, misaligning resources, and making poor quota decisions.

This project simulates a real-world territory coverage audit for a UK & Ireland enterprise sales team operating across four verticals: **FRIS** (Financial Services), **Education**, **Public Sector**, and **Healthcare**.

---

## What This Project Covers

| Area | What Was Analysed |
|------|-------------------|
| Account Health | Hierarchy status breakdown across 400 accounts |
| TAM at Risk | £3.7M of TAM sitting behind misaligned accounts |
| Active Bid Exposure | 118 accounts with live bids — 80 flagged in alignment issues |
| Before vs After | Rep-level TAM and quota impact post-cleanup |
| Territory Optimisation | ST status analysis across 24 territories |
| Operational Bottlenecks | Case workload and resolution time by team |

---

## Key Findings

- **57.8% of accounts** had a hierarchy issue at baseline — misaligned, wrong parent, duplicate, orphan, or closed entity
- **£3.7M TAM at risk** — 56% of the total portfolio sitting behind alignment problems
- **118 active bid accounts** — 30 rated High severity, meaning live deals were assigned to the wrong rep or territory
- **£354,000 TAM uplift** unlocked after cleanup across the rep team
- **37% of correction cases** were still stalled in Submitted or Delayed status — pointing to a process bottleneck, not just a data problem

---

## Dataset Structure

Five relational tables built to simulate a real business operations dataset:

| Table | Rows | Description |
|-------|------|-------------|
| `accounts.csv` | 400 | Account master with hierarchy status, TAM, active bid flag |
| `territories.csv` | 24 | Territory structure with rep assignment, TAM, quota |
| `reps.csv` | 12 | Rep-level before/after TAM and quota |
| `account_alignment.csv` | 220 | One row per alignment issue with severity and TAM at risk |
| `cases.csv` | 260 | Correction workflow with owning team and resolution dates |

---

## Analysis Structure

```
1. Setup & Data Loading
2. Dataset Overview — portfolio snapshot
3. Account Health — hierarchy status breakdown
4. TAM Distribution by Vertical
5. Alignment Issues — scale and severity
6. Active Bid Risk Analysis
7. Before vs After — Rep TAM and Quota Impact
8. Territory Health and Optimisation
9. Case Workload and Operational Bottlenecks
10. Resolution Progress Over Time
11. Key Findings and Recommendations
```

---

## Tools Used

- **Python** — pandas, numpy, matplotlib
- **Excel** — dataset design and quality control (openpyxl)
- **Kaggle** — notebook hosting and dataset publishing

---

## Files in This Repository

```
territory-coverage-capstone/
├── README.md
├── notebooks/
│   └── territory_coverage_analysis.ipynb
└── outputs/
    └── territory_coverage_dataset.xlsx
```

> The CSV data files are hosted on Kaggle. See the dataset link above.

---

## Skills Demonstrated

- Relational data modelling across 5 connected tables
- Data cleaning and integrity validation (31-point QC check)
- Exploratory data analysis with pandas
- Business-context visualisation with matplotlib
- Translating data findings into commercial recommendations
