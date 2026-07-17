# Prompt: Assess Card From Learn Card

```text
Read README.md, ENTRY.md, CORTEX.md, templates/LACI_Assess_Card_Template.md, runbooks/02_assess_runbook.md, quality_gates/assess_card_qc.md, and the relevant knowledge_base notes.

Task: Draft a LACI Assess Card from the Learn Card and source evidence.

Inputs:
- Learn Card: [file]
- Model paper/source evidence: [file or citation]
- Operational note if available: [file or none]
- IPC context or proposed application if known: [brief note]

Requirements:
- Preserve all screening questions.
- Document baseline performance values, metric definitions, what the values imply, and whether performance varies by geography, context, or prediction horizon.
- Separate baseline assessment from context-specific limitation matching.
- For IPC Outcome Modeling or IPC-indicative outputs, apply the special rule without implying any model can replace IPC consensus-based outcome classification.
- Mark claims requiring model-builder verification.

Output:
- Save draft to outputs/assess_cards/[model_name]_assess_card_draft.md.
- End with unresolved evidence gaps and verification requests.
```
