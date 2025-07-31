# 📊 Customer Behavior Analysis with SQL & Python

## 📌 Overview
This project demonstrates how to analyze customer activity using PostgreSQL and Python. The goal is to identify the most active customers based on their transaction history.

---

## 🗃️ Data Structure

Key tables used in the analysis:
- `customers_2` — customer details
- `transactions_2` — purchase history
- `products` — product catalog

They are joined using `customer_id` and `product_id`.


---

## 🛠 Tools & Technologies
- PostgreSQL + DBeaver
- SQL (JOIN, GROUP BY, COUNT, ORDER)
- Python (pandas, SQLAlchemy, matplotlib)


---

## 🧠 SQL Logic

```sql
SELECT
    c.customer_id,
    c.first_name || ' ' || c.last_name AS full_name,
    COUNT(t.transaction_id) AS transaction_count
FROM
    customers_2 c
JOIN
    transactions_2 t ON c.customer_id = t.customer_id
GROUP BY
    c.customer_id, full_name
ORDER BY
    transaction_count DESC
LIMIT 10;
