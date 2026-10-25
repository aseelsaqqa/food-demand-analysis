# Ready skills and custom skill tests

## Ready skills found

The project should not duplicate the course skills for `weekly-demand-exploration` (weekly/category/meal/center demand patterns) and `promotion-effect-analysis` (promotion comparisons using Mann–Whitney or discount association with Spearman).

Public GitHub search also found a general `pandas` skill at [kandada/aacode](https://github.com/kandada/aacode/tree/8284c7ede75e98e50c6267484cdc62eec45b6dbd/skills/pandas), which depends on an unavailable `run_skills` execution environment, and a financial `client-report` skill at [anthropics/financial-services](https://github.com/anthropics/financial-services/tree/574ed3624aebd041f2c96cd101262f30210ab26/plugins/agent-plugins/meeting-prep-agent/skills/client-report), which is not suitable for food-demand reporting. Their contents were not copied.

## Two custom skills

1. `demand-metrics-calculation`: calculate and validate operational demand metrics.
2. `client-report-writing`: draft notebook-grounded client reports with cautious claims and explicit limitations.

## Invocation test prompts

| Skill | Relevant prompt expected to invoke it | Unrelated prompt expected not to invoke it |
|---|---|---|
| `demand-metrics-calculation` | Calculate weekly mean orders, estimated revenue, discount rate, and variability per meal and center; show definitions and audit counts. | Write a brief apology for a delayed meeting. |
| `client-report-writing` | Draft the Arabic client report from the executed notebook, cite each figure's source cell, include three recommendations and limitations. | Sort a household grocery list into a table. |

In VS Code Copilot Chat, run each relevant and unrelated prompt in separate chats and record whether the matching skill was loaded. Keep `data/raw/` read-only and do not claim causality from observational tests.
