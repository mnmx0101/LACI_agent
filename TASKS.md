# LACI_agent Tasks

Use these task patterns when asking an AI assistant to work in this repo.

## Common Tasks

| Task | Required inputs | Main route | Expected output |
| :--- | :--- | :--- | :--- |
| Draft Learn Card | Model paper or technical documentation | [runbooks/01_learn_runbook.md](runbooks/01_learn_runbook.md) | Learn Card draft in `outputs/learn_cards/` |
| Draft Assess Card | Learn Card, model paper, source evidence | [runbooks/02_assess_runbook.md](runbooks/02_assess_runbook.md) | Assess Card draft in `outputs/assess_cards/` |
| Draft Use Checklist | Assess Card, latest operational note, use case definition | [runbooks/03_calibrate_runbook.md](runbooks/03_calibrate_runbook.md) and [runbooks/04_integrate_runbook.md](runbooks/04_integrate_runbook.md) | IPC Analysis Use Checklist in `outputs/use_checklists/` |
| Red-team a card | Existing Learn Card, Assess Card, or checklist | [skills/LACI_Red_Team_Reviewer.md](skills/LACI_Red_Team_Reviewer.md) | Review note in `outputs/reviews/` |
| Convert raw input to wiki update | Meeting note, memo, comment, or source note | [skills/LACI_Input_Triage.md](skills/LACI_Input_Triage.md) | Proposed knowledge update in `outputs/knowledge_updates/` |
| Public release check | Files proposed for commit/share | [_system/PUBLIC-SAFETY-CHECKLIST.md](_system/PUBLIC-SAFETY-CHECKLIST.md) | Release-ready or blocked status |

## Example Prompt Pattern

```text
Read README.md, ENTRY.md, CORTEX.md, and TASKS.md.
Task: Draft an Assess Card.
Inputs: [list files or paste public-safe excerpts].
Use: templates/LACI_Assess_Card_Template.md and runbooks/02_assess_runbook.md.
Apply: quality_gates/assess_card_qc.md.
Output: outputs/assess_cards/[model_name]_assess_card_draft.md.
Do not finalize technical claims that require model-builder verification.
```

## Stop Conditions

- **Use case is undefined:** A final Use Checklist cannot be completed without a use case definition.
- **Operational note is missing/stale:** Checklist verdict must be preliminary or reassessment must be recommended.
- **Technical claim is unsupported:** Mark as unverified and request model-builder/data-provider confirmation.
- **Public safety risk appears:** Do not commit or quote confidential/restricted material.
