1. Project Title
Sales Performance Analytics Dashboard

2. Project Description
This project analyses sales transactions from 2011 to 2026 across five regions (Central, East, North, South, West), nine products and four customer segments (Consumer, Corporate, Home Office, Small Business).

The dashboard answers questions leadership asks every week:

How much revenue, cost and profit are we generating?
Which products are the most and least profitable?
Which customer segments bring in the most customers?
How does the current year compare with last year?
How does cost behave over time, and when does it spike?

Headline KPIs (all years, all regions)

KPI	Value
Number of customers	-939
Total quantity sold	-5.571K
Total cost	-$968.591K
Total revenue	-$1.393M
Net profit	-$424.623K
Overall profit margin	about -30.5%

3. Tech Stack
ChatGPT: Prompt-based synthetic data generation.
MySQL: Data storage, querying, and SQL scripts.
Power BI Power Query: Data cleaning, transformation, and ETL.
Star Schema: Data modelling and relationship management.
DAX: Measures, calculated columns, and business KPIs.
Power BI Desktop: Interactive dashboards, reports, and data visualization.

4. Data Source
The dataset is synthetic, generated with ChatGPT so that no real customer or company data is exposed. It simulates retail sales transactions.

5. Features
KPI cards: customers, quantity, cost, revenue and net profit at a glance.
Current year revenue card with a year-over-year comparison and a sparkline.
Total Cost by Year line chart to spot cost spikes and drops.
Total Cost vs Total Revenue by Product (100% stacked bar) to compare cost share across products.
Customers by Segment column chart.
Customers by Segment and Month area chart with a scrollbar.
Slicers for Region, Product Name and Year, which filter every visual.
Clean dark theme with green accents for readability.

6. Business Problems and Solutions
   
Problem 1: Cost is volatile and sometimes spikes
Total cost jumped to about $95K in 2014 and fell to about $42K in 2023. 

Solution: Track cost by year and by product with the line chart and the cost-share bar. Investigate spike years by product and region (see sql/analysis_queries.sql, query 3) and negotiate supplier contracts for the high-cost products.

Problem 2: Some products earn much less margin than others
In the cost-vs-revenue chart, products such as Laptop, Smartphone and Monitor have a high cost share (about 40-42% of revenue), while Binder and Paper Pack have a low one (about 25%). 

Solution: Rank products by margin (query 2). Re-price or bundle low-margin hardware, and promote high-margin items such as Binder, Paper Pack and Storage Box as add-ons.

Problem 3: Customer base is concentrated in a few segments
Consumer (about 370) and Corporate (about 305) customers dominate, while Small Business has only about 90. 

Solution: Run targeted campaigns for Small Business and Home Office, such as bulk-purchase discounts and bundles. Use the segment-by-month view to time the campaigns.

Problem 4: Seasonality in customer activity
Customer counts per segment rise and fall across months (peaks around mid-year, dips around March-April). 

Solution: Plan inventory and marketing around peak months (query 5) and run promotions in the low months to smooth demand.

Problem 5: Current year revenue looks 61.67% down
The card shows $40K against $104.36K last year. Solution: First check whether the current year is only a partial year (year-to-date). Comparing a part-year with a full year overstates the drop. The DAX file includes a like-for-like YTD vs prior-year YTD measure for a fair comparison. If the drop persists on a like-for-like basis, drill down by region and product to find the cause.

Problem 6: Regional performance is hidden in the totals

Solution: Use the Region slicer and the regional query (query 4) to find under-performing regions and compare revenue, cost and margin side by side.

7.Screenshot
https://github.com/tmadhefu-eng/Sales-Performance-Analysis-Dashboard/blob/main/Sales_Performance_Analysis_PowerBI_Dashboard.png
