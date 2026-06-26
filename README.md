# Retail-Sales-Performance-Power-BI
Power BI dashboard analyzing retail sales, profitability, product performance, and regional store efficiency.
# Retail-Sales-Performance-Power-BI

Power BI dashboard analyzing retail sales, profitability, product performance, return trends, and regional store efficiency.

## Project Overview

This project analyzes retail sales performance from 2007 to 2009 using Power BI. The purpose of this dashboard is to understand how the business performed across revenue, orders, profitability, product categories, returns, regions, and stores.

The dashboard also compares revenue with orders, profit, return rate, and store efficiency to understand where the business is performing well and where improvement may be needed.

## Tools and Skills Used

* Power BI
* Power Query
* DAX Measures
* Data Modeling
* Star Schema
* Data Cleaning
* Business Analysis
* Data Visualization

## Business Questions

This project focuses on the following business questions:

1. How did revenue, orders, profit margin, and return rate perform from 2007 to 2009?
2. Was the revenue decline related to lower order volume?
3. Which products and categories contributed the most to revenue?
4. Are high-revenue products also generating strong profit?
5. Which products or categories have higher return rates?
6. Which regions and stores are the strongest revenue contributors?
7. Which stores generate high revenue, high profit, and high order volume?
8. Which stores are more efficient based on revenue per employee?

## Data Model

The report was built using a star schema model with a sales fact table connected to multiple dimension tables.

Main tables used:

* FactSales
* DimDate
* DimProduct
* DimProductCategory
* DimProductSubcategory
* DimStore
* DimSalesTerritory

The date table was used for year-based analysis. Product, store, and territory tables were used to analyze sales, profitability, returns, category contribution, regional performance, and store efficiency.

Relationships were created between the fact table and dimension tables to support filtering and interactive dashboard analysis.

## Dashboard Pages

The report contains three pages:

1. Business Executive Overview
2. Product & Profitability Analysis
3. Regional & Store Performance Analysis

---

## 1. Business Executive Overview

This page gives a high-level summary of business performance from 2007 to 2009.

### Visuals Included

* KPI cards for Revenue, Orders, Profit Margin, Return Rate, and Average Order Value
* Revenue Trend by Year
* Orders Trend by Year
* Revenue by Quarter
* Return Rate by Year
* Year slicer

### Key Insights

Revenue declined from 2007 to 2009. Orders also declined during the same period, which suggests that the drop in revenue was mainly connected to lower order volume.

Profit margin stayed stable, which means the business was still maintaining profitability even though revenue decreased. Return rate also remained low, so product returns do not appear to be the main reason for the revenue decline.

### Business Meaning

The business should look deeper into why orders decreased after 2007. Possible areas to review include customer demand, product availability, pricing, regional sales activity, and customer retention.

---

## 2. Product & Profitability Analysis

This page focuses on product and category-level performance.

### Visuals Included

* Top 10 Products by Revenue
* Revenue vs Profit by Product
* Revenue Share by Category
* Top Products by Return Rate
* Year slicer

### Key Insights

Home Appliances and Computers were major revenue-contributing categories.

The revenue vs profit chart shows that many high-revenue products also generated high profit. This means the top-selling products were not only increasing sales but also supporting profitability.

The highest return-rate products were mainly from Home Appliances. This does not mean the whole category is performing poorly, but it does show that some products in this category may need review.

### Business Meaning

The business should continue supporting products that have both high revenue and high profit. For Home Appliances, return patterns should be reviewed to understand whether returns are related to product quality, customer expectations, delivery issues, or after-sales service.

---

## 3. Regional & Store Performance Analysis

This page compares performance across regions and stores.

### Visuals Included

* Top Revenue Regions
* Top 10 Stores by Revenue
* Revenue, Profit, and Orders by Store
* Top Stores by Revenue per Employee
* Year slicer

### Key Insights

Maryland, Beijing, and Washington were among the strongest revenue-generating regions.

The top store analysis shows which stores contributed the most to revenue. The revenue, profit, and orders chart helps identify stores that are strong across multiple metrics, not only total sales.

Revenue per employee was used to compare store efficiency. This helps identify stores that generate more revenue relative to the number of employees.

### Business Meaning

Executives can use this page to identify strong-performing stores and regions. High-revenue stores are important, but revenue per employee adds another layer by showing operational efficiency. A store with slightly lower revenue but stronger revenue per employee may be operating more efficiently than a larger store with more staff.

---

## Why Revenue per Employee Was Included

Total revenue shows how much a store generated, but it does not show how efficiently the store operated.

Revenue per employee helps answer:

> Which stores are generating more revenue compared to their employee count?

This metric can help the business understand:

* Which stores are more productive
* Which stores generate strong revenue with fewer employees
* Which stores may need staffing or productivity review
* Which stores are efficient beyond just total sales

This is useful for executives because it connects sales performance with operational efficiency.

---

## Analysis Type

This project mainly uses descriptive analysis and also includes diagnostic insights.

### Descriptive Analysis

The dashboard shows what happened in the business:

* Revenue declined
* Orders declined
* Profit margin stayed stable
* Return rate stayed low
* Home Appliances and Computers were strong revenue categories
* Maryland, Beijing, and Washington were top revenue regions

### Diagnostic Insights

The dashboard also gives some clues about why performance changed:

* Revenue declined at the same time as orders, suggesting lower order volume was a key reason for lower revenue.
* Profit margin stayed stable, so the revenue decline was not mainly caused by reduced profitability.
* Return rate stayed low overall, so returns were not the main reason for the decline.
* Home Appliances had many high-return products, so this category may need further review.

With more data, such as customer data, inventory levels, pricing changes, and customer behavior, the analysis could be extended into a deeper root-cause analysis of the revenue decline.

---

## Key DAX Measures

```DAX
Total Revenue =
SUM(FactSales[SalesAmount])
```

```DAX
Total Orders =
DISTINCTCOUNT(FactSales[SalesKey])
```

```DAX
Total Cost =
SUM(FactSales[TotalCost])
```

```DAX
Total Profit =
[Total Revenue] - [Total Cost]
```

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Revenue]
)
```

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders]
)
```

```DAX
Previous Year Revenue =
CALCULATE(
    [Total Revenue],
    SAMEPERIODLASTYEAR(DimDate[Date])
)
```

```DAX
YOY Growth % =
DIVIDE(
    [Total Revenue] - [Previous Year Revenue],
    [Previous Year Revenue]
)
```

```DAX
Revenue per Employee =
DIVIDE(
    [Total Revenue],
    SUM(DimStore[EmployeeCount])
)
```

## Business Recommendations

* Review the decline in order volume after 2007 because revenue decreased along with orders.
* Analyze customer demand, product availability, pricing, regional activity, and customer retention to better understand the sales decline.
* Focus on products that generate both high revenue and high profit.
* Review high-return products in the Home Appliances category to understand possible product or customer satisfaction issues.
* Study strong regions such as Maryland, Beijing, and Washington to understand what is driving better performance.
* Compare stores using both total revenue and revenue per employee to understand sales contribution and operational efficiency.

## Dashboard Screenshots

### Business Executive Overview
Executive_Overview.png

### Product & Profitability Analysis

Product_Profitability_Analysis.png

### Regional & Store Performance Analysis

Regional_Store_Performance.png

## Project Files

The Power BI `.pbix` file was not uploaded because the file size was above GitHub’s browser upload limit.

This repository includes:

* README.md
* Dashboard screenshots

## Conclusion

This Power BI project analyzes retail performance from executive, product, and store-level views. The dashboard shows that revenue and orders declined from 2007 to 2009, while profit margin and return rate stayed stable.

Product analysis identified strong revenue categories and high-return products. Regional and store analysis helped compare top-performing locations and store efficiency using revenue per employee.

This project demonstrates Power BI dashboard design, DAX measure creation, data modeling, business analysis, and insight generation.
