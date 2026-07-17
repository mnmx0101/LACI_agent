# Runbook 03: Calibrate

## Purpose

Translate an assessed model output into bounded analyst-facing interpretation for a defined use case.

## Inputs

- Assess Card.
- Latest operational note.
- Use case definition.
- Current context notes.

## Steps

1. **Confirm use case:** Stop if `intake_forms/use_case_definition.md` is missing or incomplete.
2. **Confirm operational note:** Check model version, run date, data cut-off, source lag, spatial unit, temporal unit, and output labels.
3. **Match limitations:** Compare current conditions against known model limitations.
4. **Interpret performance:** State what the best relevant performance value implies for this use case.
5. **Translate thresholds/scores:** Explain what thresholds, probabilities, alerts, scores, or anomalies mean for IPC-facing interpretation.
6. **Define bounded guidance:** State what analysts may consider, what they must cross-check, and what they should not infer.

## Expected Output

- Calibration-ready checklist inputs or draft Use Checklist.

## QA Check

Apply `quality_gates/use_checklist_qc.md` before issuing a final verdict.
