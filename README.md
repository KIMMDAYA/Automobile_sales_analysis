# Automobile_sales_analysis

## Problem Statement
An automobile company wants to analyze its sales data to understand customer purchasing behavior, product performance, and overall revenue trends. The company also wants to identify key insights that can help improve sales strategies and customer engagement.

## Overview
This project analyzes automobile sales data using **SQL and Power BI** to uncover insights into revenue trends, customer behavior, and product performance.  

## Objectives:
1.	Identify top-selling products and product lines.
2.	Analyze customer purchase frequency and retention.
3.	Evaluate revenue trends over time.
4.	Assess the impact of order status on sales.
5.	Determine the correlation between MSRP and actual sales price.
6.	Analyze deal sizes and their contribution to total revenue.
7.	Identify geographical trends in sales performance

## Dataset Informtion

| Column Name            | Description |
|------------------------|-------------|
| **ORDERNUMBER**        | Unique identification number for each order |
| **QUANTITYORDERED**    | Number of items ordered per order |
| **PRICEEACH**          | Price of each item in the order |
| **ORDERLINENUMBER**    | Line number of each item within an order |
| **SALES**              | Total sales amount per order (QuantityOrdered * PriceEach) |
| **ORDERDATE**          | Date when the order was placed |
| **DAYS_SINCE_LASTORDER** | Days since the last order for a customer |
| **STATUS**             | Order status (Shipped, Cancelled, On Hold, etc.) |
| **PRODUCTLINE**        | Product category |
| **MSRP**               | Manufacturer's Suggested Retail Price |
| **PRODUCTCODE**        | Unique product code |
| **CUSTOMERNAME**       | Name of the customer who placed the order |
| **PHONE**              | Customer's contact phone number |
| **ADDRESSLINE1**       | Customer's address |
| **CITY**               | Customer's city |
| **POSTALCODE**         | Postal/ZIP code |
| **COUNTRY**            | Customer's country |
| **CONTACTLASTNAME**    | Last name of the contact person |
| **CONTACTFIRSTNAME**   | First name of the contact person |
| **DEALSIZE**           | Size of the deal (Small, Medium, Large) |

## Data Source
[Kaggle](https://www.kaggle.com/datasets/ddosad/auto-sales-data)



## Key Insights & Recommendations
1. **Sales Performance**
Total Revenue: $9.76M
Total Orders: 2,747
Average Order Value: $3.55K
Total Customers: 89
2. **Best-Selling Products**
The Top 10 Products contributed the most revenue.
Ensuring high stock levels for these products is crucial for revenue growth.

 3. **Sales Trends Over Time**
Sales increased in Q4, suggesting seasonal demand.
December had the highest sales, likely due to holiday or end-of-year purchases.
Capitalize on Q4 sales surge with targeted promotions.
2019 was the best sales year, but 2020 saw a decline.
 Focus on top-performing products and ensure adequate stock.

5. **Revenue by Deal Size**
Medium-sized deals generated the most revenue, followed by small deals, then large deals.
Optimizing pricing and incentives for small & medium deal sizes could improve sales.Offer discounts on medium & small deal sizes to boost sales volume.
6. **Order Status & Revenue Impact**
Most sales came from Shipped Orders 
Cancelled and disputed orders resulted in revenue loss 
Improving order fulfillment & customer service can reduce lost revenue.
 7. **Sales by Region**
Most sales occurred in Europe, with some in Africa & South America.
Expanding to underperforming regions could drive more sales.

## Power BI Dashboard Overview
Dashboard Features:
1. Filters for Order Date, Status, Product Line, Country, and Deal Size.
2. KPIs: Total Revenue, Total Orders, Avg Order Value, and Total Customers.
3. Sales Trends: Quarterly and yearly sales trends.
4. Top 10 Products by total sales.
5. Sales by City & Region visualized on a map.
6. Sales by Deal Size using a pie chart.
7. Sales by Order Status highlighting revenue loss due to cancellations.

## Dashboard
![AUTOMOBILE SALES](https://github.com/user-attachments/assets/d7bda3cf-73e1-41ca-bcd8-29881b95f0ab)


