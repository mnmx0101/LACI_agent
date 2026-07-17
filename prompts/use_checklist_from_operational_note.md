# Prompt: Use Checklist From Operational Note

```text
Read README.md, ROLE_ROUTER.md, ENTRY.md, CORTEX.md, templates/LACI_IPC_Analysis_Use_Checklist_Template.md, runbooks/03_calibrate_runbook.md, runbooks/04_integrate_runbook.md, and quality_gates/use_checklist_qc.md.

Role: [IPC Analyst / IPC-GSU / IPC-LACI Team / other]
Goal: Complete or prepare an IPC Analysis Use Checklist for a defined use case.

Required inputs for final checklist work:
- Use case definition: [file]
- Latest operational note: [file]
- Learn Card: [file]
- Assess Card: [file]
- Current context notes: [file or summary]

Explain why these are required before asking for them: the use case defines the IPC application, geography, time window, intended analyst action, and decision owner; the operational note confirms the latest model run/version, data cut-off, lags, output labels, and spatial/temporal units; current context notes allow limitation matching.

Requirements:
- Use a bullet-first structure with **bold keyword labels**. Do not bury pending items, unknowns, or verification needs in paragraphs.
- Include or preserve a **Key Status / Verification Flags** block near the top when drafting cards/checklists.
- Each major section should make verification status, pending items, or unknowns clear.
- If use case definition is missing, stop and request it.
- If latest operational note is missing or stale, mark the checklist preliminary and recommend reassessment.
- Compare current conditions against known model limitations.
- Include performance value, metric, and implication for this use case where available.
- Provide a radically simplified final verdict with bullet-point reasoning, allowed actions, not-allowed actions, and reassessment triggers.
- IPC Analyst or authorized IPC process owner owns the final case-specific verdict.

Output:
- Save checklist to outputs/use_checklists/[model_name]_[use_case]_checklist.md.
```

