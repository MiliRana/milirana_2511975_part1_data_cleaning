# Sales Orders Data Cleaning and Analysis Project

## Problem Summary

The objective of this project was to clean a raw sales orders dataset, identify data quality issues, apply business rules, create calculated fields, generate data quality reports, and build pivot-based business summaries for analysis.

---

# Dataset Description

The dataset contains sales transaction records including:

* Order information
* Customer details
* Product details
* Sales and cost data
* Payment status
* Order status
* Shipping information
* Geographic information

Key fields include:

* Order ID
* Order Date
* Ship Date
* Customer ID
* Customer Name
* Segment
* Region
* Category
* Sub-Category
* Product Name
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Payment Status
* Order Status

---

# Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Formulas
* Conditional Formatting
* Data Validation
* Filters and Sorting

---

# Cleaning Steps Performed

### 1. Missing Value Handling

* Missing Region values replaced with "Unknown"
* Missing Ship Mode values replaced with "Unknown"
* Missing Discount values replaced with 0 where applicable

### 2. Duplicate Detection

* Exact duplicate rows identified
* Duplicate copies flagged
* Duplicate Order IDs reviewed separately

### 3. Date Cleaning

* Standardized Order Date
* Standardized Ship Date
* Calculated shipping delay days
* Validated shipping dates

### 4. Data Validation

* Checked discount values
* Checked shipping records
* Reviewed payment and order statuses

### 5. Calculated Columns Created

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

# Business Rules Applied

| Rule                         | Action Taken                            |
| ---------------------------- | --------------------------------------- |
| Missing Region               | Filled with "Unknown"                   |
| Missing Ship Mode            | Filled with "Unknown"                   |
| Missing Discount             | Treated as 0 when valid                 |
| Negative Discount            | Flagged as invalid                      |
| Discount Above Allowed Range | Flagged as invalid                      |
| Cancelled Orders             | Excluded from completed sales summaries |
| Failed Payments              | Excluded from completed sales summaries |
| Refunded Orders              | Summarized separately                   |
| Ship Date Before Order Date  | Flagged as invalid shipping record      |

---

# Summary of Data Quality Issues Found

| Issue                  | Count |
| ---------------------- | ----- |
| Missing Region         | 26    |
| Missing Ship Mode      | 40    |
| Missing Discount       | 16    |
| Exact Duplicate Rows   | 40    |
| Exact Duplicate Copies | 20    |
| Cancelled Orders       | 146   |
| Failed Payments        | 69    |
| Refunded Payments      | 72    |

---

# Summary of Final Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

---

# Key Business Insights

* Some regions contained missing geographic information and required standardization.
* Cancelled orders represented a significant portion of transactions.
* Failed and refunded payments require separate monitoring.
* Sales and profitability vary across product categories and regions.
* Customer segments show different profit margin patterns.
* Monthly sales trends help identify seasonal performance patterns.

---

# Assumptions and Limitations

## Assumptions

* Missing Region values represent unavailable location information.
* Missing Ship Mode values represent unavailable shipping information.
* Missing Discount values were treated as 0 only when other sales fields were valid.
* Calculated sales and profit values were used for consistency.

## Limitations

* Duplicate Order IDs may require manual business review.
* No external source was available for validation.
* Returned and refunded transactions may represent legitimate business events.
* Analysis is limited to information available in the dataset.

---

# Screenshots Included

The project submission includes screenshots of:

* raw_data_preview.png
* cleaned_data_preview.png
* pivot_summary_1.png
* pivot_summary_2.png
