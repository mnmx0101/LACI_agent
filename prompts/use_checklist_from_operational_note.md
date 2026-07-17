# Prompt: Use Checklist From Operational Note

```text
Read README.md, ENTRY.md, CORTEX.md, templates/LACI_IPC_Analysis_Use_Checklist_Template.md, runbooks/03_calibrate_runbook.md, runbooks/04_integrate_runbook.md, and quality_gates/use_checklist_qc.md.

Task: Complete an IPC Analysis Use Checklist for a defined use case.

Required inputs:
- Use case definition: [file]
- Latest operational note: [file]
- Learn Card: [file]
- Assess Card: [file]
- Current context notes: [file or summary]

Requirements:
- If use case definition is missing, stop and request it.
- If latest operational note is missing or stale, mark the checklist preliminary and recommend reassessment.
- Compare current conditions against known model limitations.
- Include performance value, metric, and implication for this use case where available.
- Provide a radically simplified final verdict with bullet-point reasoning, allowed actions, not-allowed actions, and reassessment triggers.

Output:
- Save checklist to outputs/use_checklists/[model_name]_[use_case]_checklist.md.
```
