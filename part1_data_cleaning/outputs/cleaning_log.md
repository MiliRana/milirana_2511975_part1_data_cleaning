# Data Cleaning Log

## Dataset Information

* Original Dataset Records: 932
* Unique Order IDs: 900
* Cleaned Dataset File: cleaned_orders.xlsx

---

# 1. Issues Identified

### Missing Values

* Missing Region records found: 26
* Missing Ship Mode records found: 40
* Missing Discount records found: 16

### Duplicate Records

* Exact duplicate rows identified: 40
* Exact duplicate copies flagged: 20
* Duplicate Order IDs identified and reviewed

### Data Validation Issues

* Negative discount values checked
* Discounts above allowed business threshold checked
* Shipping dates validated against order dates
* Cancelled, refunded, and failed-payment transactions identified

---

# 2. Cleaning Actions Performed

### Missing Region

* Blank Region values were replaced with "Unknown".

### Missing Ship Mode

* Blank Ship Mode values were replaced with "Unknown".

### Missing Discount

* Missing discount values were replaced with 0 where other sales-related fields were available and valid.

### Duplicate Handling

* Exact duplicate records were identified.
* First occurrence retained.
* Duplicate copies flagged for removal.

### Date Standardization

* Order Date converted to Clean Order Date.
* Ship Date converted to Clean Ship Date.
* Shipping delay calculated.

### Calculated Columns Created

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

# 3. Business Rules Applied

### Rule: Missing Region

Action:

* Filled with "Unknown".
* Included in data quality reporting.

### Rule: Missing Ship Mode

Action:

* Filled with "Unknown".
* Included in data quality reporting.

### Rule: Missing Discount

Action:

* Treated as 0 when other sales fields were valid.

### Rule: Negative Discount

Action:

* Checked and flagged as invalid if present.

### Rule: Discount Above Allowed Range

Action:

* Checked and flagged as invalid if present.

### Rule: Cancelled Orders

Action:

* Excluded from completed sales summaries.
* Tracked separately in pivot reporting.

### Rule: Failed Payments

Action:

* Excluded from completed sales summaries.
* Tracked separately in pivot reporting.

### Rule: Refunded Orders

Action:

* Summarized separately in pivot reporting.

### Rule: Ship Date Before Order Date

Action:

* Flagged as invalid shipping record.

---

# 4. Assumptions Made

* Missing Region values represent unavailable location information and were replaced with "Unknown".
* Missing Ship Mode values represent unavailable shipping information and were replaced with "Unknown".
* Missing Discount values were assumed to be 0 only when all related sales fields were valid.
* Calculated sales and profit values were considered more reliable for analysis than raw values when discrepancies existed.
* Cancelled, refunded, and failed-payment orders should not be included in completed sales reporting.

---

# 5. Records Removed

* Exact duplicate copies identified: 20
* Duplicate copies flagged for removal.

---

# 6. Records Flagged

* Duplicate Order ID records flagged for review.
* Invalid shipping records flagged.
* Invalid discount records flagged where applicable.
* Cancelled, refunded, and failed-payment transactions identified and tracked separately.

---

# 7. Limitations

* Business decisions regarding duplicate Order IDs require manual review.
* Returned/refunded transactions may represent legitimate business events and were not automatically removed.
* Data quality assessment is based only on fields provided in the dataset.
* No external source was available to validate customer, product, or transaction information.

---

# Deliverables Produced

* cleaned_orders.xlsx
* data_quality_report.xlsx
* pivot_summary.xlsx
* cleaning_log.md
