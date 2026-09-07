# 🏦 Banking Transaction Analysis using SQL

## 📌 Project Overview

**Banking Transaction Analysis using SQL** is a data analytics project designed to analyze banking customer information, accounts, transactions, branches, and loans using **MySQL**.

The project demonstrates how SQL can be used to transform raw banking data into meaningful insights that can support business and financial decision-making.

---

## 🎯 Project Objectives

The main objectives of this project are to:

- Analyze customer and account information
- Analyze deposits, withdrawals, and transfers
- Identify high-value transactions
- Understand customer transaction behavior
- Analyze payment method usage
- Compare banking branch performance
- Analyze loan information
- Calculate important banking KPIs
- Identify unusual high-value transaction patterns
- Practice advanced SQL techniques

---

## 🗂️ Database Structure

The project contains five main tables:

```text
                    ┌──────────────┐
                    │  Customers   │
                    └──────┬───────┘
                           │
                           │
                    ┌──────▼───────┐
                    │   Accounts   │
                    └──────┬───────┘
                           │
                           │
                 ┌─────────▼──────────┐
                 │   Transactions     │
                 └────────────────────┘

                    ┌──────────────┐
                    │   Branches   │
                    └──────┬───────┘
                           │
                           ▼
                       Accounts

                    ┌──────────────┐
                    │    Loans     │
                    └──────┬───────┘
                           │
                           ▼
                       Customers
```

### Tables

| Table          | Description                         |
| -------------- | ----------------------------------- |
| `customers`    | Stores customer information         |
| `accounts`     | Stores account details and balances |
| `transactions` | Stores banking transactions         |
| `branches`     | Stores bank branch information      |
| `loans`        | Stores customer loan information    |

---

## 🛠️ Technologies Used

- **MySQL**
- **SQL**
- **MySQL Workbench**
- **Git**
- **GitHub**

---

## 📚 SQL Concepts Used

This project covers a wide range of SQL concepts:

### Basic SQL

- `SELECT`
- `WHERE`
- `ORDER BY`
- `LIMIT`
- `DISTINCT`

### Aggregate Functions

- `COUNT()`
- `SUM()`
- `AVG()`
- `MIN()`
- `MAX()`

### Data Grouping

- `GROUP BY`
- `HAVING`

### Relational Operations

- `INNER JOIN`
- `LEFT JOIN`

### Conditional Logic

- `CASE`

### Advanced SQL

- Subqueries
- Common Table Expressions (CTEs)
- Window Functions
- `RANK()`
- `DENSE_RANK()`
- `ROW_NUMBER()`
- Date-based analysis

---

## 📊 Key Analysis Performed

The project answers important business questions such as:

1. How many customers are registered?
2. How many active accounts are there?
3. What is the total transaction value?
4. What is the average transaction amount?
5. What is the highest transaction?
6. How many deposits, withdrawals, and transfers were made?
7. What is the total amount for each transaction type?
8. Which payment method is used most frequently?
9. Which customers have the highest transaction values?
10. Which branches process the highest transaction amounts?
11. What are the monthly transaction trends?
12. Which accounts have the highest balances?
13. Which customers have high-value transactions?
14. What is the total loan amount?
15. Which loan types are most common?
16. Which customers have active loans?
17. Which transactions exceed a specified high-value threshold?

---

## 📈 Key KPIs

The project calculates important banking KPIs including:

- **Total Customers**
- **Total Accounts**
- **Active Accounts**
- **Total Transactions**
- **Total Transaction Value**
- **Average Transaction Value**
- **Total Deposits**
- **Total Withdrawals**
- **Total Transfers**
- **Highest Transaction**
- **Average Account Balance**
- **Total Loan Amount**
- **High-Value Transaction Count**

---

## 🔍 Example SQL Query

### Find the top customers by transaction value

```sql
SELECT
    c.customer_id,
    c.customer_name,
    SUM(t.amount) AS total_transaction_value
FROM customers c
JOIN accounts a
    ON c.customer_id = a.customer_id
JOIN transactions t
    ON a.account_id = t.account_id
GROUP BY
    c.customer_id,
    c.customer_name
ORDER BY total_transaction_value DESC
LIMIT 10;
```

This query combines three tables to identify customers with the highest transaction activity.

---

## 🚨 High-Value Transaction Analysis

The project also identifies potentially unusual high-value transactions.

Example:

```sql
SELECT *
FROM transactions
WHERE amount > 200000
ORDER BY amount DESC;
```

This can be used for **transaction monitoring and further investigation**.

> Note: A high-value transaction alone does not establish fraud. It is simply a useful criterion for further analysis.

---

## 📁 Project Structure

```text
banking-transaction-analysis-sql/
│
├── README.md
│
├── dataset/
│   ├── customers.csv
│   ├── accounts.csv
│   ├── branches.csv
│   ├── transactions.csv
│   └── loans.csv
│
├── sql/
│   ├── 01_create_database.sql
│   ├── 02_create_tables.sql
│   ├── 03_insert_data.sql
│   ├── 04_basic_analysis.sql
│   ├── 05_group_by_analysis.sql
│   ├── 06_join_analysis.sql
│   ├── 07_advanced_analysis.sql
│   └── 08_business_insights.sql
│
└── screenshots/
    └── query_results.png
```

---

## 💡 Business Insights

The analysis can help a bank understand:

- Customer transaction behavior
- Most frequently used payment methods
- High-value customer segments
- Branch transaction performance
- Deposit and withdrawal patterns
- Account activity
- Loan distribution
- Potential transactions requiring additional review

---

## 🎓 Learning Outcomes

Through this project, I developed practical experience in:

- Relational database design
- Primary and foreign keys
- Data querying and filtering
- Aggregation and grouping
- Multi-table joins
- Business-oriented SQL analysis
- Advanced SQL queries
- Transaction pattern analysis
- Converting raw data into actionable insights

---

## 👨‍💻 Author

**RAJEEV A**

B.Tech – Artificial Intelligence & Data Science

### Skills Demonstrated

`SQL` `MySQL` `Data Analysis` `Data Cleaning` `Database Design` `Business Intelligence`

---

## ⭐ Future Improvements

Future versions of this project can include:

- Power BI banking dashboard
- Automated data pipelines
- Larger transaction datasets
- Customer segmentation
- Fraud detection models
- Predictive loan analysis
- Python-based exploratory data analysis

---

## 📌 Disclaimer

This project uses **synthetic/sample banking data** created for educational and portfolio purposes. It does not contain real customer banking information.
