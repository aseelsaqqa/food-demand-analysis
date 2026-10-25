---
name: demand-metrics-calculation
description: "Use when calculating food-demand KPIs such as total or weekly orders, estimated revenue, discount rate, promotion share, top-demand meals, or demand variability from this project's data."
---

# Demand Metrics Calculation

Calculate reproducible operational demand indicators from the project's order data. This skill complements, rather than duplicates, the ready-made weekly exploration and promotion-testing skills.

## Procedure

1. Read the root `AGENTS.md` and the loading, join, quality, and KPI sections of `notebooks/analysis.ipynb`.
2. Read `train.csv` and lookup data from `data/raw/` only. Never modify, rename, delete, move, or commit any file in that directory. `test.csv` has no `num_orders` target and is not a source for historical demand KPIs.
3. Before aggregation, identify the row grain and verify the join keys. After every join and every cleaning, drop, or filtering operation, print the number of rows and columns and, where available, the sum of `num_orders`; compare before/after values and explain changes.
4. Use documented definitions:
   - Total orders: sum of `num_orders`.
   - Weekly total and mean weekly orders: group by `week` and sum `num_orders`, then summarize weekly totals.
   - Estimated revenue: `checkout_price * num_orders`; label it an estimate, not profit.
   - Relative discount: `(base_price - checkout_price) / base_price` only when `base_price > 0`.
   - Promotion share: fraction of observed rows with the relevant flag equal to `1`; distinguish row share from order-weighted share.
   - Demand variability: standard deviation divided by mean for a clearly stated aggregation unit. Do not replace absent weeks with zero unless justified.
5. For top-demand shares, sort by summed orders and show the cumulative share, including the item crossing the threshold.
6. Display intermediate checks, state units and denominators, and round only presentation values.
7. Cite every reported metric to the notebook section and code cell. Describe observational results without implying causation.

## Output checklist

- Metric definition, grain, units, and denominator are explicit.
- Join and cleaning counts and totals are traceable.
- Results are reproducible, with no changes to `data/raw/`.
- Recommendations state their evidence and limitations.
