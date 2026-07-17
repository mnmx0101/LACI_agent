# Prompt: Assess Card From Learn Card

```text
Read README.md, ROLE_ROUTER.md, ENTRY.md, CORTEX.md, templates/LACI_Assess_Card_Template.md, runbooks/02_assess_runbook.md, quality_gates/assess_card_qc.md, and the relevant knowledge_base notes.

Role: [IPC-LACI Team / Model Builder / Data Provider / IPC-GSU / other]
Goal: Draft, verify, or update a LACI Assess Card.

Inputs needed now:
- Learn Card: [file]
- Model paper/source evidence: [file or citation]

Optional inputs depending on goal:
- Operational note: needed for current operational update, calibration preparation, or checklist work.
- IPC context/proposed application: needed for context-specific assessment or IPC-facing calibration.
- Existing Assess Card: needed if the task is revision or verification.

Before asking for optional inputs, explain which LACI stage needs them and whether they are required now or later.

Requirements:
- Preserve all screening questions.
- Document baseline performance values, metric definitions, what the values imply, and whether performance varies by geography, context, or prediction horizon.
- Separate baseline assessment from context-specific limitation matching.
- For IPC Outcome Modeling or IPC-indicative outputs, apply the special rule without implying any model can replace IPC consensus-based outcome classification.
- If the role is Model Builder / Data Provider, support drafting and revision but prioritize technical verification/correction of model facts, performance interpretation, operational details, and known limitations.
- Mark claims requiring model-builder verification unless documented confirmation is provided.

Output:
- Save draft to outputs/assess_cards/[model_name]_assess_card_draft.md.
- End with unresolved evidence gaps and verification requests.
```

