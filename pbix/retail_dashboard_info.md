# Retail Sales Dashboard - PBIX File Info

> **Note:** The `.pbix` file is not stored in this repository due to GitHub's file size limits.
> You can recreate the dashboard using the data and instructions below, or download the published version from Power BI Service.

---

## How to Build the Dashboard

### Step 1: Import Data
1. Open **Power BI Desktop**
2. Go to **Home → Get Data → Text/CSV**
3. Select `data/superstore_sales.csv` from this repository
4. Click **Load**

### Step 2: Add DAX Measures
1. Go to **Modeling → New Measure**
2. Copy and paste each measure from `pbix/DAX_measures.md`
3. Format measures appropriately (Currency, Percentage, etc.)

### Step 3: Create Report Pages

#### Page 1: Executive Summary
- **KPI Cards:** Total Sales, Total Profit, Profit Margin %, Total Orders
- **Line Chart:** Monthly Sales Trend (Order Date vs Total Sales)
- **Bar Chart:** Sales by Category
- **Donut Chart:** Sales by Region

#### Page 2: Sales Deep Dive
- **Matrix:** Product Sub-Category vs Region with Sales and Profit
- **Scatter Plot:** Sales vs Profit by Product (identify profitable products)
- **Waterfall Chart:** Profit breakdown by Category
- **Slicer:** Year, Region, Segment

#### Page 3: Customer Analysis
- **Bar Chart:** Top 10 Customers by Sales
- **Map Visual:** Sales by State (filled map)
- **Table:** Customer details with Order Count and Total Sales
- **KPI:** Total Customers, Sales per Customer

#### Page 4: Product Performance
- **Bar Chart:** Top 10 Products by Revenue
- **Heatmap Matrix:** Sub-Category vs Ship Mode
- **Bar Chart:** Discount Impact by Category
- **Line Chart:** Quantity Sold over Time

---

## Dashboard Filters (Slicers)
Add these slicers to all pages:
- **Year** (from Order Date)
- **Region** (East, West, Central, South)
- **Segment** (Consumer, Corporate, Home Office)
- **Category** (Furniture, Office Supplies, Technology)

---

## Publishing to Power BI Service

1. In Power BI Desktop, click **File → Publish → Publish to Power BI**
2. Sign in with your Microsoft/work account
3. Select your workspace
4. Once published:
   - Go to [app.powerbi.com](https://app.powerbi.com)
   - Find the report in your workspace
   - Click **Share** to get a shareable link
   - Add the live report URL to your README badge

---

## Theme & Formatting

```
Background Color: #1E1E2E (dark) or #F8F9FA (light)
Primary Color: #4F81C7 (blue)
Accent Color: #E07B39 (orange)
Font: Segoe UI, 10pt body, 14pt headers
```

---

## File Structure Reference

```
retail-powerbi-dashboard/
├── data/
│   └── superstore_sales.csv       # Source dataset (20 rows sample)
├── pbix/
│   ├── DAX_measures.md           # All custom DAX measures
│   └── retail_dashboard_info.md  # This file - build instructions
├── screenshots/
│   └── README.md                  # Dashboard screenshots
└── README.md                      # Project overview
```
