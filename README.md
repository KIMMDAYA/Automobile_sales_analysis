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

 ## SQL Queries Used

```sql
1. /*Total Revenue*/

SELECT SUM(SALES) AS Total_Revenue 
FROM Automobile_Sales;
2. /*Monthly Sales Trend*/

How do sales vary over time (month-to-month)?

SELECT
   YEAR(ORDERDATE) AS YEAR,
   MONTH (ORDERDATE) AS MONTH,
   SUM(SALES) AS Monthly_sales
   FROM [Auto Sales data]
GROUP BY YEAR(ORDERDATE), 
MONTH(ORDERDATE)
ORDER BY Year, Month ;
3. /*Top 10 Best-Selling Products*/

SELECT 
    PRODUCTCODE, 
    SUM(SALES) AS Total_Sales 
FROM [Auto Sales data]
GROUP BY PRODUCTCODE
ORDER BY Total_Sales DESC
OFFSET 100 ROWS FETCH NEXT 10 ROWS ONLY;

4. /*Customer Retention Analysis
How frequently do customers return for purchases?*/

SELECT 
    CUSTOMERNAME, 
    COUNT(ORDERNUMBER) AS Total_Orders, 
    AVG(DAYS_SINCE_LASTORDER) AS Avg_Days_Between_Orders
FROM [Auto Sales data] 
GROUP BY CUSTOMERNAME
ORDER BY Total_Orders DESC;

5. /*Sales Performance by Product Line
Which product line generates the highest revenue?*/
SELECT 
    PRODUCTLINE, 
    SUM(SALES) AS Total_Sales 
FROM [Auto Sales data]
GROUP BY PRODUCTLINE
ORDER BY Total_Sales DESC;

6. /*Impact of Order Status on Sales*/
How does order status affect revenue?
SELECT 
    STATUS, 
    COUNT(ORDERNUMBER) AS Total_Orders, 
    SUM(SALES) AS Total_Sales
FROM [Auto Sales data]
GROUP BY STATUS
ORDER BY Total_Sales DESC;

7./* MSRP vs. Actual Selling Price
How does the Manufacturer’s Suggested Retail Price (MSRP) compare with the actual selling price?*/
SELECT 
    PRODUCTCODE, 
    AVG(MSRP) AS Avg_MSRP, 
    AVG(PRICEEACH) AS Avg_Selling_Price, 
    (AVG(PRICEEACH) / AVG(MSRP)) * 100 AS Selling_Price_Percentage
FROM [Auto Sales data]
GROUP BY PRODUCTCODE
ORDER BY Selling_Price_Percentage DESC;

/*8. Contribution of Deal Sizes to Revenue
What percentage of total revenue comes from small, medium, and large deals?*/
SELECT 
    DEALSIZE, 
    SUM(SALES) AS Total_Sales, 
    (SUM(SALES) / (SELECT SUM(SALES) FROM [Auto Sales data]) * 100) AS Percentage_Contribution
FROM [Auto Sales data]
GROUP BY DEALSIZE
ORDER BY Total_Sales DESC;

/*9. Geographical Sales Performance*/
Which countries generate the highest revenue?

SELECT 
    COUNTRY, 
    SUM(SALES) AS Total_Sales
FROM [Auto Sales data]
GROUP BY COUNTRY
ORDER BY Total_Sales DESC;

/*10. Sales Distribution Across Cities
What are the top cities in terms of sales revenue?*/
 SELECT 
    CITY, 
    SUM(SALES) AS Total_Sales
FROM [Auto Sales data]
GROUP BY CITY
ORDER BY Total_Sales DESC
OFFSET 50 ROWS FETCH NEXT 10 ROWS ONLY;





