# Walmart 2010–2012 Sales Performance Report

## Executive Summary
This report analyzes historical weekly sales data across **45 Walmart stores** from **February 5, 2010, to November 1, 2012** (143 weeks). During this period, total sales reached **$6.74 billion**. Sales were heavily concentrated in the top-performing stores — the **top 10 locations** accounted for approximately **39.1%** of total revenue. **Semester 2 (July–December)** outperformed **Semester 1 (January–June)** by **2.9%**.

Notable high-performing stores include **Store 20 (~$301M)**, **Store 4 (~$299M)**, and **Store 14 (~$289M)**. High-variance stores based on coefficient of variation (CV) include **Store 35 (~23%)**, **Store 7 (~19.7%)**, and **Store 15 (~19.3%)**.

Holiday weeks significantly outperformed non-holiday weeks — by at least **3,783%** — with **Thanksgiving (2010 and 2011)** delivering the highest uplift of around **6,000%**. **Q3 2012** experienced a slight decline from **Q2 2012**, with a **4.15% decrease** in total sales.

---

## Business Questions
1. Which stores are the top-performing and which are most volatile?
2. Which stores had strong quarter-over-quarter growth in Q3 2012?
3. Which holidays generated significantly higher sales compared to the non-holiday average?
4. What are the overall monthly and semester-level sales trends across all stores?

---

## Data & Methods
The analysis used the sample **Walmart Retail dataset**, downloaded from Kaggle by Rutu Patel. It includes the following fields:
- Store
- Date
- Weekly_Sales
- Holiday_Flag
- Temperature
- Fuel_Price
- CPI
- Unemployment

The `Date` column in the raw `.csv` file was converted into a datetime column (`cleaned_date`). Aggregations and data wrangling were conducted using **PostgreSQL**. An **interactive dashboard** was used to visualize seasonal trends and compare performance metrics.

---

## KPI Overview (2010–2012)
| KPI                | Value   | Notes               | Implication                       |
|--------------------|---------|---------------------|------------------------------------|
| Total Sales        | $6.74B  | All stores, all weeks | Scale of business                |
| # of Stores        | 45      | Unique Store IDs    | Network size                      |
| Top 10 Store Share | 39.1%   | Share of total sales | Concentration risk/opportunity    |
| Semester 2 vs 1    | +2.9%   | Jul–Dec vs Jan–Jun | Seasonality planning              |

### Top 10 Stores by Total Sales
| Store | Total Sales (M) | Share of Total |
|-------|------------------|----------------|
| 20    | $301.4M          | 4.47%          |
| 4     | $299.5M          | 4.45%          |
| 14    | $289.0M          | 4.29%          |
| 13    | $286.5M          | 4.25%          |
| 2     | $275.4M          | 4.09%          |
| 10    | $271.6M          | 4.03%          |
| 27    | $253.9M          | 3.77%          |
| 6     | $223.8M          | 3.32%          |
| 1     | $222.4M          | 3.30%          |
| 39    | $207.4M          | 3.08%          |

**Store 20** leads the network with approximately **$301 million** in total sales, closely followed by Stores 4 and 14. Combined, the **top 10 stores** contributed roughly **39%** of total revenue.

---

## Sales Volatility by Store
High standard deviation indicates larger week-to-week swings; **coefficient of variation (CV)** standardizes volatility by each store’s mean sales.

- **Absolute volatility** (highest swings): Stores 14, 10, and 20
- **Relative volatility (CV):**
  - Store 35 (~23%)
  - Store 7 (~19.7%)
  - Store 15 (~19.3%)

These stores with high CV may benefit from **adjusted inventory controls** and more **responsive staffing strategies**.

---

## Q3 2012 vs Q2 2012 Growth by Store
| Store | Q2 Sales (M) | Q3 Sales (M) | QoQ Growth (%) |
|-------|--------------|--------------|----------------|
| 16    | $6.63M       | $6.44M       | -2.86%         |
| 7     | $7.61M       | $7.32M       | -3.81%         |
| 35    | $10.75M      | $10.25M      | -4.65%         |
| 26    | $13.22M      | $12.42M      | -6.05%         |
| 39    | $20.19M      | $18.90M      | -6.39%         |
| 23    | $18.28M      | $17.10M      | -6.46%         |
| 41    | $17.56M      | $16.37M      | -6.77%         |
| 44    | $4.32M       | $4.02M       | -6.98%         |
| 32    | $15.42M      | $14.14M      | -8.31%         |
| 37    | $6.86M       | $6.25M       | -8.93%         |

While several stores showed declining sales in Q3, **Store 7 (+13.3%)**, **Store 16 (+8.5%)**, and **Store 35 (+4.5%)** experienced **positive quarter-over-quarter growth**. However, the majority posted small single-digit declines.

---

## Holiday Impact vs Non-Holiday Weeks
**Average non-holiday weekly total across all stores:** $1,041,256

| Holiday Week      | Total Sales     | Lift vs Non-Holiday Avg | Notes           |
|-------------------|------------------|---------------------------|------------------|
| Thanksgiving 2011 | $66,593,605      | +$65,552,348              | Above baseline   |
| Thanksgiving 2010 | $65,821,003      | +$64,779,746              | Above baseline   |
| Super Bowl 2012   | $50,009,408      | +$48,968,151              | Above baseline   |
| Super Bowl 2010   | $48,336,678      | +$47,295,421              | Above baseline   |
| Labor Day 2012    | $48,330,059      | +$47,288,802              | Above baseline   |
| Super Bowl 2011   | $47,336,193      | +$46,294,936              | Above baseline   |
| Labor Day 2011    | $46,763,228      | +$45,721,971              | Above baseline   |
| Christmas 2011    | $46,042,461      | +$45,001,204              | Above baseline   |
| Labor Day 2010    | $45,634,398      | +$44,593,141              | Above baseline   |
| Christmas 2010    | $40,432,519      | +$39,391,262              | Above baseline   |

All 10 holiday weeks significantly exceeded the baseline, with **Thanksgiving** and **Super Bowl** weeks showing the largest boosts. **Christmas weeks showed smaller uplifts**, indicating potential **refinements in promotion strategies**.

---

## Monthly and Semester Views
- **Highest-volume months**: April and July (~$0.65B each)
- **Lower-volume months**: November and January
- **Semester Totals:**
  - Semester 1 (Jan–Jun): $3.32B
  - Semester 2 (Jul–Dec): $3.42B

This confirms a **seasonal sales increase** in the second half of the year.

---

## Business Recommendations
1. **Inventory & Labor Planning**: Increase inventory and staffing in April–July; adjust reorder points for high-variance stores (e.g., Stores 35, 7, 15).
2. **Holiday Promotions**: Prioritize Thanksgiving and Super Bowl; reassess strategy for Christmas promotions.
3. **Store-Level Forecasting**: Build store-level weekly forecasts; use holiday flags and CV to monitor volatility.
4. **Executive Dashboard**: Create an ongoing dashboard that tracks top-performing stores, holiday uplift, and high-variance watchlist.

---

## Limitations
- Data ends on **2012-11-01**, missing late November and December 2012.
- Holiday lift uses a **global non-holiday average**; month-specific comparisons could offer different insights.
- No data available on **price, promotion, or in-store merchandising**.

---

## Appendix: Queries & Metrics
- Store-level stats (avg, std dev, CV)
- Quarterly sales and Q3 vs Q2 comparisons
- Holiday week totals vs non-holiday baseline
- Month and semester-level rollups

Final metrics were compiled using **PostgreSQL** and **pandas** for analysis and visualization.
