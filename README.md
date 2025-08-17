# data-analyst-internship-task-6
The goal was to analyze sales trends over time using SQL on an online sales dataset where you can see order level information (order date, order amount, and product ID)

# Task 6: Sales Trend Analysis Using Aggregations

## Goal:
Use aggregation methods in SQL to analyze monthly revenue and order volume from an online sales dataset. This task aims to focus on time-based grouping, revenue, and trends in consumer purchasing behaviors.

## Tools Used:
- MySQL (or PostgreSQL / SQLite)
- SQL: query and aggregates

## Dataset Description:
The dataset contains an orders table with the following columns:
- order_id: Primary key to identify each order
- order_date: The timestamp of the order
- amount: Revenue from the order
- product_id: The identifier for the product ordered

## Important SQL Concepts Used:
- EXTRACT(MONTH FROM order_date) and EXTRACT(YEAR FROM order_date) for grouping by year and month
- GROUP BY clause to group the monthly data by month and year 
- SUM(amount) to aggregate monthly revenue
- COUNT(DISTINCT order_id) to get monthly order volume
- ORDER BY clause to order items chronologically or by revenue
- LIMIT clause to retrieve the best months in order of revenue

## Analysis Objectives:
- Understand trends in revenue and order volume through months
- Identify the top 3 months in total sales
- Ascertain any seasonal or cyclical trends in consumer purchasing behaviors

## Script Summary:
``sql
SELECT 
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS monthly_revenue,
  COUNT(DISTINCT order_id) ORDER_VOLUME
FROM orders
GROUP BY year, month
ORDER BY year, month;
