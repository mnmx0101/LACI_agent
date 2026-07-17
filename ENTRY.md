# LACI_agent Entry

Use this page when you first open the repo or when you need to decide what to ask an AI assistant to do.

## Choose Your Starting Point

| Your situation | Start with | Then use |
| :--- | :--- | :--- |
| You have a model paper or technical report | [intake_forms/model_paper_intake.md](intake_forms/model_paper_intake.md) | [prompts/learn_card_from_model_paper.md](prompts/learn_card_from_model_paper.md) and [runbooks/01_learn_runbook.md](runbooks/01_learn_runbook.md) |
| You have a Learn Card and need assessment | [templates/LACI_Assess_Card_Template.md](templates/LACI_Assess_Card_Template.md) | [prompts/assess_card_from_learn_card.md](prompts/assess_card_from_learn_card.md) and [runbooks/02_assess_runbook.md](runbooks/02_assess_runbook.md) |
| You need a case-specific analyst checklist | [intake_forms/use_case_definition.md](intake_forms/use_case_definition.md) | [prompts/use_checklist_from_operational_note.md](prompts/use_checklist_from_operational_note.md) and [runbooks/03_calibrate_runbook.md](runbooks/03_calibrate_runbook.md) |
| You have raw notes, comments, or meeting input | [raw/README.md](raw/README.md) | [prompts/knowledge_update_from_raw_input.md](prompts/knowledge_update_from_raw_input.md) |
| You need a skeptical review | Current card or checklist draft | [prompts/red_team_assess_card.md](prompts/red_team_assess_card.md) and [skills/LACI_Red_Team_Reviewer.md](skills/LACI_Red_Team_Reviewer.md) |

## Before You Ask The Agent

- **Confirm public safety:** Do not paste confidential IPC analysis, restricted partner material, or unpublished operational data into a public issue or commit.
- **Define the task:** Name the LACI stage: Learn, Assess, Calibrate, or Integrate.
- **Provide minimum inputs:** Model paper, Learn Card, Assess Card, operational note, and use case definition as relevant.
- **State the output folder:** Draft outputs should go under `outputs/` locally unless your team decides to share them.

## Minimum Inputs For Final Checklist Work

A final IPC Analysis Use Checklist requires:

- **Use case definition:** IPC application, working analytical function, geography, time window, intended analyst action, and decision owner.
- **Latest operational note:** Model version/run date, data cut-off, source lags, spatial/temporal units, and any changed implementation details.
- **Current context:** Known conflict, epidemic, drought, access, cloud cover, displacement, data interruption, or other conditions that may trigger model limitations.
- **Relevant cards:** Learn Card and Assess Card, preferably verified by the model builder or data provider.
