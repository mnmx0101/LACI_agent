# Using LACI_assistant With Claude

This guide is for users who clone the repository and want to work with Claude or Claude Code.

## 1. Open The Repo

- Clone the repository.
- Open the repo folder in Claude Code or attach the relevant files to Claude.
- Start by reading:
  - `README.md`
  - `LACI_assistant/README.md`
  - `CLAUDE.md`

## 2. Choose Your Starting Point

- **I have a model paper:** ask Claude to use `LACI_assistant/workflows/02_Model_Paper_To_Learn_Card.md`.
- **I have a Learn Card:** ask Claude to use `LACI_assistant/workflows/03_Model_Paper_To_Assess_Card.md`.
- **I have a specific IPC use case and operational note:** ask Claude to use `LACI_assistant/workflows/04_Operational_Note_To_Use_Checklist.md`.
- **I need a skeptical review:** ask Claude to use `LACI_assistant/skills/LACI_Red_Team_Reviewer.md`.

## 3. Copy-Paste Starter Prompts

### Draft A Learn Card

```text
Use the LACI_assistant workflow to draft a Learn Card from this model paper.
Follow LACI_assistant/templates/LACI_Learn_Card_Template.md.
Do not invent missing technical facts. Mark unknowns clearly.
Identify what the model builder or data provider must verify.
```

### Draft An Assess Card

```text
Use the LACI_assistant workflow to draft an Assess Card from the existing Learn Card and source evidence.
Follow LACI_assistant/templates/LACI_Assess_Card_Template.md.
Preserve all screening questions.
Separate baseline model-output assessment from context-specific assessment.
Do not imply the model can replace IPC consensus classification.
```

### Draft A Use Checklist

```text
Use the LACI_assistant workflow to draft an IPC Analysis Use Checklist.
Before drafting, confirm that I provided:
1. a specific use case definition
2. the latest operational note
If either is missing, mark the checklist preliminary and ask for the missing item.
Use LACI_assistant/templates/LACI_IPC_Analysis_Use_Checklist_Template.md.
```

## 4. Expected Outputs

- Learn Card: model understanding and metadata.
- Assess Card: baseline and context-specific suitability assessment.
- Use Checklist: case-specific limitation match and final verdict.
- Red Team Review: risks, weak logic, overclaims, and required fixes.

## 5. Safety Reminder

Do not upload private IPC data, restricted manuals, unpublished analysis, confidential partner material, or local personal file paths into public repo outputs.
