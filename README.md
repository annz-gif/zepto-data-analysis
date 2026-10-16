# Zepto Inventory & Retail Data Analysis using SQL

## 📌 Project Overview

This project analyzes Zepto product and inventory data using SQL to uncover insights into product pricing, discount strategies, stock availability, category-wise revenue, and inventory distribution.

The project uses **PostgreSQL** to perform data exploration, data cleaning, and business-focused analysis. It demonstrates how SQL can transform raw retail data into actionable insights that support pricing, inventory management, and business decision-making.

## 🎯 Project Objectives

- Explore and understand the retail product dataset.
- Identify missing values, duplicate product names, and invalid prices.
- Analyze product discounts and identify the best-value products.
- Examine out-of-stock products with high maximum retail prices (MRP).
- Estimate revenue and inventory weight across product categories.
- Compare product value using price-per-gram calculations.
- Categorize products based on their weight.

## 🛠️ Tools & Technologies

- **Database:** PostgreSQL
- **Query Language:** SQL
- **Key Concepts:** Data exploration, data cleaning, aggregation, filtering, sorting, conditional logic, and business analysis.

## 📂 Dataset Description

The dataset contains product-level information related to pricing, discounts, availability, and quantity.

| Column | Description |
|---|---|
| `sku_id` | Unique stock-keeping unit identifier |
| `category` | Product category |
| `name` | Product name |
| `mrp` | Maximum retail price |
| `discountPercent` | Discount percentage |
| `availableQuantity` | Available inventory quantity |
| `discountedSellingPrice` | Price after discount |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Indicates whether a product is out of stock |
| `quantity` | Product quantity field |

*Note: The dataset's source and exact unit conventions should be documented if known.*

## 🔍 Project Workflow

### 1. Data Exploration

Initial queries were used to understand the structure and quality of the dataset.

- Counted the total number of records.
- Retrieved sample product records.
- Checked for missing values across key columns.
- Identified distinct product categories.
- Compared in-stock and out-of-stock product counts.
- Identified product names associated with multiple SKUs.

### 2. Data Cleaning

The following cleaning operations were performed:

- Identified products with zero MRP or selling price.
- Removed records where MRP was zero.
- Converted MRP and discounted selling prices from paise to rupees.

**Important:** The currency conversion assumes both price columns were originally stored in paise. Confirm the source data's units before applying this transformation. Also, zero-priced products should be investigated before deletion.

### 3. Business Analysis

Eight business questions were explored using SQL.

#### Q1. What are the top 10 best-value products based on discount percentage?
Ranked products by discount percentage to identify the highest-discount offerings.

**Business value:** Helps customers and merchandising teams identify attractive promotions.

#### Q2. Which high-MRP products are out of stock?
Filtered products that are out of stock and have an MRP greater than ₹300.

**Business value:** Helps identify potentially valuable products that may need replenishment.

#### Q3. What is the estimated revenue for each category?
Calculated a category-level estimate using discounted selling price multiplied by available quantity.

**Business value:** Provides a starting point for comparing category-level inventory value.

*Limitation: This calculation estimates the value of available inventory, not actual realized revenue. Actual revenue requires sales or transaction data.*

#### Q4. Which products have an MRP greater than ₹500 and a discount below 10%?
Identified higher-priced products with relatively small discounts.

**Business value:** Helps evaluate pricing strategies and discount opportunities.

#### Q5. Which five categories have the highest average discount?
Calculated the average discount percentage for each category and ranked the categories.

**Business value:** Helps compare promotional intensity across product categories.

#### Q6. Which products offer the best price per gram?
Calculated price per gram for products weighing at least 100 grams and sorted them from lowest to highest cost per gram.

**Business value:** Supports unit-price comparisons and value-for-money analysis.

#### Q7. How can products be classified by weight?
Used a `CASE` expression to classify products into three groups:

- **Low:** Below 1,000 grams
- **Medium:** 1,000 to below 5,000 grams
- **Bulk:** 5,000 grams or more

**Business value:** Supports weight-based inventory segmentation.

#### Q8. What is the total inventory weight for each category?
Calculated total inventory weight using product weight multiplied by available quantity.

**Business value:** Helps assess category-level storage and inventory handling requirements.

## 💡 SQL Concepts Demonstrated

This project demonstrates practical use of:

- `SELECT`, `WHERE`, `DISTINCT`
- `ORDER BY` and `LIMIT`
- `GROUP BY` and `HAVING`
- Aggregate functions: `COUNT()`, `SUM()`, `AVG()`
- `ROUND()` for numerical formatting
- `CASE WHEN` for conditional categorization
- `UPDATE` and `DELETE` for data cleaning
- Filtering with `AND` and `OR`
- Calculated columns and derived metrics

## 📊 Key Business Takeaways

The analysis is designed to help answer questions about:

- Products offering the largest discounts.
- High-priced products that require restocking attention.
- Categories with the highest average discounts.
- Product-level unit-price competitiveness.
- Category-wise inventory value and weight.
- Potential data quality issues affecting analysis.

*Actual findings and numerical results should be added after executing the queries against the dataset.*

## 🚀 How to Run the Project

1. Install PostgreSQL and open a SQL client such as pgAdmin or DBeaver.
2. Obtain the source dataset and import it into PostgreSQL.
3. Create the `zepto` table using the SQL schema in this repository.
4. Load the data into the table.
5. Run the exploration queries first.
6. Execute the data-cleaning statements after validating the source data and backing up the original records.
7. Run the business-analysis queries and review the results.

## 📁 Repository Structure

```text
zepto-sql-data-analysis/
│
├── README.md
├── zepto_analysis.sql
└── zeptov1.csv
```

*The filenames above are suggested; adjust them to match the files in your repository. Include the dataset only if you have permission to redistribute it.*

## 🔮 Future Improvements

- Add visualizations using Power BI or Tableau.
- Build a category-level dashboard for discounts and inventory.
- Analyze stock availability alongside product pricing.
- Compare MRP and discounted selling price to validate discount calculations.
- Improve data quality checks for duplicates, nulls, and invalid values.
- Incorporate sales transaction data to calculate actual revenue and sales performance.

## 👩‍💻 Author

**Aanshi Rakesh Kumar**

B.Tech in Computer Science & Engineering | Aspiring Data Analyst / Software Engineer



---

If you found this project useful, consider giving the repository a ⭐.
