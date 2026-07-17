# Runbook 02: Assess

## Purpose

Evaluate whether a model-generated output is credible, documented, IPC-relevant, and bounded enough to inform later use-case decisions.

## Inputs

- Learn Card.
- Model paper/source evidence.
- Operational note if available.
- Proposed IPC application if known.

## Steps

1. **Run baseline screening:** Preserve all screening questions in the Assess Card template.
2. **Record performance:** Include metric values, metric meaning, justification for metric choice, and performance variation by geography/context/horizon when available.
3. **Assess limitations:** Record known model failure modes and assumptions.
4. **Apply IPC special rule:** For IPC Outcome Modeling and IPC-indicative outputs, examine spatial/temporal alignment, threshold meaning, and population-share implications without treating the model as a replacement for IPC classification.
5. **Prepare context-specific hooks:** Identify limitations that must be checked again during a concrete use case.
6. **List verification needs:** Separate public-source inference from model-builder or data-provider confirmation.

## Expected Output

- Assess Card draft in `outputs/assess_cards/`.

## QA Check

Apply `quality_gates/assess_card_qc.md` and consider a red-team review before finalizing.
