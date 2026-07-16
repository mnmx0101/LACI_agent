# Codex Agent Instructions For LACI_agent

This repository contains the public-facing `LACI_agent` workspace for developing and testing LACI: Learn, Assess, Calibrate, and Integrate model-generated outputs for IPC-supporting workflows.

## Orientation

- Start with `README.md`.
- Main workspace: `README.md`.
- Workflows: `workflows/`.
- Templates: `templates/`.
- Skill role cards: `skills/`.
- Examples: `examples/`.

## Operating Rules

- Never state or imply that model output replaces IPC consensus classification.
- Learn and Assess Cards can be drafted by `LACI_agent` / `IPC-LACI Team`, but model builders or data providers verify technical facts before finalization.
- A Use Checklist requires a user-provided use case definition and the latest operational note.
- If either the use case or operational note is missing, mark the checklist preliminary and request the missing item.
- Preserve all Assess Card screening questions unless the user explicitly changes the template governance.
- Keep `IPC-GSU` responsible for IPC-facing knowledge/process alignment and `IPC Analyst` responsible for case-specific final verdicts.

## When Asked To Draft

- Use the relevant template rather than inventing a new structure.
- Save outputs under an appropriate folder if the user asks for files.
- Use examples only as demonstrations, not as binding decisions.
- For final verdicts, use the visual badge labels from `decision_support/Final_Verdict_Guide.md`.

## Suggested Routing

- **Model paper only:** use `workflows/02_Model_Paper_To_Learn_Card.md`.
- **Learn Card exists:** use `workflows/03_Model_Paper_To_Assess_Card.md`.
- **Operational note + use case:** use `workflows/04_Operational_Note_To_Use_Checklist.md`.
- **Known limitation matching:** use `workflows/05_Context_Specific_Limitation_Match.md`.
- **Final verdict:** use `workflows/06_Final_Decision_Guide.md`.

## Public-Repo Safety

- Do not commit private IPC manuals, confidential data, local absolute paths, or unpublished partner material.
- Keep public outputs free of internal/private workspace paths and local machine references.
- Use relative links within the repo.


