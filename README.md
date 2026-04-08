# 📊 Electronics Sales Analysis Dashboard (Power BI)

## 📌 Project Overview

This project presents a comprehensive data analysis and visualization solution for an electronics sales dataset using Power BI. It covers the full data workflow including data cleaning, data modeling, DAX calculations, and dashboard design to generate actionable business insights.

The final output is an interactive Power BI report that enables stakeholders to analyze sales performance across products, regions, time, and currencies.

## 🎯 Objectives
- Clean and prepare raw sales data
- Build a star schema data model
- Create DAX measures for key business metrics
- Perform currency conversion to USD
- Design an interactive dashboard and report


## 🛠️ Tools & Technologies
- Power BI Desktop
- Power Query (Data Cleaning & Transformation)
- DAX (Data Analysis Expressions)
- Data Modeling (Star Schema)

## 🧩 Data Modeling
### ⭐ Star Schema Design
**Fact Table:** Order  
**Dimension Tables:**  
- Date  
- Product  
- Customer  
- Region  

### 🔗 Relationships  
Order[OrderDate] → Date[Date] *(Active)*  
Order[DeliveryDate] → Date[Date] *(Inactive)*  
Other dimensions linked using Many-to-One relationships.

## 📐 Key DAX Measures
### 📊 Total Sales  
total_sales = SUM('Order'[SalesAmount])

### 📈 Profit Margin %
profit_margin_percent = DIVIDE(SUM('Order'[Profit]), SUM('Order'[SalesAmount]))

### 💱 Sales in USD  
sales_in_usd = SUMX( 'Order', 'Order'[SalesAmount] * SWITCH( 'Order'[Currency], "USD", 1,  "CAD", 0.72, 1 ) )

## 📊 Dashboard Features
### 📌 Main Dashboard (Overview)  
kpi_cards:
- Total Sales
- Total Profit
- Profit Margin %
- Sales in USD   
sales_trend_line_chart: Sales trend (Line Chart)   
top_products_bar_chart: Top products (Bar Chart)   
sales_distribution_pie_chart: Sales distribution (Pie Chart)   
dashboard_slicers: Interactive slicers (Year, Region, Product, Customer)

### 📦 Product Analysis  
sales_by_product: Sales by product   
p_profitability_by_product: Profitability by product   
top_performing_products: Top-performing products   

### 🌍 Region Analysis  
sales_by_region_bar_chart: Sales by region (Bar Chart)   
geographic_visualization_map: Geographic visualization (Map)   p_profit_margin_comparison: Profit margin comparison   

### 📈 Trend Analysis  
Daily_sales_trends: Daily sales trends   



## 💡 Key Insights
a certain products contribute significantly to total revenue.
some regions have high sales but lower profitability.
sales trends show consistent growth patterns.
