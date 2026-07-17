# Runbook 01: Learn

## Purpose

Convert model documentation into a structured Learn Card.

## Inputs

- Model paper or technical documentation.
- Any operational note or implementation description.
- `intake_forms/model_paper_intake.md` if available.

## Steps

1. **Identify output:** Record what the model generates and what it does not generate.
2. **Record metadata:** Capture geography, spatial unit, time unit, prediction horizon, update frequency, and output labels.
3. **Document training and validation:** Record labels, reference data, validation design, and reported metrics.
4. **Capture limitations:** Extract known failure modes, context gaps, and operational caveats.
5. **Mark unknowns:** List missing information and verification requests.

## Expected Output

- Learn Card draft in `outputs/learn_cards/`.

## QA Check

Apply `quality_gates/learn_card_qc.md` before treating the card as ready for assessment.
