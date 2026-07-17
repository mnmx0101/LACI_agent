# Runbook 01: Learn

## Purpose

Convert model documentation into a structured Learn Card.

## Role-Aware Entry

- **IPC-LACI Team:** Start from a model paper or public technical documentation. LACI_agent should prefill model-paper intake and draft the Learn Card.
- **Model Builder / Data Provider:** May draft a Learn Card directly, verify an existing draft, or correct model facts. Their distinctive role is technical verification of model facts, performance, limitations, and operational details.

## Inputs

- Model paper or technical documentation.
- `intake_forms/model_paper_intake.md` if already completed; otherwise LACI_agent may prefill it from the model paper and mark gaps.
- Operational note or implementation description if the goal includes current operational details. This is helpful but not required to start baseline Learn work.

## Steps

1. **Confirm role and goal:** Use `ROLE_ROUTER.md` if unclear.
2. **Explain input needs:** Model paper is required now for from-scratch Learn work; operational notes are only required later for current-use updates/checklists.
3. **Prefill intake if useful:** Extract available model-paper intake fields from the source; do not require the user to fill the form manually before drafting.
4. **Identify output:** Record what the model generates and what it does not generate.
5. **Record metadata:** Capture geography, spatial unit, time unit, prediction horizon, update frequency, and output labels.
6. **Document training and validation:** Record labels, reference data, validation design, and reported metrics.
7. **Capture limitations:** Extract known failure modes, context gaps, and operational caveats.
8. **Mark unknowns:** List missing information and verification requests.

## Expected Output

- Learn Card draft in `outputs/learn_cards/`.

## QA Check

Apply `quality_gates/learn_card_qc.md` before treating the card as ready for assessment.

