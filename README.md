![img alt](<img width="1324" height="619" alt="image" src="https://github.com/user-attachments/assets/cf2d8aef-d93b-4e6f-9936-bae7db09d412" />)

# McDonald’s Sales Data Analysis

# Project Overview
This project analyzes McDonald’s sales and order data using Excel Power Query, Power Pivot, and Pivot Tables.  
The dataset contains menu item details and customer order transactions.

The goal of this project is to:
- Clean and transform raw data
- Create relationships between tables
- Analyze sales trends
- Build an interactive dashboard

---

# Dataset Information

# 1. Menu Item Table (`menu_item`)
Contains product details.

| Column Name | Description |
|---|---|
| menu_item_id | Unique ID of menu item |
| item_name | Name of menu item |
| category | Food category |
| price | Item price |

---

# 2. Order Details Table (`order_details`)
Contains customer order transactions.

| Column Name | Description |
|---|---|
| order_details_id | Unique transaction ID |
| order_id | Order number |
| order_date | Date of order |
| order_time | Time of order |
| item_id | Menu item ID |

---

# Power Query Data Cleaning Steps

# Menu Item Query
# Performed Operations
- Imported Excel workbook
- Promoted headers
- Changed data types
- Removed null values
- Removed duplicate menu item IDs

# Final Columns
- menu_item_id
- item_name
- category
- price

---

# Order Details Query
# Performed Operations
- Imported CSV file
- Promoted headers
- Changed data types
- Replaced NULL values
- Filled down missing item IDs
- Added Month Name column
- Added Day Name column
- Created workday_type column
- Added Hour column
- Merged with menu_item table
- Expanded item details

# New Generated Columns
| Column | Purpose |
|---|---|
| Month Name | Monthly analysis |
| Day Name | Daily trend analysis |
| workday_type | Weekday vs Weekend analysis |
| Hour | Time-based order analysis |

---

# Data Model Relationship

| Table | Column | Relationship |
|---|---|---|
| menu_item | menu_item_id | One-to-Many |
| order_details | item_id | One-to-Many |

---

# Key Business Questions

# Sales Analysis
- What is the total sales revenue?
- Which menu items generate the highest revenue?
- Which categories perform best?

# Order Analysis
- What are the busiest hours?
- Which days receive the highest orders?
- Weekday vs Weekend sales comparison

# Trend Analysis
- Monthly sales trends
- Category performance by month
- Top 5 selling menu items

---

# Important Measures (DAX)

# Total Revenue
```DAX
Total Revenue =
SUMX(
    order_details,
    order_details[price]
)
```

# Total Orders
```DAX
Total Orders =
DISTINCTCOUNT(order_details[order_id])
```

# Average Order Value
```DAX
Average Order Value =
DIVIDE([Total Revenue],[Total Orders])
```

---

# Dashboard Features

# KPIs
- Total Revenue
- Total Orders
- Average Order Value
- Total Menu Items

# Charts
- Sales by Category
- Orders by Hour
- Monthly Revenue Trend
- Weekday vs Weekend Orders
- Top 5 Menu Items

# Slicers
- Category
- Month
- Workday Type

---

# Tools Used
- Microsoft Excel
- Power Query
- Power Pivot
- Pivot Tables
- DAX

---

# Author
Darshan Sangala

