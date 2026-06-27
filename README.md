# Superstore Sales Performance Analytics

Business sales performance analysis built for a Data Science & Analytics internship task. The project cleans raw transactional sales data, analyzes revenue trends, top products, category/regional performance, and discount impact, then presents the findings in an interactive Excel dashboard and a written insights report.

## Objective

Analyze business sales data the way a real analyst would for a client, answering:
- Which products generate the most revenue (and which are actually profitable)?
- How do sales change over time?
- Which categories and regions are most profitable?
- Where should the business focus to grow faster?

## Dataset

**Superstore Sales Dataset** (Kaggle) — 9,994 transaction-level rows covering Order/Ship dates, Customer, Region/State/City, Category/Sub-Category, Product, Sales, Quantity, Discount, and Profit, spanning 2014–2017.
Source: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

## Tools Used

Microsoft Excel — PivotTables, PivotCharts, Slicers, and an interactive KPI dashboard. No external libraries or paid tools required.

## Repository Structure

```
├── README.md
├── Superstore_Sales_Dashboard.xlsx        # Full workbook: cleaned data, 5 pivot sheets, dashboard
├── Superstore_Sales_Performance_Report.docx  # Written insights & recommendations report
└── screenshots/
    ├── dashboard.png
    ├── revenue_trend.png
    ├── top_products.png
    ├── category_performance.png
    ├── region_performance.png
    └── discount_impact.png
```

## Data Cleaning Steps

- Removed duplicate rows
- Identified and fixed a mixed-format date column (some entries stored as real Excel dates, others as US-format `MM/DD/YYYY` text) using a custom formula that checks `ISTEXT()` and rebuilds the date with `DATE(YEAR, MONTH, DAY)`
- Standardized numeric data types for Sales, Profit, Discount, and Quantity
- Added helper columns: `Order Year`, `Order Month`, `Profit Margin %`

## Analysis Performed

1. **Revenue trend over time** — monthly Sales aggregated by Order Month, visualized as a line chart
2. **Top 10 products by revenue** — Sales and Profit side by side, sorted and filtered to the top performers
3. **Category & Sub-Category performance** — Sales and Profit nested by Category → Sub-Category
4. **Region & State performance** — Sales, Profit, and Order Count by Region → State
5. **Discount impact on profit** — Profit grouped into discount bands (0–10% through 70–80%)

## Key Findings

- Total Sales: **$2,297,200.86** | Total Profit: **$286,397.02** | Profit Margin: **12%** | Total Orders: **5,009**
- Orders discounted at 0–10% generated **more profit on their own** than the company's entire total profit — every discount band above 30% operated at a net loss.
- **Furniture** is the only category with a thin margin (2.5%), dragged down by **Tables** and **Bookcases**, the only two sub-categories in the dataset that lose money outright.
- **Technology** is the strongest category (17.4% margin), led by **Copiers** (37%+ margin) and **Phones**.
- The **Central region** underperforms **East** on margin (7.9% vs. 13.5%), driven mainly by losses in **Illinois** and **Texas**.

Full analysis, charts, and recommendations are in `Superstore_Sales_Performance_Report.docx`.

## Recommendations

1. Cap discounts at 20% company-wide
2. Re-price or renegotiate Furniture — specifically Tables and Bookcases
3. Audit the Central region, especially Illinois and Texas
4. Invest further in Technology, especially Phones and Copiers
5. Re-evaluate underperforming top-selling SKUs that lose money despite high revenue
6. Plan inventory/marketing around the Aug–Sep and Nov–Dec seasonal peaks

## Author

Naredla Poojitha — Data Science & Analytics Intern
