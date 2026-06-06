

# Amazon Sales Data Analysis

This repository contains a comprehensive data analysis workflow for Amazon sales records. The project involves raw data cleaning, text formatting fixes, and business intelligence reporting using Excel formulas (`VLOOKUP`) and Pivot Tables.

## 📂 Repository Structure

* `amazon.xlsx`: The cleaned, master dataset. This file contains the fully processed sales data with normalized formatting, ready for analysis.
* `amazon_sales.xlsx`: The reporting and insights dashboard. This file features dynamic Pivot Tables built from the cleaned data to track key performance indicators (KPIs).

---

## 📊 Dataset Schema

The underlying dataset contains the following attributes for each transaction:

| Column Name         | Description                                        |
| --------------------| -------------------------------------------------- |
| product_id          | Unique identifier for each product *(Primary Key)* |
| product_name        | Full title of the product                          |
| category            | Product categorization and sub-categories          |
| discounted_price    | Final selling price after discounts                |
| actual_price        | Original retail price (MSRP)                       |
| discount_percentage | Percentage reduction from the actual price         |
| rating              | Average customer review rating (out of 5)          |
| rating_count        | Total number of customer reviews                   |
| about_product       | Description of product features and specifications |
| user_id             | Unique identifier of the reviewing customer        |
| user_name           | Name of the reviewing customer                     |
| review_id           | Unique identifier of the customer review           |
| review_title        | Headline/title of the customer review              |
| review_content      | Full text of the customer review                   |
| img_link            | URL of the product image                           |
| product_link        | URL of the Amazon product page                     |



## 🛠️ Data Cleaning & Processing Steps (`amazon.xlsx`)

Before analysis, the raw dataset underwent several critical data-cleaning steps to ensure accuracy:

1. Encoding Fixes (Currency Symbols):
* Fixed corrupted text strings (e.g., `â‚¹`) resulting from CSV UTF-8 import errors.
* Cleaned and restored data formatting to native currency fields.


2. Cell Formatting Normalization:
* Resolved data type mismatches where financial numeric values were incorrectly formatted as `Percentage` (causing numbers like `1099` to erroneously display as `10990%`).
* Converted prices and ratings into proper `Currency` and `Number` formats.


3. Data Integration via VLOOKUP:
* Utilized exact-match vertical lookups (`=VLOOKUP(A2, Range, Col, FALSE)`) anchored by `product_id` to map, validate, and reference attributes across data tables seamlessly without creating circular references.


## 📈 Business Intelligence & Insights (`amazon_sales.xlsx`)

The `amazon_sales.xlsx` file utilizes **Pivot Tables** to aggregate the cleaned data and extract actionable retail insights:

* Sales Performance by Category: Analyzes which product categories drive the highest revenue based on `discounted_price`.
* Discount Optimization: Evaluates the relationship between `discount_percentage` and total `rating_count` to see if steeper discounts generate higher customer engagement.
* Product Rating Analysis: Identifies top-tier products by cross-referencing `rating` averages against overall sales volume.
