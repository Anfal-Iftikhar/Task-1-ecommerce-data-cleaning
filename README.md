# Task-1-ecommerce-data-cleaning
Cleaning raw e-commerce order data handling missing values, duplicates, type errors, and price validation using Python &amp; pandas. 
# 🧹 ecommerce-data-cleaning

> **DecodeLabs Industrial Training Kit — Project 1**  
> Batch 2026 | Data Analytics Track

---

## 📌 Project Overview

This project covers the foundational skill every data analyst must master before any analysis can begin: **data cleaning**. Raw e-commerce order data is rarely submission-ready — it contains missing values, duplicate records, inconsistent formatting, and logical errors. This project systematically identifies and resolves all such issues using Python and pandas.

The cleaned output (`Project1_Cleaned_Dataset.xlsx`) produced here serves as the base dataset for all subsequent projects in this training track.

---

## 🎯 Objectives

- Detect and handle missing values using appropriate strategies (drop, fill, impute)
- Identify and remove duplicate records
- Standardize inconsistent data formats (dates, strings, casing)
- Validate data types and correct mismatches
- Detect and treat outliers in numerical columns
- Create a `PriceCheck` column to validate `TotalPrice = Quantity × UnitPrice`
- Export a clean, analysis-ready dataset

---

## 🗂️ Dataset

| Property | Detail |
|---|---|
| File | `Raw_Ecommerce_Dataset.xlsx` |
| Records | ~1,200 orders |
| Columns | 15 (OrderID, Date, CustomerID, Product, Quantity, UnitPrice, ShippingAddress, PaymentMethod, OrderStatus, TrackingNumber, ItemsInCart, CouponCode, ReferralSource, TotalPrice, PriceCheck) |
| Date Range | January 2023 – June 2025 |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| pandas | Data manipulation and cleaning |
| numpy | Numerical operations |
| openpyxl | Excel file I/O |

---

## 📁 Project Structure

```
ecommerce-data-cleaning/
│
├── data/
│   ├── Raw_Ecommerce_Dataset.xlsx       # Original raw data (input)
│   └── Project1_Cleaned_Dataset.xlsx   # Cleaned output dataset
│
├── Project1_Data_Cleaning.py            # Main Python script
├── requirements.txt                     # Dependencies
└── README.md
## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/ecommerce-data-cleaning.git
cd ecommerce-data-cleaning

# 2. Install dependencies
pip install -r requirements.txt

# 3. Place raw dataset in data/ folder and run
python Project1_Data_Cleaning.py
## 🔑 Key Cleaning Steps

1. **Missing Value Treatment** — Identified nulls per column; filled categorical columns with mode and numerical with median
2. **Duplicate Removal** — Dropped exact duplicate rows based on OrderID
3. **Date Standardization** — Parsed all date strings to `datetime` format (`YYYY-MM-DD`)
4. **String Normalization** — Stripped whitespace, applied `.title()` casing to Product and PaymentMethod columns
5. **Type Enforcement** — Cast Quantity and ItemsInCart to `int`, UnitPrice and TotalPrice to `float`
6. **Outlier Detection** — Applied IQR method on UnitPrice and TotalPrice; flagged extreme values
7. **PriceCheck Validation** — Added derived column: `"Correct"` if `TotalPrice == Quantity × UnitPrice`, else `"Mismatch"`
## 📊 Output Summary
Records before cleaning : 1,250
Duplicates removed      :    50
Missing values handled  :    38
Type corrections        :     4 columns
PriceCheck mismatches   :  ~12%
Records after cleaning  : 1,200

