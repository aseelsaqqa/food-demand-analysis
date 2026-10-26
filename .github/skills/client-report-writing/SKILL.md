---
name: client-report-writing
description: "Use when drafting or editing the food-delivery analysis client report, executive summary, evidence-backed recommendations, or presentation narrative from this project's notebooks."
---

# Client Report Writing

Turn verified notebook outputs into a concise Arabic, client-facing report for an operations manager. This skill is specific to communicating the project's results; it does not repeat the ready-made analysis skills.

## Procedure

1. Read the root `AGENTS.md`, the client-report requirements, `notebooks/analysis.ipynb`, and relevant analysis or cleaning documentation before drafting.
2. Treat the executed notebook and its displayed tables as the source of truth. Verify each number against its producing cell; never estimate, invent, or copy a number without a notebook reference.
3. Organize the report around the client's questions: weekly demand; categories and meals; centers; promotions and discount; variable demand; recommendations.
4. Begin with the most decision-relevant result. Explain its practical meaning in plain Arabic, then give the evidence and point to the corresponding notebook section and code cell. Label estimated revenue as an estimate and describe its calculation.
5. Use descriptive and associational language for observational data. Do not say a promotion, discount, center type, or other factor "caused" a demand change unless the study design provides valid causal evidence. Explain test results, effect size, uncertainty, and multiple-testing caveats where applicable.
6. Provide at least three actionable recommendations. For each, distinguish the observed evidence from the proposed action and name a measurable follow-up KPI.
7. Include a dedicated **حدود التحليل** section describing relevant data gaps, assumptions, missing weeks, repeated observations, statistical limitations, and outcomes not present in the source data.
8. Check every number and local link before delivery. Ensure charts support the claim in the text and that no recommendation is stronger than its evidence.

## Output checklist

- Every reported number has a precise notebook section and code-cell citation.
- At least three evidence-linked recommendations include follow-up measures.
- The limitations section is explicit and specific to this dataset.
- No unsupported causal claims or unverified figures.
