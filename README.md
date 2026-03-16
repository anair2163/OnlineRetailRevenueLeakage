# Online Retail Revenue Leakage & Risk Mitigation Analysis (CFPB)

This project analyzes real U.S. consumer complaint data from the CFPB Consumer Complaint Database to identify risk signals and process breakdowns that map to online retail “revenue leakage” themes:
- unauthorized transactions / fraud
- billing disputes
- refunds / returns issues
- operational performance (timely response)

Deliverable:
- A reproducible Python notebook with KPIs, trends, company scorecard, an interpretable risk score, and an executive summary.

## Data setup
Put the downloaded CSV at:
- data/raw/complaints.csv

Raw data is not committed to GitHub.

## How to run
pip install -r requirements.txt
jupyter lab

Open:
- notebooks/revenue_leakage_risk_mitigation_cfpb.ipynb
