# Sales Performance Dashboard


![Power BI](https://img.shields.io/badge/Tool-Power%20BI-blue)
![Dataset](https://img.shields.io/badge/Dataset-Synthetic-green)


## Overview


A sample end-to-end Business Intelligence project demonstrating sales analytics using Power BI. The report covers revenue trends, product & region performance, and top-performing sales reps. This project is designed to showcase data modeling, time intelligence, and stakeholder-focused visualization.


## What’s included


- `sales_data.csv` — transactional sales data (1,000 rows)
- `sales_queries.sql` — example SQL queries to aggregate and explore the data
- `sales_dax_measures.txt` — suggested DAX measures for Power BI
- `README.md` — this file


## Key features & highlights


- Time-series revenue analysis (monthly / YTD)
- Product and region performance comparison
- Top N reports for sales reps and products
- Example DAX for YTD and YoY calculations


## Suggested Power BI build steps


1. Import `sales_data.csv` into Power BI Desktop.
2. In Power Query, convert `order_date` to Date type and clean columns.
3. Create a Date (Calendar) dimension table and mark it as a Date table.
4. Build a star schema: Sales (fact) → Date (dimension).
5. Create the following visuals:
- Line chart — Total Revenue by Month
- Clustered bar — Revenue by Region and Product
- KPI cards — Total Revenue, Revenue Growth (YoY)
- Table — Top 10 Sales Reps by Revenue
6. Add slicers for Region, Product, and Sales Rep for interactive filtering.


## Example DAX snippets


```dax
Total Revenue = SUM(sales_data[revenue])
Total Units = SUM(sales_data[units])
Revenue YTD = TOTALYTD([Total Revenue], 'Date'[Date])
Revenue YoY % = DIVIDE([Total Revenue] - CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date])), CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date])))
