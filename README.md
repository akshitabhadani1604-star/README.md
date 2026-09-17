# README.md
# BigBasket Category Performance Diagnostic

## Overview

This project analyzes BigBasket category performance using SQL, Google Sheets, Tableau Public, and Python/Pandas.

The analysis covers January to June 2026 and focuses on Delivered orders, category revenue performance, targets, monthly trends, and data-quality diagnostics.

## Key Findings

- Total Delivered Revenue: ₹88,282
- Total Delivered Orders: 434
- Average Order Value: ₹203.40
- Categories Meeting Target: 3 out of 6
- Top Revenue Category: Household Essentials
- Top Supplier: HomeEssentials Traders

### Category Performance

| Category | Revenue | Target | Status |
|---|---:|---:|---|
| Household Essentials | ₹21,715 | ₹17,000 | Above Target |
| Personal Care | ₹16,382 | ₹15,500 | Above Target |
| Bakery | ₹15,410 | ₹12,000 | Above Target |
| Dairy & Eggs | ₹14,090 | ₹16,500 | Below Target - Watch |
| Snacks & Beverages | ₹10,895 | ₹13,000 | Below Target - Watch |
| Fruits & Vegetables | ₹9,790 | ₹12,000 | Below Target - Critical |

## Data Pipeline

The project follows this workflow:

Raw deterministic data
→ SQLite database
→ SQL analysis
→ monthly_category_revenue.csv
→ Google Sheets cross-check
→ Tableau dashboard
→ Python/Pandas data-quality analysis

## Repository Structure

- `generate_data.py` — deterministic data-generation script
- `bigbasket_capstone.db` — SQLite database
- `orders_raw.csv` — raw order data for Python analysis
- `products.csv` — product master data
- `verify.sql` — database verification queries
- `01_foundations.sql` — SQL fundamentals queries
- `02_aggregation_joins.sql` — joins, aggregation and HAVING queries
- `03_reporting.sql` — reporting, tiering and variance analysis
- `monthly_category_revenue.csv` — Part 1 reporting export used for Parts 2 and 3
- `BigBasket_Category_Performance.xlsx` — spreadsheet cross-check
- `analysis.ipynb` — Python/Pandas analysis
- `ai_log.md` — AI-assisted prompting and verification log
- `README.md` — project documentation

## SQL Analysis

SQL files are located in the repository root:

- `01_foundations.sql`
- `02_aggregation_joins.sql`
- `03_reporting.sql`

The database contains 31 products, 50 customers, 500 orders and 6 category targets.

Delivered order count: 434.

## Reproducing the Database

Run:

```bash
python generate_data.py
