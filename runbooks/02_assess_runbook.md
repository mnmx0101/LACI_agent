# Runbook 02: Assess

## Purpose

Evaluate whether a model-generated output is credible, documented, IPC-relevant, and bounded enough to inform later use-case decisions.

## Role-Aware Entry

- **IPC-LACI Team:** Draft baseline Assess Card from Learn Card and source evidence, then identify verification needs.
- **Model Builder / Data Provider:** May draft, verify, or update Assess Card content, with special authority over documented model facts, operational details, performance interpretation, and limitations.
- **IPC-GSU:** Reviews IPC-facing fit, calibration logic, threshold meaning, and process implications.

## Inputs

- Learn Card.
- Model paper/source evidence.
- Operational note if the goal is current operational update, calibration preparation, or checklist work.
- Proposed IPC application/context if context-specific assessment is requested.

## Steps

1. **Confirm role and goal:** Use `ROLE_ROUTER.md` if unclear.
2. **Explain input needs:** Learn Card and source evidence are needed for baseline assessment; operational notes and use-case details are needed later for current-use or checklist guidance.
3. **Run baseline screening:** Preserve all screening questions in the Assess Card template.
4. **Record performance:** Include metric values, metric meaning, justification for metric choice, and performance variation by geography/context/horizon when available.
5. **Assess limitations:** Record known model failure modes and assumptions.
6. **Apply IPC special rule:** For IPC Outcome Modeling and IPC-indicative outputs, examine spatial/temporal alignment, threshold meaning, and population-share implications without treating the model as a replacement for IPC classification.
7. **Prepare context-specific hooks:** Identify limitations that must be checked again during a concrete use case.
8. **List verification needs:** Separate public-source inference from model-builder or data-provider confirmation.

## Expected Output

- Assess Card draft in `outputs/assess_cards/`.

## QA Check

Apply `quality_gates/assess_card_qc.md` and consider a red-team review before finalizing.

