# Final Recommendation — Regression-Based Business Insights

**To:** Retail Chain Leadership  
**From:** Jahnavi Gurram, Business Analyst  
**Date:** June 2025

---

## Which Factors Are Most Strongly Associated With Monthly Sales?

Based on the multiple regression model (R² = 0.835), the following factors show the strongest statistical association with monthly sales:

1. **Footfall** (coefficient: +₹28.53 per visitor, p < 0.001) — the single most powerful driver. A store with 1,000 more monthly visitors is associated with ~₹28,500 more in sales.

2. **Inventory Availability** (coefficient: +₹3,048 per 1%, p < 0.001) — keeping shelves stocked has a direct, significant link to sales. A 5% improvement in availability is associated with ~₹15,000 more in monthly sales.

3. **Marketing Spend** (coefficient: +₹1.18 per ₹1 spent, p < 0.001) — every rupee spent on marketing is associated with ₹1.18 in sales return. This is a positive ROI signal, though the marginal return may diminish at very high spend levels.

4. **Customer Rating** (coefficient: +₹14,210 per point, p = 0.003) — stores with higher customer satisfaction earn significantly more. A 0.5-point rating improvement is associated with ~₹7,100 more in sales.

5. **Staff Count** (coefficient: +₹3,041 per person, p = 0.015) — more staff is associated with better sales, likely through improved customer service and faster checkout.

6. **Store Type** — Airport stores significantly outperform Residential (-₹42,280) and High Street (-₹23,230) stores, holding everything else constant.

---

## What Should Leadership Focus On?

Based on the regression evidence, the three highest-impact levers are:

1. **Driving footfall** — this is the dominant factor. Strategies to increase store visits (local events, partnerships, visibility) should be the top priority.

2. **Improving inventory availability** — ensuring products are in stock is the most operationally controllable factor with a strong, proven association with sales.

3. **Maintaining marketing spend** — the positive ROI (~1.18x) suggests current marketing is working and should not be cut. Regional allocation could be optimized based on diminishing returns.

---

## What Should NOT Be Over-Interpreted?

1. **Average discount percentage** — the regression shows no statistically significant relationship between discount depth and monthly sales (p = 0.174). Leadership should not assume that deeper discounts automatically drive more revenue. This does not mean discounts are useless — they may drive volume without proportionally increasing revenue.

2. **Customer rating** — while statistically significant, it is likely a *result* of good operations rather than a *cause* of high sales. Trying to artificially boost ratings without improving the underlying experience will not move sales.

3. **Competitor distance** — excluded from the final model because it showed no meaningful predictive power. The distance to the nearest competitor does not appear to affect sales in this dataset.

---

## Recommended Business Actions

| Action | Expected Impact | Confidence |
|---|---|---|
| Invest in footfall-driving activities (local marketing, signage, events) | High — strongest coefficient | High |
| Maintain inventory above 90% availability | Medium — ₹3K per 1% | High |
| Keep marketing spend at current levels; do not cut | Medium — positive ROI | High |
| Staff Residential and High Street stores adequately | Medium — ₹3K per staff member | Moderate |
| Audit underperforming West and South stores (high negative residuals) | Variable — depends on root cause | Moderate |
| Avoid relying on discount depth as a primary sales strategy | N/A — no significant effect found | High |

---

## Risks and Limitations

1. **Correlation ≠ Causation.** Regression shows association, not cause-and-effect. Footfall is strongly correlated with sales, but it could be that popular stores attract more visitors (reverse causality) rather than visitors driving sales. Running a controlled experiment (e.g., increasing marketing in select stores to boost footfall) would be needed to confirm causation.

2. **Limited time window.** The data covers only 4 months (Jan–Apr 2025). Seasonal effects, holiday shopping patterns, and year-over-year trends are not captured.

3. **Missing variables.** The model explains 83.5% of variance, meaning 16.5% is unexplained. Factors like local economic conditions, store age, lease terms, parking availability, and manager effectiveness are not in the dataset.

4. **Multicollinearity risk.** Footfall and staff_count are likely correlated (busy stores need more staff). This means the individual coefficient for staff may be understated because footfall is absorbing some of its effect.

5. **Average discount is not significant** — but this could be because the discount range in the data is narrow (0–29%). A wider range might reveal a relationship. The absence of significance does not prove discounts don't matter — it means this dataset doesn't provide enough evidence either way.

6. **Airport stores as reference category** — Airport only has 28 data points (vs 116 for High Street). Conclusions about Airport vs other types should be treated with some caution due to the smaller sample.

---

## Why Regression Shows Association but Not Causation

Regression identifies mathematical relationships between variables — it finds that when X goes up, Y tends to go up too. But it cannot determine *why*. Three common issues:

- **Reverse causality:** High sales could cause high footfall (successful stores become destinations), not the other way around.
- **Omitted variable bias:** A third factor (e.g., store location quality) could drive both high footfall and high sales, making them appear connected when the real cause is something else entirely.
- **Self-selection:** Stores with higher marketing spend may already be in better locations or have better management — the spend isn't causing the sales; both are caused by being a priority store.

To move from association to causation, the business would need to run controlled experiments — like increasing marketing spend in randomly selected stores and comparing outcomes.
