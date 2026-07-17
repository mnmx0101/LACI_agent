# Runbook 03: Calibrate

## Purpose

Translate an assessed model output into bounded analyst-facing interpretation for a defined use case.

## Role-Aware Entry

- **IPC-LACI Team:** May prepare checklist inputs after ingesting an operational note.
- **IPC-GSU:** Reviews IPC process fit, calibration logic, and context-specific limitation matching.
- **IPC Analyst:** Uses the calibrated guidance to support final case-specific decision-making.

## Inputs

- Assess Card.
- Latest operational note.
- Use case definition.
- Current context notes.

## Steps

1. **Confirm role and goal:** Use `ROLE_ROUTER.md` if unclear.
2. **Explain input needs:** Operational note is required for current model-run interpretation; use case definition is required before final checklist work; current context notes are required for limitation matching.
3. **Confirm use case:** Stop if `intake_forms/use_case_definition.md` is missing or incomplete.
4. **Confirm operational note:** Check model version, run date, data cut-off, source lag, spatial unit, temporal unit, and output labels.
5. **Match limitations:** Compare current conditions against known model limitations.
6. **Interpret performance:** State what the best relevant performance value implies for this use case.
7. **Translate thresholds/scores:** Explain what thresholds, probabilities, alerts, scores, or anomalies mean for IPC-facing interpretation.
8. **Define bounded guidance:** State what analysts may consider, what they must cross-check, and what they should not infer.

## Expected Output

- Calibration-ready checklist inputs or draft Use Checklist.

## QA Check

Apply `quality_gates/use_checklist_qc.md` before issuing a final verdict.

