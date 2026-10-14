# Online Store Sales Dashboard

A 10-page Power BI dashboard that analyses 50 orders from an online store (Jan–May 2024). It answers simple business questions: which month sold the most, which city and category earn the most, what customers prefer to pay with, and how much revenue comes from repeat buyers.

![Sales Overview](screenshots/01-sales-overview.png)

## Business questions

- Which month had the highest sales?
- Which cities and categories bring in the most revenue?
- Are the best sellers by revenue the same as the best sellers by units?
- Which payment mode do customers use most?
- How much of the revenue comes from repeat customers?

## Key insights

| Insight | Number |
|---|---|
| Total revenue | ₹54,371 from 50 orders |
| Average order value | ₹1,087 |
| Best month | March, ₹12,681 (every month had 10 orders, so March won on bigger orders) |
| Top categories | Fitness (₹21,728) and Electronics (₹21,561) make up about 80% of revenue |
| Top city | Bangalore, ₹8,484, only ₹46 ahead of Mumbai |
| Top 3 cities | Bangalore, Mumbai and Chennai earn about 45% of revenue |
| Best product by revenue | Running Shoes, ₹12,495 (about 23% of revenue) |
| Best product by units | Notebook Set, 20 units |
| Top payment mode | UPI, 32% of orders and about 40% of revenue |
| Repeat customers | 20 customers generate ₹41,690, about 77% of revenue |

**Main takeaway:** the business depends on two categories and on repeat buyers. High-priced items (Running Shoes, Bluetooth Speaker) drive revenue, while low-priced items (Notebook Set, USB Cable) drive volume.

## Dashboard pages

1. Sales Overview (KPI cards, category chart, city slicer)
2. City-Wise Sales
3. Monthly Sales Trend
4. Payment Mode Distribution
5. Top Selling Products
6. Category Deep Dive
7. Customer Purchase Behaviour
8. Electronics vs Fitness (monthly)
9. City x Category Heatmap
10. Detailed Analysis and Sales Performance

## DAX measures

```DAX
Total Revenue = SUM(Sales[Total_Amount])
Total Orders = DISTINCTCOUNT(Sales[Order_ID])
Average Order Value = DIVIDE([Total Revenue], [Total Orders])
Total Quantity = SUM(Sales[Quantity])
Repeat Customers =
    COUNTROWS(FILTER(VALUES(Sales[Customer_Name]), [Total Orders] >= 2))
Repeat Customer Revenue =
    SUMX(FILTER(VALUES(Sales[Customer_Name]), [Total Orders] >= 2), [Total Revenue])
```

Also built: `Most Purchased Category` and `Top Product by Units` (using TOPN).

## Dataset

`data/online_store_sales.csv`: 50 orders, 10 columns.

`Order_ID, Order_Date, Customer_Name, City, Product, Category, Quantity, Unit_Price, Total_Amount, Payment_Mode`

- 9 cities, 10 products, 4 categories (Electronics, Fitness, Home, Stationery)
- 4 payment modes (UPI, Credit Card, Debit Card, Cash on Delivery)

## Tools and skills used

- Power BI Desktop
- DAX measures
- Data modelling and a Month / Month Number helper column for sorting
- Slicers, donut, bar, line and column charts, matrix heatmap
- Custom dark-and-gold theme (`theme/OnlineStore_Theme.json`)

## Files

| Folder | What's inside |
|---|---|
| `power-bi/` | `.pbix` (full dashboard) and `.pbit` (template without data) |
| `data/` | Source CSV |
| `theme/` | Custom Power BI theme |
| `screenshots/` | Dashboard page images |

## How to open

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
2. Download `power-bi/Mohammed_Shameel_Sales_Dashboard.pbix` and open it.
3. To use the template instead, open the `.pbit` and point it to `data/online_store_sales.csv` when asked.

## Author

Mohammed Shameel, Bengaluru
