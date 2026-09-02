# Sales Analytics

For this project, I wanted to practice the whole pipeline of turning raw sales data into something actually useful for a business. I took a messy six-month dataset, cleaned it up, dug into what was really happening with the business, and then built a dashboard that a non-technical person could just open and use.

**Tools:** Microsoft Excel (PivotTables, PivotCharts, Slicers, formulas)

**Period covered:** January – June 2026

> Quick disclaimer: This was a practice project completed through Catalyst Support Group, not actual client work. The dataset is also synthetic not real sales figures or employees; but I approached the analysis as if it were a genuine engagement.

---

## What I was working with

The dataset consisted of 1000 order-level transactions, including order ID, date, region, salesperson, product category, product, quantity, unit price, discount, and total sales; with no additional context provided. This mirrors how real-world requests typically arrive.

## Cleaning it up

The raw data had the usual mess:

- Duplicate order records
- Region names entered inconsistently (`East` and `east` in the same column)
- Missing values I had to track down
- Missing Total Sales Values which were essential for the analysis

# Handling duplicates
I checked for duplicates using Order ID, which was expected to be unique. Of the total records, 993 were unique and 7 were duplicates. I dug into those 7 to see whether entire rows were duplicated or whether only some fields matched. It turned out some had discrepancies in the discount column which is an important field; so I dropped those records, since the discount value couldn't be reliably calculated or inferred.

# Standardizing regions
Region names were standardized into a single consistent format: East, North, West, South.

# Handling missing values
I checked each column for missing values and found gaps in three: salesperson (38 missing), quantity (29 missing), and unit price (30 missing). I dropped these records rather than guess-filling them, since I had no reliable way to reconstruct the correct values without more context.

# Calculating Total Sales
I calculated the Total Sales column using quantity, unit price, and discount.


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



**Observation**


While going through the numbers, one thing stood out more than anything else. At first, it looked like East was simply the best-performing region. But the more I dug in, the clearer it became that East's success wasn't spread out. It was really coming from one category, and that one category was being carried by one product.

East didn't just have the highest total sales. It also had the highest average order value, at ₦1,430 per order, compared to ₦1,043 to ₦1,230 in the other regions. That told me East wasn't winning simply by getting more orders. The orders themselves were bigger. When I looked into why, Electronics stood out as the answer. It made up about 60% of total revenue, ₦656,093 out of ₦1,101,979, more than Furniture, Home Appliances, and Office Supplies combined. And within Electronics, one product was doing most of the work. Laptop alone made up nearly 60% of that category's revenue, almost three times more than the next best product, Cabinet.

Putting these pieces together made the pattern even clearer. East's Electronics sales alone, ₦217,323, came close to outselling the entire Furniture category across the whole business. That's not a business performing well across the board. It's a business doing very well in one small part of what it sells, while the rest trails far behind.

This is the part I felt was worth flagging. A large portion of total revenue is riding on one region, one category, and really one product continuing to perform well. If Laptop sales were to slow down, or if East's Electronics numbers were to dip, the effect wouldn't be minor. It would be significant enough to notice across the whole business.


**Business Recommendations**

Right now, a large share of revenue depends on one region (East), one category (Electronics), and mainly one product (Laptop). This is good news, but it's also a risk. If Laptop sales slow down or East underperforms, the business would feel it strongly, not just a little. So while this combination should keep getting support, the company should also start building up the other regions and categories as a backup. North, South, and West aren't just behind on order volume, their average order sizes are smaller too, so growth efforts there should focus on increasing order value, not just order count. Furniture is the strongest candidate for this, since it's already the clear second-place category and outperforms Home Appliances and Office Supplies by a wide margin.

Office Supplies is worth a second look. It brings in a high number of orders but contributes very little to overall revenue, so the company should confirm whether it's genuinely worth the effort it takes to run, or if resources are better placed elsewhere.

On the sales team side, performance shouldn't be measured by one number alone. Grace Udo brings in the most total sales and orders, but Fatima Musa closes fewer deals at a much higher value per sale. Recognition and incentives should account for both types of strong performance.

The company should also look into why sales dropped by almost 40% between February and May before recovering slightly in June. If this dip is tied to something fixable, like a pause in marketing or a supply issue, addressing it could recover meaningful revenue.

Finally, the dashboard built for this analysis should not be treated as a one-time report. It should be used going forward to track whether the company's dependence on East, Electronics, and Laptop is growing or easing over time.

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
