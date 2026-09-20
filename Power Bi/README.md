# Adventure Works Sales Performance Dashboard (2023)

A Power BI dashboard analyzing bike sales performance for Adventure Works, a fictional bike retailer, across product categories, sizes, and individual products.

## Dataset
- 48 orders, Feb 1 – Mar 28, 2023
- Fields: Product ID, Category, Subcategory, Name, Description, Price, Weight, Size, Order ID, Customer ID, Order Date, Order Status, Order Quantity, Order Total, Payment Method
- 7 product categories: Mountain Bikes, Road Bikes, Touring Bikes, E-Bikes, Hybrid Bikes, BMX Bikes, Kids Bikes
- Order statuses: Shipped (24), Processing (18), Cancelled (6)
- Payment methods: Credit Card (29), PayPal (19)

## What's in the Dashboard
- **Donut chart** — Order Total by Product Category
- **Column chart** — Order Total by Product Size
- **Table** — Order Totals by Product Name
- **Slicers** — filter by Product Category, filter by Payment Method

## Key Insights
- **Mountain Bikes and Road Bikes drive two-thirds of revenue** — $50,400 and $48,100 respectively out of $147,800 total, while Kids Bikes and BMX Bikes together make up barely 1.5%.
- **Cancelled orders are disproportionately high-value** — they're only 12.5% of orders (6 of 48) but account for 21% of total order value ($30,900), suggesting cancellations are concentrated in bigger-ticket purchases rather than spread evenly.
- **Medium-sized bikes outsell large by nearly 2:1** in revenue ($96,400 vs. $51,400), worth checking against inventory mix.
- **Credit Card is the dominant payment method** by both order count (29 vs. 19) and revenue ($84,200 vs. $63,600).

## Tools Used
- Power BI Desktop — data modeling, DAX, and visualization
- Excel — source data

## Notes
This project uses a public sample dataset (not proprietary business data) and served as a hands-on exercise in Power BI fundamentals — data modeling, visual design, and slicers/filters.
