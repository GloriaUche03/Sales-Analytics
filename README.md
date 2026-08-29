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

## What I'd recommend

1. Put more marketing and inventory budget behind East since it's already the strongest region.
2. Look into why North and South are behind, and try targeted promotions there.
3. Stock and promote Electronics harder, it's clearly the category doing the heavy lifting.
4. Figure out what Grace Udo is doing right and see if it's repeatable across the team.


**Key insight: one region, one category, one product**

The real story here isn't just that East is the top-performing region. It's that East's success basically comes down to one category, and that category comes down to one product.

East doesn't just lead on total sales. It also has the highest average order value, at ₦1,430 per order, compared to ₦1,043 to ₦1,230 everywhere else. So it's not winning by getting more orders; the orders themselves are bigger. The reason why comes down to Electronics. It makes up about 60% of total revenue (₦656,093 of ₦1,101,979), more than Furniture, Home Appliances, and Office Supplies put together. And inside Electronics, one product carries most of that weight. Laptop makes up nearly 60% of the category's revenue, almost three times what the next best product, Cabinet, brings in.

Put it all together, and East's Electronics sales alone (₦217,323) come close to outselling the entire Furniture category across the whole business. That's not a business winning broadly. It's one that's winning narrowly, in a fairly small part of what it sells.

That's the part worth paying attention to. A big chunk of total revenue is riding on one region, one category, and really one product continuing to perform well. If Laptop sales slow down, or East's Electronics numbers drop, the impact won't be small, it will be big. So the takeaway isn't just "invest more in East." It's "understand how much the business depends on this one combination, and start building up the other regions and categories so there's a backup."



**Business Recommendations**

**1. Treat the East, Electronics, and Laptop combination as a risk, not just a win.**
A large share of total revenue depends on one region, one category, and basically one product doing well. Before putting more investment into this combination, the business should think through what happens if any part of it slows down. A drop in Laptop demand or a slowdown in East would not just hurt sales a little. It would hit hard.

**2. Make a real effort to grow the other three regions.**
North, South, and West are not just behind East in volume. Their average order values are lower too, which means the gap isn't only about how many orders they get, but how big each order is. Promotions or bundling in these regions should aim to raise order value, not just get more orders.

**3. Grow other categories without stepping away from Electronics.**
Electronics should stay the main focus, but Furniture is clearly in second place and the most realistic category to grow further. It's already doing much better than Home Appliances and Office Supplies. Pushing Furniture harder, especially outside East, would make the business less dependent on one category.

**4. Take a closer look at what Office Supplies is really doing for the business.**
It brings in the second-highest number of orders but only a little over 1% of total revenue. That's not automatically a bad thing. It might just be a low-margin category that sells often. But it's worth checking whether it's actually contributing enough, or just taking up effort for very little return.

**5. Recognize salespeople for different strengths, not just one number.**
Grace Udo leads in both total sales and number of orders, but Fatima Musa closes fewer deals at a much higher average value. A reward system based only on "top performer" misses this difference. Incentives should recognize both people who sell a lot and people who sell big, since both add real value.

**6. Look into why sales dropped in spring.**
Sales fell by almost 40% from February's peak down to May's low, before picking back up a bit in June. Rather than assuming this is just seasonal, the business should check if it lines up with something specific, like holidays, supply problems, or a pause in marketing. If the cause can be fixed, this is a simple way to recover real revenue.

**7. Keep using the dashboard, not just as a one-time report but as an ongoing tool.**
The dashboard already lets people filter by region, category, and salesperson. Going forward, it should be used to keep an eye on whether the East, Electronics, and Laptop concentration is getting worse or improving over time, instead of treating this analysis as something done once and forgotten.

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
