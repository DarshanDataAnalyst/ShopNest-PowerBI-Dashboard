# 📊 ShopNest E-Commerce Sales Intelligence Dashboard — Power BI

> **Full-stack Power BI solution analyzing 9,000+ sales transactions across product, customer, regional, and delivery dimensions — built on a star schema data model with 15+ DAX measures.**

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow?style=flat-square&logo=powerbi) ![DAX](https://img.shields.io/badge/DAX-15%2B%20Measures-blue?style=flat-square) ![Dataset](https://img.shields.io/badge/Dataset-9%2C000%2B%20Transactions%20%7C%209%20Tables-orange?style=flat-square)

---

## 📌 Project Overview

ShopNest is a simulated e-commerce retail business. As the data analyst for this capstone project, I designed a complete Power BI solution — from raw multi-table data ingestion through Power Query, to a star schema data model, through to an interactive executive dashboard.

The dashboard answers critical business questions across four domains: **Sales Performance**, **Delivery Operations**, **Customer Behavior**, and **Product Quality** — all in a single self-service BI interface accessible to non-technical stakeholders.

---

## 🎯 Business Questions Answered

1. Which product categories generate the most revenue — and which have the highest delay rates?
2. How does delivery performance (on-time vs delayed) vary by category and month?
3. What payment methods do customers prefer, and how does this affect order volume?
4. Which products receive the best and worst customer ratings?
5. Which states drive the most sales, and where is regional performance lagging?
6. What are the seasonal and yearly revenue growth trends?

---

## 💡 Key Insights Delivered

| Insight | Detail |
|---|---|
| **Top 3 categories drive 62% of total revenue** | Electronics, Sports, and Home are the primary growth engines |
| **Discount-margin inversion in Q3** | Aggressive discounting in July–September compressed margins without proportional volume gains |
| **12% margin recovery opportunity identified** | By adjusting discount strategy in Q3, simulated margin recovery of ~12% is achievable |
| **Delayed orders concentrated in 2 categories** | Sports and Electronics show the highest delivery delay rates — operational bottleneck flagged |
| **Customer re-engagement signal** | At-risk customer cohort identified through RFM — low recency, high historical spend |

---

## 🏗 Data Model — Star Schema

```
                    ┌──────────────────┐
                    │   FACT: Orders   │
                    │ (9,000+ records) │
                    └────────┬─────────┘
          ┌─────────────────┼─────────────────┐
          │                 │                 │
   ┌──────▼──────┐  ┌───────▼──────┐  ┌──────▼──────┐
   │  DIM:       │  │  DIM:        │  │  DIM:       │
   │  Customers  │  │  Products    │  │  Calendar   │
   └─────────────┘  └──────────────┘  └─────────────┘
          │
   ┌──────▼──────┐
   │  DIM:       │
   │  Regions    │
   └─────────────┘
```

**4 dimension tables + 1 fact table**, engineered in Power Query for clean multi-table DAX calculations and optimized query performance.

---

## 📐 DAX Measures (15+ Written)

```dax
-- Month-over-Month Revenue Growth
MoM Revenue Growth % = 
DIVIDE(
    [Total Net Revenue] - CALCULATE([Total Net Revenue], DATEADD('Calendar'[Date], -1, MONTH)),
    CALCULATE([Total Net Revenue], DATEADD('Calendar'[Date], -1, MONTH))
)

-- Year-over-Year Comparison
YoY Revenue Growth % = 
DIVIDE(
    [Total Net Revenue] - CALCULATE([Total Net Revenue], SAMEPERIODLASTYEAR('Calendar'[Date])),
    CALCULATE([Total Net Revenue], SAMEPERIODLASTYEAR('Calendar'[Date]))
)

-- Contribution % by Category
Category Revenue % = 
DIVIDE([Total Net Revenue], CALCULATE([Total Net Revenue], ALL('Products'[Category])))
```

Other measures include: Running Totals, Delayed Order Rate, Average Rating by Product, On-Time Delivery %, Payment Method Share.

---

## ✅ Dashboard Features

- Top 10 Product Categories by Total Sales
- Delayed Orders by Product Category
- Monthly On-Time vs Delayed Delivery Comparison
- Payment Method Breakdown (Credit, Debit, Voucher, Boleto)
- Product Rating Analysis — Top 10 and Bottom 10
- State-wise Sales Performance Map
- Quarterly Seasonal Sales Patterns
- Yearly Revenue Trends with Growth Rate

---

## 📁 Repository Structure

```
ShopNest-PowerBI-Dashboard/
├── ShopNest Store Dashboard.png     # Dashboard screenshot — Page 1
├── ShopNest Store Dashboard2.png    # Dashboard screenshot — Page 2
└── README.md
```

> Note: The `.pbix` file is available on request. GitHub's file size limits prevent direct upload of large Power BI files.

---

## 📸 Dashboard Preview

![ShopNest Dashboard Page 1](ShopNest%20Store%20Dashboard.png)
![ShopNest Dashboard Page 2](ShopNest%20Store%20Dashboard2.png)

---

## 📁 Dataset Summary (9 Source Tables)

| Table | Description |
|---|---|
| `customers_dataset` | Customer ID, demographics, location |
| `orders_dataset` | Order ID, timestamps, status |
| `order_items_dataset` | Product-level line items per order |
| `order_reviews_dataset` | Customer ratings and review text |
| `order_payments_dataset` | Payment method and transaction values |
| `products_dataset` | Product names, categories, dimensions |
| `sellers_dataset` | Seller ID and location |
| `geolocation_dataset` | Zip code to lat/lon mapping |
| `product_categories_dataset` | Category name translations |

---

## 🛠 Tools & Skills Used

- **Power BI Desktop** — Data modeling, DAX, interactive visualizations
- **Power Query (M Language)** — ETL: data ingestion, cleaning, type casting, table merging
- **DAX** — 15+ calculated measures for time intelligence, contribution %, and KPI tracking
- **Star Schema Design** — 4 dimension tables + 1 fact table
- **Chart Types Used** — Bar, column, line, area, pie, map, matrix, KPI cards, slicers

---

## 👤 About Me

**Darshan BK** — Data Analyst with 8+ years of analytical experience in healthcare revenue cycle management and hands-on expertise in SQL, Python, Power BI, and Excel.

📧 darshan.bk92@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/bkdarshan) | [GitHub](https://github.com/DarshanDataAnalyst)
