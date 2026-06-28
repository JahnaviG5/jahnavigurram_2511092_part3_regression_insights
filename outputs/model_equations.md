# Model Equations

## Simple Regression Equations

### Model 1: Marketing Spend
```
Monthly Sales = 5,60,777 + 2.1296 × marketing_spend
```
For every ₹1 increase in marketing spend, monthly sales increase by approximately ₹2.13. R² = 0.1672.

### Model 2: Footfall
```
Monthly Sales = 4,46,411 + 35.678 × footfall
```
For every 1 additional visitor, monthly sales increase by approximately ₹35.68. R² = 0.7363.

### Model 3: Staff Count
```
Monthly Sales = 4,00,551 + 16,984 × staff_count
```
For every additional staff member, monthly sales increase by approximately ₹16,984. R² = 0.6523.

---

## Multiple Regression Equation (Final Model)

```
Monthly Sales = 72,500
    + 1.1846 × marketing_spend
    + 28.527 × footfall
    - 49,250 × avg_discount_pct
    + 3,041 × staff_count
    + 3,048 × inventory_availability_pct
    + 14,210 × customer_rating
    + 5,270 × region_North
    + 19,280 × region_South
    + 18,020 × region_West
    - 23,230 × store_High_Street
    - 12,410 × store_Mall
    - 42,280 × store_Residential
```

R² = 0.835 | Adjusted R² = 0.829

---

## Coefficient Explanations

| Variable | Coefficient | Meaning |
|---|---|---|
| Intercept | 72,500 | Baseline sales for an Airport store in the East region with all other variables at zero |
| marketing_spend | +1.18 | Each ₹1 of marketing spend is associated with ₹1.18 more in sales |
| footfall | +28.53 | Each additional walk-in customer is associated with ₹28.53 more in sales |
| avg_discount_pct | -49,250 | Higher discount depth is associated with lower sales (not statistically significant, p=0.17) |
| staff_count | +3,041 | Each additional staff member is associated with ₹3,041 more in sales |
| inventory_availability_pct | +3,048 | Each 1% increase in inventory availability is associated with ₹3,048 more in sales |
| customer_rating | +14,210 | Each 1-point increase in rating is associated with ₹14,210 more in sales |
| region_North | +5,270 | North stores earn ~₹5,270 more than East stores (not significant, p=0.45) |
| region_South | +19,280 | South stores earn ~₹19,280 more than East stores |
| region_West | +18,020 | West stores earn ~₹18,020 more than East stores |
| store_High Street | -23,230 | High Street stores earn ~₹23,230 less than Airport stores |
| store_Mall | -12,410 | Mall stores earn ~₹12,410 less than Airport stores (not significant, p=0.20) |
| store_Residential | -42,280 | Residential stores earn ~₹42,280 less than Airport stores |

---

## Dummy Variable Explanation

### Region Dummies
- **Reference category:** East
- Three dummy variables created: region_North, region_South, region_West
- Each dummy is 1 if the store is in that region, 0 otherwise
- Coefficients represent the sales difference compared to East region

### Store Type Dummies
- **Reference category:** Airport
- Three dummy variables created: store_High Street, store_Mall, store_Residential
- Coefficients represent the sales difference compared to Airport stores
- Airport was chosen as reference because it had the fewest stores (28), making it a clear comparison baseline

### Why Drop One Category?
If all four dummies are included, the model encounters perfect multicollinearity — the columns sum to 1 for every row, which is identical to the intercept. Dropping one category (the "reference") avoids this and makes the remaining coefficients interpretable as differences from the baseline.

---

## Final Model Selected

**Multiple Regression (Full Model)** with R² = 0.835.

### Reason for Selection
- It explains 83.5% of the variation in monthly sales — far more than any single-variable model
- It accounts for the combined effects of operations, marketing, staffing, and location simultaneously
- It identifies which factors are statistically significant when controlling for everything else (e.g., staff_count is significant alone but weaker once footfall is included, suggesting they overlap)
- It allows leadership to see the relative importance of each lever they can pull
