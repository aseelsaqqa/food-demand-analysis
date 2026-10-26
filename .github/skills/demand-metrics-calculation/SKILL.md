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
   - Weekly total and mean weekly orders: group by `week` and sum `num_orders`, then summarize those weekly totals.
   - Estimated revenue: `checkout_price * num_orders`; label it an estimate, not profit.
   - Relative discount: `(base_price - checkout_price) / base_price` only when `base_price > 0`; state how invalid or missing values are handled.
   - Promotion share: fraction of observed rows with the relevant promotion flag equal to `1`; distinguish row share from order-weighted share.
   - Demand variability: standard deviation divided by mean orders for a clearly stated aggregation unit. Do not replace absent weeks with zero unless the data definition justifies it.
5. For top-demand shares, sort the requested entities by summed orders and show the cumulative share, including the item that crosses the chosen threshold.
6. Display intermediate tables or assertions needed to check totals and arithmetic. Avoid unexplained rounding; keep adequate precision in calculations and round only presentation values.
7. Cite every reported metric to the notebook section and code cell that computes it. Describe observational results without implying causation.

## Output checklist

- Metric definition, grain, units, and denominator are explicit.
- Row/column counts and order totals remain traceable through joins and cleaning.
- Results are reproducible from the notebook, with no changes to `data/raw/`.
- Any recommendation states its evidence and the limits of the metric.
