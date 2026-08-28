# Sales Analytics

This is a project I did to practice going from raw sales data to something a business could actually use: clean up a messy six-month dataset, figure out what's going on with the business, and build a dashboard someone non-technical could open and use without me having to explain it to them.

**Tools:** Microsoft Excel (PivotTables, PivotCharts, Slicers, formulas)

**Period covered:** January – June 2026

> Quick note: This wasn't a client work, it's a practice project done in the context of Catalyst Support Group. The dataset is generic/synthetic too, not real sales figures or real employees. I treated it like a real engagement anyway.

---

## What I was working with

897 order-level transactions: order ID, date, region, salesperson, product category, product, quantity, unit price, discount, total sales. No context beyond that, which is basically how real requests show up anyway.

## Cleaning it up

The raw data had the usual mess:

- Duplicate order records
- Region names entered inconsistently (`East` and `east` in the same column)
- Missing values I had to track down
- A few missing Total Sales figures I recalculated from quantity, unit price, and discount.


## What I was trying to answer

1. What were total sales over the six months?
2. Which region did best?
3. Which product category brought in the most revenue?
4. Who was the top salesperson?
5. What were the top 10 products?
6. What was the average order value?

## What I found

| Metric | Result |
|---|---|
| Total Sales | ₦1,101,979 |
| Total Orders | 897 |
| Average Order Value | ₦1,229 |
| Top Region | East (₦325,976) |
| Top Product Category | Electronics (₦651,492) |
| Top Salesperson | Grace Udo (₦172,849) |
| Best-Selling Product | Laptop (₦392,194) |

East pulled ahead of every other region, mostly on the back of Electronics. Laptop alone brought in more than a third of that category's revenue, more than double the next product (Cabinet).

## The dashboard

The `Sales Dashboard` tab pulls all of this into one view:

- KPI cards for Total Sales, Total Orders, Average Order Value, Sales Region
- Charts for Sales by Region, Sales by Product Category, Top 10 Products, Sales by Salesperson
- Slicers for Region, Product Category, and Salesperson, so anyone can filter every chart at once without touching a formula

*(Screenshot goes here — I'll add one from the actual Excel file and drop it in `screenshots/dashboard.png`.)*

<!-- ![Sales Dashboard](screenshots/dashboard.png) -->

## What I'd recommend

1. Put more marketing and inventory budget behind East since it's already the strongest region.
2. Look into why North and South are behind, and try targeted promotions there.
3. Stock and promote Electronics harder, it's clearly the category doing the heavy lifting.
4. Figure out what Grace Udo is doing right and see if it's repeatable across the team.
5. Add a monthly trend view, six months in one snapshot hides any seasonality.
6. Stick with dashboards over static reports. People actually use the slicers.

## Repo structure

```
sales-analytics/
├── README.md
├── data/
│   └── retail_sales_dataset.xlsx   # Raw data, PivotTables, and dashboard in one workbook
├── docs/
│   └── project_report.docx         # My original written report
└── screenshots/
    └── dashboard.png               # Dashboard screenshot goes here
```

## Skills I practiced here

Data cleaning, PivotTables and PivotCharts, dashboard design, picking the right KPIs, building slicer-based interactivity, and turning raw transactions into recommendations someone could actually act on.
