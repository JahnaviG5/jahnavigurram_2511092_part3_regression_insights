# Part 3: Regression-Based Business Insights & Model Interpretation

**Jahnavi Gurram | bitsom_ba_2511092**

---

## Business Problem Summary

The retail chain's leadership wants to understand which factors drive monthly store sales so they can make informed decisions about marketing budgets, staffing, inventory, and store-type prioritization. Regression analysis is used to quantify the strength and direction of each factor's association with sales.

---

## Dataset Description

| Property | Value |
|---|---|
| File | business_regression_data.xlsx |
| Records | 320 (80 stores × 4 months) |
| Dependent variable | monthly_sales |
| Time period | January–April 2025 |
| Missing values | competitor_distance_km (6), customer_rating (8) — filled with median |

---

## Variables

### Dependent Variable
- `monthly_sales` — total monthly revenue per store (₹)

### Numerical Independent Variables
- `marketing_spend` — monthly marketing budget per store
- `footfall` — number of monthly walk-in customers
- `avg_discount_pct` — average discount offered (0–0.29)
- `staff_count` — number of employees
- `inventory_availability_pct` — percentage of SKUs in stock
- `customer_rating` — average customer rating (2.8–5.0)
- `competitor_distance_km` — distance to nearest competitor

### Categorical Independent Variables
- `region` — East, North, South, West
- `store_type` — Airport, High Street, Mall, Residential

### Variables Excluded From Final Model
- `competitor_distance_km` — no significant relationship with sales
- `store_id` — identifier, not a predictor
- `month` — only 4 months, too few for meaningful time variable
- `monthly_profit` — derived from sales, cannot be used as predictor

---

## Regression Approach

1. Cleaned dataset — filled 14 missing values with median
2. Created dummy variables for region (reference: East) and store_type (reference: Airport)
3. Ran 3 simple linear regressions (one variable at a time)
4. Ran 1 multiple regression with 6 numerical + 6 dummy variables
5. Compared models by R², p-values, and business interpretability
6. Analyzed residuals to identify over/underpredicted stores

---

## Dummy Variable Approach

- **Region:** 4 categories → 3 dummies (region_North, region_South, region_West). Reference = East.
- **Store Type:** 4 categories → 3 dummies (store_High Street, store_Mall, store_Residential). Reference = Airport.
- One category dropped from each to avoid perfect multicollinearity with the intercept.

---

## Model Comparison Summary

| Model | R² | Key Insight |
|---|---|---|
| Simple: footfall | 0.7363 | Footfall alone explains 74% — strongest single predictor |
| Simple: staff_count | 0.6523 | Staff count explains 65% |
| Simple: marketing_spend | 0.1672 | Marketing alone is a weak predictor |
| **Multiple (Full)** | **0.8350** | **Best model — all factors combined explain 83.5%** |

---

## Final Model Selected

**Multiple Regression** (R² = 0.835, Adjusted R² = 0.829)

Significant predictors (p < 0.05): footfall, marketing_spend, inventory_availability_pct, customer_rating, staff_count, region_South, region_West, store_High Street, store_Residential.

Non-significant: avg_discount_pct, region_North, store_Mall.

---

## Business Recommendation

1. **Prioritize footfall** — it's the dominant sales driver. Invest in activities that bring people to stores.
2. **Keep inventory above 90%** — strong, actionable association with sales.
3. **Maintain marketing spend** — positive ROI (~₹1.18 return per ₹1).
4. **Staff adequately** — more staff is associated with more sales.
5. **Don't rely on discounts** — no significant sales impact found.
6. **Audit underperforming stores** — residual analysis identified specific stores selling well below their predicted potential.

---

## Assumptions and Limitations

- Regression shows association, not causation — controlled experiments needed to confirm
- 4-month data window is too short for seasonal analysis
- 16.5% of sales variation is unexplained by the model
- Footfall and staff_count may be correlated (multicollinearity)
- Airport stores have only 28 observations vs 100+ for other types

---

## Screenshots

| File | Shows |
|---|---|
| screenshots/simple_regression_output.png | All simple regression results |
| screenshots/multiple_regression_output.png | Full multiple regression coefficients and R² |
| screenshots/residuals_preview.png | Top 5 underpredicted and overpredicted stores |
| screenshots/model_comparison_preview.png | Side-by-side model comparison |
