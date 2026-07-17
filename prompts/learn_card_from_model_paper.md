# Prompt: Learn Card From Model Paper

```text
Read README.md, ENTRY.md, CORTEX.md, templates/LACI_Learn_Card_Template.md, runbooks/01_learn_runbook.md, and quality_gates/learn_card_qc.md.

Task: Draft a LACI Learn Card from the provided model paper or technical documentation.

Inputs:
- Model paper/documentation: [file or citation]
- Any operational notes: [file or none]
- Any known IPC-facing use interest: [brief note]

Requirements:
- Use bullets with bold keywords where possible.
- Record model output definition, target, spatial unit, temporal unit, prediction horizon, update frequency, input data, training labels, validation design, performance metrics, and known limitations.
- Mark unknowns explicitly.
- Do not finalize technical facts that require model-builder verification.

Output:
- Save draft to outputs/learn_cards/[model_name]_learn_card_draft.md.
- End with missing information and model-builder verification requests.
```
