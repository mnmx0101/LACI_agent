# Runbook 04: Integrate

## Purpose

Support a final, case-specific IPC analyst verdict on whether and how a model output may be considered for a defined IPC-supporting workflow.

## Inputs

- Completed Use Checklist.
- Use case definition.
- Latest operational note.
- Current context-specific limitation match.

## Steps

1. **Review gates:** Confirm required inputs, spatial/temporal fit, performance relevance, and limitation match.
2. **Choose verdict:** Use the LACI final verdict system from `README.md` and `decision_support/Final_Verdict_Guide.md`.
3. **Write reasoning:** Provide bullet-point reasoning tied to checklist findings.
4. **Define actions:** State allowed actions, not-allowed actions, cross-check requirements, and reassessment triggers.
5. **Record decision:** Save final checklist or decision-support note in `outputs/use_checklists/`.
6. **Update learning loop:** Propose knowledge-base or template updates if new limitations or workflow lessons were identified.

## Expected Output

- IPC Analysis Use Checklist with simplified final verdict.

## QA Check

Apply `quality_gates/use_checklist_qc.md` and `_system/PUBLIC-SAFETY-CHECKLIST.md` before sharing.
