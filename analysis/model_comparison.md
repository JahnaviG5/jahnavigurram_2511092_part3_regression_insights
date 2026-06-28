# Model Comparison

## Models Built

| Model | Dependent Variable | Independent Variables | R² |
|---|---|---|---|
| Simple 1 | monthly_sales | marketing_spend | 0.1672 |
| Simple 2 | monthly_sales | footfall | 0.7363 |
| Simple 3 | monthly_sales | staff_count | 0.6523 |
| Multiple (Full) | monthly_sales | marketing_spend, footfall, avg_discount_pct, staff_count, inventory_availability_pct, customer_rating, region dummies, store_type dummies | 0.8350 |

## Comparison

### R-squared (Explanatory Power)
- Footfall alone explains 73.6% of sales variation — it is the single most powerful predictor
- Staff count alone explains 65.2% — also strong
- Marketing spend alone only explains 16.7% — meaningful but not sufficient on its own
- The full multiple regression explains 83.5% — combining all factors gives the most complete picture

### Significant Variables (p < 0.05 in the full model)
- **footfall** (p < 0.001) — strongest driver
- **marketing_spend** (p < 0.001) — significant positive effect
- **inventory_availability_pct** (p < 0.001) — stocking shelves matters
- **customer_rating** (p = 0.003) — satisfaction links to sales
- **staff_count** (p = 0.015) — more staff helps, but effect is smaller when controlling for other factors
- **region_South** (p = 0.007) and **region_West** (p = 0.004) — these regions outperform East (baseline)
- **store_Residential** (p < 0.001) and **store_High Street** (p = 0.012) — underperform compared to Airport stores

### Non-significant Variables
- **avg_discount_pct** (p = 0.174) — discount depth does not significantly drive sales in this model
- **region_North** (p = 0.451) — not meaningfully different from East
- **store_Mall** (p = 0.197) — not significantly different from Airport stores

### Business Usefulness
The full multiple regression model is the most useful for leadership decisions because it accounts for the combined effects of all factors simultaneously. A simple regression on footfall alone is useful for quick back-of-envelope estimates but misses the impact of operational factors like inventory and staffing.

### Limitations
- The model does not capture seasonality beyond the 4-month window in the data
- Competitor distance was not significant and was excluded from the final model
- Correlation is not causation — higher footfall is associated with higher sales, but increasing footfall artificially (e.g., through promotions) may not produce the same effect
- Store-level factors not in the dataset (local economy, parking, store age) may explain some residual variation
