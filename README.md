# Banking Account Analytics | Power BI

## Overview

A confidentiality-safe Power BI portfolio project that analyzes banking account data across account status, balances, branches, account officers, products, currencies, and overdraft exposure.

The published repository contains documentation only. The original PBIX file, source data, and screenshots are intentionally excluded because they contain confidential banking information.

## Business Questions

- How many unique accounts are active or dormant?
- What share of accounts is active versus dormant?
- Where is the bank's overdraft exposure?
- How do balances and account volumes vary by account officer, product, and currency?

## Dashboard Features

- Account-status analysis
- Customer search
- Balance and account-count reporting
- Branch and account-officer performance views
- Product and currency analysis
- Overdraft balance reporting

## Measures

The documented measures are available in [DAX/measures.md](DAX/measures.md). They use a single model table named `ACCOUNT_DETAILS_GM`.

## Data Preparation

The portfolio-safe data-preparation notes are in [PowerQuery/data-cleaning.md](PowerQuery/data-cleaning.md). No source records or query exports are included.

## Repository Structure

```text
banking-account-analytics/
├── README.md
├── .gitignore
├── DAX/
│   └── measures.md
├── PowerQuery/
│   └── data-cleaning.md
├── data/
│   └── README.md
└── screenshots/
    └── README.md
```

## Tools Used

- Power BI Desktop
- Power Query
- DAX

## Confidentiality

This is a portfolio documentation project based on a real banking dashboard. No real customer names, account numbers, account balances, account-officer information, PBIX file, source data, or raw dashboard screenshots are published.

To share visuals publicly in the future, recreate them with fully synthetic data and ensure every visible label, filter value, and tooltip is anonymized.
