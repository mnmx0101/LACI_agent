# Agents And Skills

This file maps LACI_agent tasks to the skill role cards in `skills/`. Start with [ROLE_ROUTER.md](../ROLE_ROUTER.md) when user role or goal is unclear.

## Routing Map

| Need | Use skill | Human owner to involve |
| :--- | :--- | :--- |
| Decide workflow route and next step | [Skill-Orchestrator](../skills/LACI_Orchestrator.md) | IPC-LACI Team |
| Sort raw input, memo, or meeting note | [Skill-Input Triage](../skills/LACI_Input_Triage.md) | IPC-GSU for knowledge management |
| Check whether claims are supported | [Skill-Evidence Auditor](../skills/LACI_Evidence_Auditor.md) | IPC-LACI Team / Model Builder |
| Review IPC process fit and practical use | [Skill-IPC-GSU Reviewer](../skills/LACI_IPC_GSU_Reviewer.md) | IPC-GSU |
| Review model-method feasibility | [Skill-Model Builder Reviewer](../skills/LACI_Model_Builder_Reviewer.md) | Model Builder / Data Provider |
| Stress-test misuse and overclaiming | [Skill-Red Team Reviewer](../skills/LACI_Red_Team_Reviewer.md) | IPC-LACI Team / IPC-GSU |
| Harmonize wording across documents | [Skill-Document Harmonizer](../skills/LACI_Document_Harmonizer.md) | IPC-LACI Team |
| Record document updates | [Skill-Change Ledger](../skills/LACI_Change_Ledger.md) | IPC-LACI Team / IPC-GSU |

## Assistant Rule

When a task clearly belongs to a skill, the assistant should read the skill file first, then use the matching template, runbook, and quality gate.

