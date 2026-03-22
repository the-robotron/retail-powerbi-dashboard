# Business Metrics Definitions & KPI Glossary

This file defines every KPI and metric used in the **Retail Sales Power BI Dashboard**.
Use this as a reference when reviewing visuals or presenting findings to stakeholders.

---

## Revenue Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Total Sales** | SUM(Sales) | YoY growth >10% | Core revenue measure |
| **Total Profit** | SUM(Profit) | Profit margin >15% | Business health |
| **Profit Margin %** | (Profit / Sales) * 100 | >15% | Higher = better efficiency |
| **Net Revenue** | Sales – Discounts | Maximize | Revenue after discounts applied |
| **Gross Margin** | (Sales – COGS) / Sales | >40% | Healthy for retail |
| **Revenue per Order** | Total Sales / Orders | Trending up | Avg transaction value |
| **Revenue per Customer** | Total Sales / Customers | Trending up | Customer value indicator |

---

## Order & Volume Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Total Orders** | COUNT(DISTINCT Order ID) | Growing MoM | Business activity |
| **Total Quantity** | SUM(Quantity) | Trending up | Volume sold |
| **Avg Order Value (AOV)** | Total Sales / Orders | >$200 | Higher AOV = better upsell |
| **Avg Items per Order** | Total Quantity / Orders | >2.5 | Basket size indicator |
| **Orders per Customer** | Orders / Customers | >1.5 | Repeat buy rate |

---

## Customer Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Total Customers** | COUNT(DISTINCT Customer ID) | Growing | Market penetration |
| **New Customers** | First-time buyers in period | +10% QoQ | Acquisition health |
| **Returning Customers** | Customers with >1 order | >30% | Loyalty health |
| **Customer Retention Rate** | Returning / Total * 100 | >30% | Key loyalty metric |
| **Sales per Customer** | Total Sales / Customers | Trending up | Lifetime value proxy |

---

## Time Intelligence Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Sales YTD** | DATESYTD aggregate | vs last YTD | Year progress |
| **Sales Previous Year** | SAMEPERIODLASTYEAR | Baseline | Comparison anchor |
| **YoY Growth %** | (Current – PY) / PY * 100 | >10% | Annual performance |
| **MoM Growth %** | (Current – Prev Month) / Prev * 100 | >5% | Monthly trend |
| **QoQ Growth %** | (Current Q – Prev Q) / Prev Q * 100 | >8% | Quarterly progress |
| **Sales Last 30 Days** | Rolling 30-day sum | Trending up | Recency indicator |

---

## Product & Category Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Category Revenue Share** | Category Sales / Total Sales * 100 | Balanced portfolio | Dependency risk |
| **Sub-Category Profit Rank** | RANKX by profit | Top 3 consistent | Product prioritisation |
| **Discount Impact** | SUM(Sales * Discount) | <15% of revenue | Over-discounting risk |
| **Return Rate** | Returned orders / Total | <5% | Quality signal |
| **Top Product Revenue** | Max single product revenue | Growing | Star product health |

---

## Regional Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Regional Sales %** | Region Sales / Total * 100 | Balanced | Market concentration risk |
| **Best Performing State** | Max revenue state | Growing | Geographic strength |
| **Sales per City** | City revenue / City customers | Trending up | Local market depth |

---

## Operational Metrics

| Metric | Formula | Target | Interpretation |
|--------|---------|--------|----------------|
| **Ship Mode Distribution** | Orders by ship mode % | Standard <70% | Fulfillment cost balance |
| **Avg Days to Ship** | AVG(Ship Date – Order Date) | <5 days | Customer satisfaction driver |
| **Segment Revenue Share** | Segment sales / Total | Corporate growing | Mix management |

---

## KPI Benchmarks for Superstore Retail

| KPI | Weak | Good | Excellent |
|-----|------|------|----------|
| Profit Margin % | <10% | 10–20% | >20% |
| AOV | <$150 | $150–$300 | >$300 |
| YoY Revenue Growth | <5% | 5–15% | >15% |
| Customer Retention | <20% | 20–40% | >40% |
| Return Rate | >10% | 5–10% | <5% |
| Discount Rate | >25% | 10–25% | <10% |

---

## Improvement Opportunities from Dashboard Data

| Observation | Metric Affected | Target Improvement | Action |
|-------------|----------------|-------------------|--------|
| Furniture has lowest profit margin | Profit Margin % | +5pp | Review supplier contracts; reduce discounts |
| Q1 consistently weakest quarter | QoQ Growth | Flat to positive | Launch Q1 promotional campaigns |
| Central region underperforms | Regional Sales % | +10% share | Increase marketing spend in Central |
| High discounts eroding margin | Discount Impact | Reduce to <10% | Discount cap policy + A/B testing |
| Standard Class dominates shipping | Ship Mode Distribution | Balance to 60% | Promote First Class for high-value orders |
| Home Office segment smallest | Segment Revenue Share | +5% share | B2B micro-business outreach program |
| Technology AOV highest but fewest orders | Category Orders | +15% orders | Bundle deals; cross-sell accessories |

---

## How to Use This File

1. Reference when explaining dashboard visuals to non-technical stakeholders
2. Use benchmarks to set dashboard alert thresholds (conditional formatting)
3. Update targets quarterly based on actuals
4. Link each visual to a metric defined here for documentation completeness

---

## Related Files

- [`DAX_measures.md`](DAX_measures.md) — Power BI formulas for each metric
- [`retail_dashboard_info.md`](retail_dashboard_info.md) — Dashboard build instructions
- [`../data/superstore_sales.csv`](../data/superstore_sales.csv) — Source data
