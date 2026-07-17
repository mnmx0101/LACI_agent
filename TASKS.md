# LACI_agent Tasks

Use these task patterns when asking an AI assistant to work in this repo. First orient the user to LACI and the current Learn/Assess focus, then identify the user role and goal with [ROLE_ROUTER.md](ROLE_ROUTER.md). If the user wants to browse first, use [NAVIGATE.md](NAVIGATE.md).

## Common Tasks

| Task | Required inputs | Main route | Expected output |
| :--- | :--- | :--- | :--- |
| Orient user | No input required | [ROLE_ROUTER.md](ROLE_ROUTER.md) | Brief explanation of LACI, current Learn/Assess focus, role workflows, and non-replacement rule |
| Browse before starting | User interest area | [NAVIGATE.md](NAVIGATE.md) | Locate templates, knowledge base/wiki, core documents, or workflow guidance |
| Identify role and goal | User role and goal statement | [ROLE_ROUTER.md](ROLE_ROUTER.md) | Correct workflow route and stage-specific input request |
| Draft Learn Card | Model paper or technical documentation | [runbooks/01_learn_runbook.md](runbooks/01_learn_runbook.md) | Learn Card draft in `outputs/learn_cards/` |
| Draft Assess Card | Learn Card, model paper, source evidence | [runbooks/02_assess_runbook.md](runbooks/02_assess_runbook.md) | Assess Card draft in `outputs/assess_cards/` |
| Draft Use Checklist | Assess Card, latest operational note, use case definition | [runbooks/03_calibrate_runbook.md](runbooks/03_calibrate_runbook.md) and [runbooks/04_integrate_runbook.md](runbooks/04_integrate_runbook.md) | IPC Analysis Use Checklist in `outputs/use_checklists/` |
| Red-team a card | Existing Learn Card, Assess Card, or checklist | [skills/LACI_Red_Team_Reviewer.md](skills/LACI_Red_Team_Reviewer.md) | Review note in `outputs/reviews/` |
| Convert raw input to wiki update | Meeting note, memo, comment, or source note | [skills/LACI_Input_Triage.md](skills/LACI_Input_Triage.md) | Proposed knowledge update in `outputs/knowledge_updates/` |
| Public release check | Files proposed for commit/share | [_system/PUBLIC-SAFETY-CHECKLIST.md](_system/PUBLIC-SAFETY-CHECKLIST.md) | Release-ready or blocked status |

## Example Prompt Pattern

```text
Read README.md, ROLE_ROUTER.md, ENTRY.md, CORTEX.md, and TASKS.md.
Role: [IPC-LACI Team / Model Builder / Data Provider / IPC-GSU / IPC Analyst / Skill Reviewer].
Goal: [brief goal].
Task: Draft an Assess Card.
Inputs: [list files or paste public-safe excerpts].
Use: templates/LACI_Assess_Card_Template.md and runbooks/02_assess_runbook.md.
Apply: quality_gates/assess_card_qc.md.
Output: outputs/assess_cards/[model_name]_assess_card_draft.md.
Do not finalize technical claims that require model-builder verification.
```

## Before Asking For Files

Explain why each requested input is needed and whether it is required for the current stage or a later stage. Model papers start Learn/Assess; operational notes support current-use updates and checklist work; use case definitions are required before final Use Checklists.

## Stop Conditions

- **Role or goal is undefined:** Ask who is using LACI_agent and what they want to do before routing.
- **Use case is undefined:** A final Use Checklist cannot be completed without a use case definition.
- **Operational note is missing/stale:** Checklist verdict must be preliminary or reassessment must be recommended.
- **Technical claim is unsupported:** Mark as unverified and request model-builder/data-provider confirmation.
- **Public safety risk appears:** Do not commit or quote confidential/restricted material.

