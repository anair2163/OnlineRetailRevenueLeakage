# Consumer Finance Complaint Trends and Triage

A DuckDB and Python analysis of published consumer finance complaints. It tracks monthly volume, compares complaint workload by company, and measures how much of the database simple billing, refund and unauthorized-transaction tags actually cover.

[Open the notebook](notebooks/revenue_leakage_risk_mitigation_cfpb.ipynb) · [CFPB data and publication notes](https://www.consumerfinance.gov/data-research/consumer-complaints/)

## Findings

- **Volume is concentrated.** The historical snapshot contains about 13.66 million records from December 2011 through February 17, 2026. Three credit reporting firms account for 75.6% of complaints.
- **The keyword rules have limited coverage.** About 91.6% of records fall into the unmatched `Other` category. The tags are a starting point for reviewing a defined financial product, with a sample of manually labeled records needed to assess accuracy.
- **Workload and response are separate measures.** The company scorecard shows complaint counts and response indicators side by side. Comparing complaint incidence across companies would require customer or transaction denominators.

The CFPB database covers consumer financial products and services, with publication rules and reporting differences that affect comparisons. Retail revenue leakage would require internal refund, dispute, chargeback and transaction data. The saved snapshot's last month is partial.

## Reproduce

Download and extract the [CFPB complaint CSV](https://www.consumerfinance.gov/data-research/consumer-complaints/#download-the-data) to `data/raw/complaints.csv`.

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Open `notebooks/revenue_leakage_risk_mitigation_cfpb.ipynb` and run all cells. The notebook caches DuckDB tables under `data/processed/`. Delete `data/processed/cfpb.duckdb` before rerunning with a new download.
