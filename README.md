# 📊 SQL Sales Analysis Project

## 👩‍💻 Author
Ramisha

---

## 📌 Project Description

This project analyzes an online sales dataset using SQL.
The objective is to calculate:

- Total Revenue
- Monthly Revenue
- Best Selling Product

---

## 🗂 Dataset Structure

Table Name: online_sales

Columns:
- order_id (INT)
- order_date (DATE)
- amount (DECIMAL)
- product_id (INT)

---

## 🔹 1️⃣ Create Table

```sql
CREATE TABLE online_sales (
    order_id INT,
    order_date DATE,
    amount DECIMAL(10,2),
    product_id INT
);
##Insert Sample Data
INSERT INTO online_sales VALUES
(1, '2023-01-10', 500, 101),
(2, '2023-01-15', 300, 102),
(3, '2023-02-05', 700, 103),
(4, '2023-02-20', 200, 101),
(5, '2023-03-01', 900, 104),
(6, '2023-03-18', 400, 102);

##View Data
SELECT * FROM online_sales;

##Monthly Revenue Analysis
SELECT 
    YEAR(order_date) AS year,
    MONTH(order_date) AS month,
    SUM(amount) AS monthly_revenue
FROM online_sales
GROUP BY YEAR(order_date), MONTH(order_date)
ORDER BY year, month;

##Best Selling Product
SELECT 
    product_id,
    SUM(amount) AS total_sales
FROM online_sales
GROUP BY product_id
ORDER BY total_sales DESC
LIMIT 1;

##Insights

March generated the highest revenue.

Product 104 is the best selling product.
