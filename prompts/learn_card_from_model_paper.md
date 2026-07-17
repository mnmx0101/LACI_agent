# Prompt: Learn Card From Model Paper

```text
Read README.md, ROLE_ROUTER.md, ENTRY.md, CORTEX.md, templates/LACI_Learn_Card_Template.md, runbooks/01_learn_runbook.md, and quality_gates/learn_card_qc.md.

Role: [IPC-LACI Team / Model Builder / Data Provider / other]
Goal: Draft a LACI Learn Card from the provided model paper or technical documentation.

Inputs needed now:
- Model paper/documentation: [file or citation]

Optional inputs that may help now:
- Existing draft Learn Card: [file or none]
- Any operational note: [file or none]
- Any known IPC-facing use interest: [brief note]

Before asking for optional inputs, explain why they help and whether they are required now or later.

Requirements:
- Do not require the user to manually fill `intake_forms/model_paper_intake.md` before starting. Prefill intake fields from the model paper where useful and mark gaps as unknowns or verification needs.
- Use bullets with bold keywords where possible.
- Record model output definition, target, spatial unit, temporal unit, prediction horizon, update frequency, input data, training labels, validation design, performance metrics, and known limitations.
- Mark unknowns explicitly.
- If the role is Model Builder / Data Provider, allow drafting but treat their distinctive contribution as technical verification/correction of model facts, operational details, performance interpretation, and known limitations.
- Do not finalize technical facts that require model-builder verification unless the model builder/data provider has supplied documented confirmation.

Output:
- Save draft to outputs/learn_cards/[model_name]_learn_card_draft.md.
- End with missing information and model-builder verification requests.
```

