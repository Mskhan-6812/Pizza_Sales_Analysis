🍕 PIZZA SALES ANALYSIS USING POWER BI AND SQL
🎯 Data Analytics Project by Md Sahanwaj Khan

This project uses SQL Server for data analysis and Power BI for interactive dashboard visualization.
It provides business insights from pizza sales data — covering revenue, trends, and top-performing pizzas.

🧩 PROJECT OBJECTIVES

Analyze total revenue, total orders, and average order value

Identify top and bottom performing pizzas by revenue and quantity

Study daily and monthly order trends

Evaluate sales distribution across pizza categories and sizes

🧰 TOOLS & TECHNOLOGIES USED
Tool	Purpose
Microsoft SQL Server	KPI calculation and data analysis
Microsoft Power BI	Dashboard creation and visualization
Microsoft Excel	Data source and cleaning
Power Query & DAX	Data transformation and modeling
🧮 SQL QUERIES USED
-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- Average Order Value
SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_Order_Value FROM pizza_sales;

-- Total Pizzas Sold
SELECT SUM(quantity) AS Total_Pizzas_Sold FROM pizza_sales;

-- Total Orders
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales;

-- Average Pizzas per Order
SELECT CAST(SUM(quantity) AS DECIMAL(10,2)) / 
       CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS Avg_Pizzas_Per_Order
FROM pizza_sales;

📈 TREND ANALYSIS

Daily Trend for Orders:

SELECT DATENAME(DW, order_date) AS Order_Day,
       COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATENAME(DW, order_date);


Monthly Trend for Orders:

SELECT DATENAME(MONTH, order_date) AS Month_Name,
       COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATENAME(MONTH, order_date);

💹 KEY METRICS (KPIs)
KPI	Description	Value (Example)
Total Revenue	Total sales value	₹817.86K
Average Order Value	Avg. sales per order	₹38.31
Total Pizzas Sold	Number of pizzas sold	49,574
Total Orders	Unique orders	21,350
Avg Pizzas per Order	Pizzas per order	2.32
📊 DASHBOARD PREVIEWS
🔹 Dashboard 1 – Overall Sales Overview

This dashboard shows overall KPIs, daily & monthly trends, and sales by category and size.

🔹 Dashboard 2 – Best/Worst Sellers

This dashboard displays the top and bottom-performing pizzas by revenue, quantity, and total orders.

💡 KEY INSIGHTS

Friday and Saturday have the highest number of sales 🍕

Classic pizzas contribute maximum to total revenue

Medium-sized pizzas are most preferred by customers

July and January show peak order months

Thai Chicken Pizza generates the highest revenue and orders

📘 FILES INCLUDED
Pizza_Sales_Analysis/
├── Pizza_Sales_Analysis.pbix          → Power BI Dashboard
├── Pizza_Sales_Data.xlsx              → Dataset
├── Pizza_Sales_SQL_Queries.sql        → SQL File
├── Pizza_Sales_Analysis_Report.docx   → Word Report
├── Pizza_Sales_Analysis_Dashboard.pptx → PowerPoint Presentation
├── Dashboard_1_Overall_Sales.png      → Dashboard 1 Image
├── Dashboard_2_Best_Worst_Sellers.png → Dashboard 2 Image
└── README.md                          → This file

📊 CONCLUSION

The Pizza Sales Dashboard provides a complete analysis of sales performance.
It helps understand:

Which pizzas and sizes drive revenue

When demand peaks during the week/month

How customer preferences affect business outcomes

Combining SQL and Power BI delivers actionable insights for better decision-making.

🚀 FUTURE ENHANCEMENTS

Add live SQL connection for automatic refresh

Include customer segmentation & regional analysis

Integrate predictive analytics for forecasting future sales

👨‍💻 AUTHOR

Md Sahanwaj Khan
GitHub: Mskhan-6812

“Turning raw data into meaningful business insights using SQL & Power BI.”

⭐ SUPPORT

If you found this project useful, please consider giving it a 🌟 star on GitHub.
It motivates me to continue learning and building data projects!

🧾 HOW TO USE

Clone or download this repository.

Open Pizza_Sales_Analysis.pbix in Power BI Desktop.

Explore the interactive visuals and slicers.

Open Pizza_Sales_SQL_Queries.sql to see how data was analyzed.

Check README.md for full documentation and dashboard preview.
