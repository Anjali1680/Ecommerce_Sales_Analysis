# E-Commerce Sales & Customer Analysis

**Question:** What drives sales and profit, which discounts and products lose money, and which customers are most valuable?
**Data:** Sample Superstore orders 2015-2018 (public dataset): 9,993 order lines, 5,009 orders, 793 customers
**Tools:** Python (Pandas, Matplotlib, Seaborn), Excel (formula-driven dashboard)

## Files
| File | Description |
|---|---|
| `ecommerce_analysis.ipynb` | Cleaning, joins, EDA, charts, RFM segmentation and findings |
| `ecommerce_dashboard.xlsx` | Excel dashboard: KPI cards, 6 charts, summary tables (265 formulas), RFM sheet, cleaned data |
| `superstore_clean.csv` | Cleaned order data |
| `rfm_customers.csv` | Customer-level Recency / Frequency / Monetary scores and segments |
| `Superstore-raw.csv` | Raw file (contains the Returns and People tables pasted below the orders) |

## Data cleaning
- The raw file has 10,800 rows, but only 9,994 are orders. The rest are two separate tables (People, Returns) pasted below, which were split out.
- Converted text dates (m/d/yyyy) and numbers; removed 1 duplicate order line.
- 11 blank postal codes (all Burlington, VT) were left as is, since they are not used in the analysis.
- Joined orders to the Returns table (by Order ID) and the People table (by Region).

## Key results
- Sales **$2.30M**, profit **$286K** (12.5% margin), 5,009 orders, 793 customers, average order value $459
- Sales grew **29.5% in 2017** and **20.4% in 2018**; September, November and December are the peak months
- **Discounts above 20% lose money:** 1,392 lines (13.9%) lost **$135K**, about 47% of total profit. Margin is 29.5% with no discount, -15.3% at 21-40%, and -77.4% above 40%
- **Tables, Bookcases and Supplies lose money overall.** Tables: +$13.0K at normal discounts but -$30.7K when discounted above 20%
- **West region return rate is 11.7% vs ~3% in other regions** (overall 5.9% of orders returned)
- **RFM:** Champions are 17% of customers but **29.9% of revenue**; "Can't Lose Them" + "At Risk" = 131 customers, **~25% of revenue** at risk of lapsing

## Excel dashboard
Every number on the Summary, Monthly and Dashboard sheets is a formula (SUMIFS / COUNTIF) on the Data and RFM sheets. The RFM scores were computed in Python and pasted as values.

## Recommendations
1. Cap discounts at 20% and review pricing on Tables, Bookcases and Supplies.
2. Run a win-back campaign for "Can't Lose Them" and "At Risk" customers.
3. Offer loyalty perks to Champions.
4. Investigate the West region's return rate.
5. Plan stock and campaigns around September, November and December.
