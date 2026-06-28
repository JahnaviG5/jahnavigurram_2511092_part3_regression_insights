# Residual Analysis

## What Are Residuals?

Residual = Actual Sales − Predicted Sales

A positive residual means the store performed better than the model expected (underpredicted). A negative residual means the store performed worse than expected (overpredicted).

## Top 5 Underpredicted Stores (Positive Residuals)

| Store | Region | Store Type | Actual Sales | Predicted | Residual |
|---|---|---|---|---|---|
| STR-1028 | East | Mall | ₹7,13,611 | ₹6,01,419 | +₹1,12,192 |
| STR-1073 | East | Residential | ₹8,13,317 | ₹7,11,191 | +₹1,02,125 |
| STR-1030 | West | Residential | ₹8,20,519 | ₹7,30,256 | +₹90,263 |
| STR-1026 | East | Mall | ₹6,25,514 | ₹5,36,308 | +₹89,206 |
| STR-1027 | West | High Street | ₹7,95,154 | ₹7,08,389 | +₹86,765 |

**Business interpretation:** These stores are outperforming what their observable factors (footfall, marketing, staff, etc.) would suggest. This could mean they benefit from factors not captured in the model — strong local brand presence, excellent store managers, favorable location within their area, or loyal customer base. These stores could be studied as best-practice examples for the rest of the chain.

## Top 5 Overpredicted Stores (Negative Residuals)

| Store | Region | Store Type | Actual Sales | Predicted | Residual |
|---|---|---|---|---|---|
| STR-1017 | West | High Street | ₹6,85,379 | ₹8,38,966 | -₹1,53,587 |
| STR-1023 | South | Mall | ₹6,27,172 | ₹7,66,067 | -₹1,38,895 |
| STR-1012 | West | Residential | ₹5,95,468 | ₹7,22,545 | -₹1,27,077 |
| STR-1007 | West | Mall | ₹8,00,452 | ₹9,15,179 | -₹1,14,727 |
| STR-1077 | South | Residential | ₹5,38,376 | ₹6,34,950 | -₹96,574 |

**Business interpretation:** These stores are underperforming relative to their inputs. They have the footfall, marketing spend, and staff count that should produce higher sales, but something is holding them back. Possible reasons include poor store layout, local competition not captured in the data, management issues, or unfavorable micro-location. These stores should be prioritized for operational audits.

## Patterns in Residuals

- West region appears in both lists — the region has high variance in performance, meaning some West stores do very well while others struggle despite similar inputs
- Residential stores appear frequently in both extremes — their performance is harder to predict, possibly because residential area dynamics vary more than mall or airport environments
- The model tends to overpredict more for West High Street and South Mall stores — leadership should investigate whether these specific combinations face unique local challenges

## Model Reliability

The residual standard deviation is approximately ₹42,000–43,000, meaning the model's predictions are typically within ₹42K of the actual value. For stores averaging ₹6.8 lakh in monthly sales, this represents roughly a 6% error margin — acceptable for strategic planning but not precise enough for store-level budgeting without additional local context.
