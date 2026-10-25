---
name: client-report-writing
description: "Use when drafting or editing the food-delivery analysis client report, executive summary, evidence-backed recommendations, or presentation narrative from this project's notebooks."
---

# Client Report Writing

Turn verified notebook outputs into a concise Arabic, client-facing report for an operations manager. This skill is specific to communicating this project's results and does not repeat the ready-made analysis skills.

## Procedure

1. Read the root `AGENTS.md`, reporting requirements, `notebooks/analysis.ipynb`, and relevant data-quality documentation.
2. Treat executed notebook outputs as the source of truth. Verify every number against its producing cell; never invent or estimate a reported figure.
3. Organize the report around weekly demand; categories and meals; centers; promotions and discount; variability; and recommendations.
4. Lead with the most decision-relevant finding, explain it in plain Arabic, and cite its notebook section and code cell. Label estimated revenue as an estimate and explain its calculation.
5. Use descriptive or associational language for observational data. Do not claim causality from correlation or a difference test. Explain effect sizes, uncertainty, and multiple-testing caveats where applicable.
6. Provide at least three actionable, evidence-linked recommendations and name a measurable follow-up KPI for each.
7. Include a dedicated **حدود التحليل** section specific to data gaps, assumptions, missing weeks, repeated observations, test limitations, and unavailable outcomes.
8. Verify every number and link, and ensure recommendations are no stronger than the evidence.

## Output checklist

- Every figure cites the exact notebook section and code cell.
- At least three recommendations include follow-up measures.
- The limitations section is explicit and dataset-specific.
- No unsupported causal claims or unverified figures.
