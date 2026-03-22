# DAX Measures Reference

This file documents all custom DAX measures used in the **Retail Sales Power BI Dashboard**.
Use these in Power BI Desktop by going to **Modeling → New Measure**.

---

## Sales Metrics

### Total Sales
```dax
Total Sales = SUM('superstore_sales'[Sales])
```

### Total Profit
```dax
Total Profit = SUM('superstore_sales'[Profit])
```

### Total Orders
```dax
Total Orders = DISTINCTCOUNT('superstore_sales'[Order ID])
```

### Total Quantity
```dax
Total Quantity = SUM('superstore_sales'[Quantity])
```

### Profit Margin %
```dax
Profit Margin % = 
DIVIDE(
    SUM('superstore_sales'[Profit]),
    SUM('superstore_sales'[Sales]),
    0
) * 100
```

### Average Order Value
```dax
Avg Order Value = 
DIVIDE(
    SUM('superstore_sales'[Sales]),
    DISTINCTCOUNT('superstore_sales'[Order ID]),
    0
)
```

---

## Time Intelligence Measures

### Sales YTD
```dax
Sales YTD = 
CALCULATE(
    SUM('superstore_sales'[Sales]),
    DATESYTD('superstore_sales'[Order Date])
)
```

### Sales Previous Year
```dax
Sales PY = 
CALCULATE(
    SUM('superstore_sales'[Sales]),
    SAMEPERIODLASTYEAR('superstore_sales'[Order Date])
)
```

### YoY Sales Growth %
```dax
YoY Growth % = 
DIVIDE(
    [Total Sales] - [Sales PY],
    [Sales PY],
    0
) * 100
```

### Sales Last 30 Days
```dax
Sales Last 30 Days = 
CALCULATE(
    SUM('superstore_sales'[Sales]),
    DATESINPERIOD(
        'superstore_sales'[Order Date],
        MAX('superstore_sales'[Order Date]),
        -30,
        DAY
    )
)
```

---

## Customer Metrics

### Total Customers
```dax
Total Customers = DISTINCTCOUNT('superstore_sales'[Customer ID])
```

### Sales per Customer
```dax
Sales Per Customer = 
DIVIDE(
    SUM('superstore_sales'[Sales]),
    DISTINCTCOUNT('superstore_sales'[Customer ID]),
    0
)
```

### New Customers (Current Year)
```dax
New Customers = 
CALCULATETABLE(
    DISTINCTCOUNT('superstore_sales'[Customer ID]),
    FILTER(
        'superstore_sales',
        YEAR('superstore_sales'[Order Date]) = YEAR(TODAY())
    )
)
```

---

## Category & Product Metrics

### Top Category Sales
```dax
Top Category = 
CALCULATE(
    SUM('superstore_sales'[Sales]),
    TOPN(1, VALUES('superstore_sales'[Category]), [Total Sales], DESC)
)
```

### Category Profit Rank
```dax
Category Profit Rank = 
RANKX(
    ALL('superstore_sales'[Category]),
    [Total Profit],
    ,
    DESC,
    Dense
)
```

### Discount Impact
```dax
Discount Impact = 
SUMX(
    'superstore_sales',
    'superstore_sales'[Sales] * 'superstore_sales'[Discount]
)
```

---

## Regional Metrics

### Regional Sales %
```dax
Regional Sales % = 
DIVIDE(
    SUM('superstore_sales'[Sales]),
    CALCULATE(SUM('superstore_sales'[Sales]), ALL('superstore_sales'[Region])),
    0
) * 100
```

---

## Usage Notes

- All measures assume the table is named `superstore_sales` after import
- For time intelligence to work, mark `Order Date` as a **Date Table** in Power BI
- Format `Profit Margin %` and `YoY Growth %` as **Percentage** with 2 decimal places
- Format `Total Sales`, `Total Profit`, `Avg Order Value` as **Currency ($)**
