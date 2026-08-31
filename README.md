# Territory Coverage Capstone / UK & Ireland Enterprise Sales

**Author:** Maria Cordova
**Tools:** Python · pandas · matplotlib · Excel
**Dataset:** [Kaggle · territory-coverage-capstone](https://www.kaggle.com/datasets/mariacordova/territory-coverage-capstone)
**Notebook:** [Kaggle · territory-coverage-capstone-analysis](https://www.kaggle.com/code/mariacordova/territory-coverage-capstone-analysis)
**Dashboard:** [Tableau Public · UK & Ireland Coverage Audit](https://public.tableau.com/app/profile/maria.cordova6235/viz/UKIrelandCoverageAudit/Dashboard1)

---

## Business Problem

Enterprise sales organisations depend on clean territory coverage to assign accounts correctly, protect active bids, and set fair quotas. When territory data becomes messy, through duplicate ownership, wrong segment assignments, orphaned accounts, or closed entities still marked active, the business risks losing revenue, misaligning resources, and making poor quota decisions.

This project simulates a territory coverage audit for a UK and Ireland enterprise sales team operating across three verticals: **Financial & Retail**, **Education**, and **Public Sector**.

All data in this repository is generated. It models the structure and failure modes of an enterprise coverage dataset. No client or employer data is used anywhere in this project, and no internal terminology appears in any table: every label in the published files is the readable label used in the analysis.

---

## What This Project Covers

| Area                    | What Was Analysed                                             |
| ----------------------- | ------------------------------------------------------------- |
| Account Health          | Hierarchy status breakdown across 400 accounts                |
| TAM at Risk             | $2.97M of TAM sitting behind misaligned accounts              |
| Active Bid Exposure     | 119 accounts with live bids, 48 flagged in alignment issues   |
| Before vs After         | Rep-level TAM and quota impact post-correction                |
| Territory Optimisation  | Territory status analysis across 24 territories               |
| Operational Bottlenecks | Case workload and resolution time by team                     |

---

## Key Findings

- **42.5% of accounts** carried a hierarchy defect at baseline: misaligned, wrong parent, duplicate, orphan, or a closed entity still marked active
- **$2.97M TAM at risk**, 28% of the $10.6M modelled portfolio sitting behind alignment problems
- **119 active bid accounts**, 48 of them carrying alignment issues and 21 rated high severity, meaning $755,700 of live deal value assigned to the wrong rep or territory
- **Correction moved books in both directions.** Seven rep books fell and five rose, for a net reduction of $210,700 in TAM and $50,500 in quota. Validation that only ever adds value is not validation; the source overstated more often than it missed, and the correction says so
- **37% of correction cases** were still stalled in submitted or delayed status, pointing to a process bottleneck rather than only a data problem
- **Territory structure is uneven.** 5 of 24 territories are flagged for consolidation and 3 are over-fragmented, carrying an average of 9 accounts against a book average of 17

---

## Dataset Structure

Five relational tables built to model an enterprise sales operations dataset. Every table ties back to `accounts`: territory TAM and rep book TAM both sum to the account total, and no alignment row or case row references an account that does not exist.

| Table                   | Rows | Description                                                 |
| ----------------------- | ---- | ----------------------------------------------------------- |
| `accounts.csv`          | 400  | Account master with hierarchy status, TAM, active bid flag  |
| `territories.csv`       | 24   | Territory structure with rep assignment, TAM, quota, status |
| `reps.csv`              | 12   | Rep-level before/after TAM and quota, with direction        |
| `account_alignment.csv` | 170  | One row per alignment issue with severity and TAM at risk   |
| `cases.csv`             | 260  | Correction workflow with owning team and resolution dates   |

Relationships are enforced rather than assumed. Each account sits in exactly one territory, each territory belongs to one vertical, each rep owns territories in a single vertical, and accounts registered in Ireland sit in Ireland territories.

---

## Analysis Structure

```
1. Setup & Data Loading
2. Dataset Overview · portfolio snapshot
3. Account Health · hierarchy status breakdown
4. TAM Distribution by Vertical
5. Alignment Issues · scale and severity
6. Active Bid Risk Analysis
7. Before vs After · Rep TAM and Quota Impact
8. Territory Health and Optimisation
9. Case Workload and Operational Bottlenecks
10. Resolution Progress Over Time
11. Key Findings and Recommendations
```

---

## Tools Used

- **Python** · pandas, numpy, matplotlib
- **Excel** · dataset design and quality control (openpyxl)
- **Kaggle** · notebook hosting and dataset publishing
- **Tableau Public** · the same audit published as an interactive dashboard

---

## Files in This Repository

```
territory-coverage-capstone/
├── README.md
├── territory_coverage_capstone_notebook.ipynb
└── territory_coverage_dataset.xlsx
```

> The CSV data files are hosted on Kaggle. See the dataset link above.

---

## Skills Demonstrated

- Relational data modelling across 5 connected tables
- Data cleaning and integrity validation
- Exploratory data analysis with pandas
- Business-context visualisation with matplotlib and Tableau
- Translating data findings into commercial recommendations
