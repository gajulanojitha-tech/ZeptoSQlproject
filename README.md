# ZeptoSQlproject
zepto project using SQL

🛒 Zepto E-Commerce Data Analysis (SQL)
📌 Project Overview
This project performs an end-to-end data exploration, cleaning, and business analysis of Zepto's e-commerce dataset using PostgreSQL. The goal is to analyze product pricing, discounts, inventory levels, category performance, and total estimated revenue to generate actionable business insights.

📁 Repository Structure
Plaintext
├── zepto_sql_project.sql   # Complete SQL script (Schema, Cleaning, Analysis)
├── zepto_v2.csv            # Raw dataset used for analysis
├── zepto_v1.xlsx           # Supplementary data file
└── README.md               # Project documentation


🛠️ Database Schema
SQL
CREATE TABLE zepto (
    sku_id SERIAL PRIMARY KEY,
    category VARCHAR(120),
    name VARCHAR(150) NOT NULL,
    mrp NUMERIC(8,2),
    discountPercent NUMERIC(5,2),
    availableQuantity INTEGER,
    discountedSellingPrice NUMERIC(8,2),
    weightInGms INTEGER,
    outOfStock BOOLEAN,	
    quantity INTEGER
);


🧹 Data Cleaning & Preprocessing
Key data quality issues addressed in the SQL workflow:

Removed Invalid Records: Handled products with invalid prices (mrp = 0).

Currency Standardisation: Converted pricing values from paise to Indian Rupees (₹) by dividing mrp and discountedSellingPrice by 100.

Data Integrity Checks: Evaluated NULL values and identified duplicate SKUs across product categories.

📊 Key Business Questions Solved
1. Best-Value Products
Identified top 10 products offering the highest discount percentage to highlight competitive promotions.

2. Revenue Estimation by Category
Calculated total potential revenue per category using discountedSellingPrice * availableQuantity to evaluate top-performing categories.

3. High-Value Out-of-Stock Items
Flagged products with high MRP (> ₹300) that are currently out of stock to improve inventory replenishment decisions.

4. Unit Cost Analysis (Price Per Gram)
Calculated price per gram for items over 100g to determine unit-cost value for budget-conscious consumers.

5. Product Segmentation by Weight
Categorized inventory into Low, Medium, and Bulk packages using conditional SQL logic (CASE WHEN).


🚀 How to Run the Project
Clone the repository:
Bash
git clone https://github.com/gajulanojitha-tech/ZeptoSQlproject.git
Open your preferred SQL tool (e.g., pgAdmin, DBeaver, or VS Code).

Execute zepto_sql_project.sql sequentially to create tables, clean the data, and run analytical queries.


⚙️ Tech Stack
Database: PostgreSQL

Language: SQL (Data Definition, Manipulation, and Querying)

Dataset Format: CSV / Excel
