# Using LACI_assistant With Codex

This guide is for users who clone the repository and want to work with Codex in a local coding workspace.

## 1. Open The Repo

- Clone the repository.
- Open the repo folder in Codex.
- Read:
  - `README.md`
  - `LACI_assistant/README.md`
  - `AGENTS.md`

## 2. Tell Codex Which Workflow To Run

Use one of these entry points:

- `LACI_assistant/workflows/02_Model_Paper_To_Learn_Card.md`
- `LACI_assistant/workflows/03_Model_Paper_To_Assess_Card.md`
- `LACI_assistant/workflows/04_Operational_Note_To_Use_Checklist.md`
- `LACI_assistant/workflows/05_Context_Specific_Limitation_Match.md`
- `LACI_assistant/workflows/06_Final_Decision_Guide.md`

## 3. Starter Prompts

### Model Paper To Learn Card

```text
Use LACI_assistant to draft a Learn Card from the model paper I provide.
Follow LACI_assistant/templates/LACI_Learn_Card_Template.md.
Record unknowns and verification needs.
Do not add private paths or unsupported claims.
```

### Learn Card To Assess Card

```text
Use LACI_assistant to draft or revise an Assess Card.
Follow LACI_assistant/templates/LACI_Assess_Card_Template.md.
Preserve all screening questions.
Document performance metrics, context-specific limitations, spatial/temporal fit, and IPC-facing guardrails.
```

### Assess Card To Use Checklist

```text
Use LACI_assistant to draft an IPC Analysis Use Checklist.
First check whether I provided a use case definition and latest operational note.
If missing, create a preliminary checklist status and list the missing fields.
Use LACI_assistant/templates/LACI_IPC_Analysis_Use_Checklist_Template.md.
```

## 4. Suggested File Locations

If the user asks Codex to save outputs, use a clear local folder such as:

- `outputs/learn_cards/`
- `outputs/assess_cards/`
- `outputs/use_checklists/`
- `outputs/reviews/`
- `outputs/knowledge_updates/`

Create these folders only when needed.

## 5. Codex Behavior Expectations

- Use existing templates and role cards.
- Keep changes scoped.
- Use relative repo links.
- Do not commit private sources or internal local folders.
- Ask before changing template governance or removing screening questions.

## 6. Final Verdict Rule

For any final verdict, include:

- **Decision badge / label**
- **Reasoning from checklist**
- **Allowed actions**
- **Not allowed actions**
- **Owner of final judgment**

The IPC Analyst owns the case-specific final verdict, supported by IPC-GSU and IPC-LACI Team as needed.
