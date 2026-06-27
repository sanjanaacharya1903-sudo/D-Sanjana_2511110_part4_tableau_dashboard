# Part 4 – Executive Tableau Dashboard

## Business Problem Summary

A retail company requires an interactive executive dashboard to monitor business performance and support strategic decision-making. Leadership wants a single dashboard that summarizes sales, profitability, customer segments, regional performance, product categories, shipping efficiency, discount impact, and product return patterns.

The objective of this project is to transform raw transactional sales data into meaningful business insights using Tableau. The dashboard enables executives to identify business opportunities, operational risks, and areas requiring immediate attention.

---

# Dataset Description

The dataset used in this project contains retail order-level transactional data.

### Major Fields Included

### Date Fields

* Order Date
* Ship Date

### Geographic Fields

* Region
* State
* City

### Customer Fields

* Customer ID
* Customer Segment

### Product Fields

* Category
* Sub Category
* Product Name

### Sales Measures

* Sales
* Profit
* Discount
* Quantity

### Shipping Fields

* Ship Mode
* Delivery Days

### Return Information

* Return Flag

### Marketing Information

* Campaign Channel

The dataset provides sufficient information for sales analysis, profitability analysis, customer behavior analysis, shipping performance, and return analysis.

---

# Tableau Workbook Description

The Tableau workbook contains one Executive Dashboard supported by multiple worksheets.

### Worksheets Included

* Sales Trend View
* Regional Performance View
* Category Profitability View
* Customer Segment View
* Shipping Performance View
* Discount vs Profit View
* Return Analysis View

The dashboard combines these worksheets into a single interactive executive reporting interface.

---

# Calculated Fields Created

## 1. Profit Margin

Measures profitability relative to sales.

Formula:

```text
SUM([Profit]) / SUM([Sales])
```

---

## 2. Cost

Calculates estimated product cost.

Formula:

```text
SUM([Sales]) - SUM([Profit])
```

---

## 3. Average Order Value

Calculates average revenue generated per order.

Formula:

```text
SUM([Sales]) / COUNTD([Order ID])
```

---

## 4. Return Rate

Measures the proportion of returned orders.

Formula:

```text
SUM([return_flag]) / COUNTD([order_id])
```

---

## 5. Shipping Delay Bucket

Groups deliveries based on shipping duration.

Formula:

```text
IF [delivery_days] <= 2 THEN "Fast"
ELSEIF [delivery_days] <= 5 THEN "Normal"
ELSE "Delayed"
END
```

---

# Dashboard Components

The Executive Dashboard contains:

* KPI Card – Total Sales
* KPI Card – Total Profit
* KPI Card – Profit Margin
* KPI Card – Average Order Value
* KPI Card – Return Rate

Visualizations:

* Monthly Sales Trend
* Regional Performance
* Category Profitability
* Customer Segment Analysis
* Shipping Performance
* Discount vs Profit Scatter Plot
* Return Analysis

---

# Filters Used

The dashboard includes the following interactive filters:

* Region
* Category
* Customer Segment
* Ship Mode
* Campaign Channel
* Order Date

These filters allow leadership to analyze business performance from different perspectives.

---

# Dashboard Interactions

Dashboard filter actions have been configured so that selecting one visualization filters related charts automatically.

Examples include:

* Selecting a region updates all charts.
* Selecting a product category updates profitability and return analysis.
* Customer segment selection filters sales and shipping performance.

This interaction improves dashboard usability and supports deeper business exploration.

---

# Key Business Insights

* Sales show seasonal trends throughout the year.
* Regional performance differs significantly.
* Some high-selling products generate relatively low profits.
* Customer segments contribute differently to revenue.
* Higher discounts generally reduce profitability.
* Shipping delays may impact customer satisfaction.
* Product returns are concentrated in selected categories.
* Profitable regions provide opportunities for business expansion.
* Continuous KPI monitoring supports better executive decision-making.

---

# Dashboard Story Summary

The dashboard provides a complete executive overview of retail business performance by integrating sales, profitability, customer behavior, shipping efficiency, discounts, and returns.

Instead of viewing isolated reports, leadership can evaluate relationships between multiple business functions using interactive visualizations. The dashboard highlights strengths, identifies operational challenges, and supports strategic planning.

---

# Assumptions

* Delivery Days accurately represent shipping performance.
* Return Flag correctly identifies returned orders.
* Sales and Profit values are accurate.
* Each Order ID represents a unique customer order.
* Historical data represents actual business performance.

---

# Limitations

* Dashboard uses historical transactional data only.
* External market conditions are not included.
* Customer demographics are unavailable.
* Product inventory information is not included.
* Future sales forecasting is outside the scope of this project.

---

# Repository Structure

```
part4_tableau_dashboard/
│
├── data/
│   └── dashboard_sales_data.xlsx
│
├── tableau/
│   └── executive_dashboard.twbx
│
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
│
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
│
└── README.md
```

---

# Screenshots Included

The repository contains the following dashboard screenshots:

* Full Executive Dashboard
* Sales Trend View
* Regional Performance View
* Category Profitability View
* Filter Interaction View

These screenshots demonstrate the dashboard layout, visualization quality, and interactive functionality.

---

# Conclusion

This Tableau Executive Dashboard transforms raw retail sales data into actionable business intelligence. By combining KPIs, interactive filters, and multiple analytical views, the dashboard enables leadership to monitor performance, identify opportunities, manage risks, and make informed data-driven decisions. The project demonstrates effective use of Tableau visualization techniques, calculated fields, dashboard interactions, and business storytelling to support executive-level reporting.
