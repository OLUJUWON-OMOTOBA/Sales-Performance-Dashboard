# Sales Performance Dashboard

## Overview
A sample end-to-end Business Intelligence project demonstrating sales analytics using Power BI. The report covers revenue trends, product & region performance, and top-performing sales reps. This project is designed to showcase data modeling, time intelligence, and stakeholder-focused visualization.

<img width="1034" height="524" alt="image" src="https://github.com/user-attachments/assets/3b531572-de0d-4759-a2f6-bce8f780dc29" />

## Total Sales by Country

<img width="866" height="523" alt="image" src="https://github.com/user-attachments/assets/1cf32014-e226-41ec-aae2-6fd281412f94" />

## Monthly Total Sales
<img width="896" height="523" alt="image" src="https://github.com/user-attachments/assets/e15d7a82-6622-4512-ace3-23d93b233fc5" />

## Key Influencers in Numerical and Non-Numerical Variables
<img width="1032" height="523" alt="image" src="https://github.com/user-attachments/assets/be96e0ca-2a33-4d20-b100-8696f4c3a26c" />


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


## Power BI build steps


1. Imported `sales_data.csv` into Power BI Desktop.
2. In Power Query, converted `order_date` to Date type and clean columns.
3. Created a Date (Calendar) dimension table and mark it as a Date table.
4. Built a star schema: Sales (fact) → Date (dimension).
5. Created the following visuals:
- Line chart — Total Revenue by Month
- Clustered bar — Revenue by Region and Product
- KPI cards — Total Revenue, Revenue Growth (YoY)
- Table — Top 10 Sales Reps by Revenue
6. Added slicers for Region, Product, and Sales Rep for interactive filtering.


## DAX snippets


```dax
Total Revenue = SUM(sales_data[revenue])
Total Units = SUM(sales_data[units])
Revenue YTD = TOTALYTD([Total Revenue], 'Date'[Date])
Revenue YoY % = DIVIDE([Total Revenue] - CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date])), CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date])))
