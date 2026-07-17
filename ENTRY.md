# LACI_agent Entry

Use this page when you first open the repo or when you need to decide what to ask an AI assistant to do.

## Start With Role And Goal

Before routing to a template or form, identify the user role and goal. Use [ROLE_ROUTER.md](ROLE_ROUTER.md) if either is unclear.

| Role | Common goals | First entry point |
| :--- | :--- | :--- |
| **IPC-LACI Team** | Start review from model paper; update Learn/Assess Cards; ingest operational note for checklist preparation | Model paper or public technical documentation |
| **Model Builder / Data Provider** | Draft, verify, or update cards; provide operational note; clarify performance, limitations, and implementation details | Model paper, existing draft card, technical documentation, or operational note |
| **IPC-GSU** | Review IPC fit, process alignment, calibration, and knowledge-base implications | Assess Card, operational note, IPC context |
| **IPC Analyst** | Complete Use Checklist and final case-specific verdict | Use case definition, latest operational note, Assess Card |
| **Skill Reviewer** | Red-team, evidence audit, harmonize, triage, or ledger update | Existing artifact or raw input |

## Choose Your Starting Point

| Your situation | Start with | Then use |
| :--- | :--- | :--- |
| You are IPC-LACI Team starting from scratch | Model paper or public technical documentation | [prompts/learn_card_from_model_paper.md](prompts/learn_card_from_model_paper.md) and [runbooks/01_learn_runbook.md](runbooks/01_learn_runbook.md); LACI_agent can prefill [model paper intake](intake_forms/model_paper_intake.md) |
| You are Model Builder / Data Provider drafting or verifying | Model paper, existing card, technical documentation, or operational note | [skills/LACI_Model_Builder_Reviewer.md](skills/LACI_Model_Builder_Reviewer.md) plus the relevant Learn/Assess prompt |
| You have a Learn Card and need assessment | [templates/LACI_Assess_Card_Template.md](templates/LACI_Assess_Card_Template.md) | [prompts/assess_card_from_learn_card.md](prompts/assess_card_from_learn_card.md) and [runbooks/02_assess_runbook.md](runbooks/02_assess_runbook.md) |
| You need a case-specific analyst checklist | [intake_forms/use_case_definition.md](intake_forms/use_case_definition.md) and latest operational note | [prompts/use_checklist_from_operational_note.md](prompts/use_checklist_from_operational_note.md), [runbooks/03_calibrate_runbook.md](runbooks/03_calibrate_runbook.md), and [runbooks/04_integrate_runbook.md](runbooks/04_integrate_runbook.md) |
| You have raw notes, comments, or meeting input | [raw/README.md](raw/README.md) | [prompts/knowledge_update_from_raw_input.md](prompts/knowledge_update_from_raw_input.md) |
| You need a skeptical review | Current card or checklist draft | [prompts/red_team_assess_card.md](prompts/red_team_assess_card.md) and [skills/LACI_Red_Team_Reviewer.md](skills/LACI_Red_Team_Reviewer.md) |

## Before You Ask The Agent

You do not need to manually complete every intake form before starting. For Learn and Assess work, the assistant should prefill intake fields from the model paper and mark gaps for IPC-LACI Team or model-builder verification. For final Use Checklist work, the use case definition and latest operational note are required.

- **Confirm public safety:** Do not paste confidential IPC analysis, restricted partner material, or unpublished operational data into a public issue or commit.
- **State role and goal:** Identify whether you are using the tool as IPC-LACI Team, Model Builder / Data Provider, IPC-GSU, IPC Analyst, or Skill Reviewer.
- **Provide stage-specific inputs:** Give the inputs needed for the current stage; do not collect later-stage materials without explaining why they are needed.
- **State the output folder:** Draft outputs should go under `outputs/` locally unless your team decides to share them.

## Why The Agent May Ask For Additional Inputs

- **Model paper:** Needed now for IPC-LACI Team or Model Builder / Data Provider starting Learn/Assess from scratch.
- **Operational note:** Needed later for current operational assessment, model-run updates, calibration, and Use Checklist work.
- **Use case definition:** Needed for Calibrate/Integrate and required before final checklist verdict.
- **Current context notes:** Needed for context-specific limitation matching and final analyst guidance.

## Minimum Inputs For Final Checklist Work

A final IPC Analysis Use Checklist requires:

- **Use case definition:** IPC application, working analytical function, geography, time window, intended analyst action, and decision owner.
- **Latest operational note:** Model version/run date, data cut-off, source lags, spatial/temporal units, and any changed implementation details.
- **Current context:** Known conflict, epidemic, drought, access, cloud cover, displacement, data interruption, or other conditions that may trigger model limitations.
- **Relevant cards:** Learn Card and Assess Card, preferably verified by the model builder or data provider.

