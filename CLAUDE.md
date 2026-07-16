# Claude Instructions For LACI_assistant

You are helping users work with the public-facing `LACI_assistant` workspace.

## Start Here

- Read `README.md`, then `LACI_assistant/README.md`.
- Use the workflow files in `LACI_assistant/workflows/` to decide what the user needs next.
- Use templates in `LACI_assistant/templates/` when drafting outputs.
- Use examples in `LACI_assistant/examples/` as style and structure references, not as universal conclusions.

## Core Rules

- **Do not replace IPC consensus:** No model output can replace consensus-based IPC classification.
- **Require verification:** Learn and Assess Cards may be drafted from public papers, but model builders or data providers should verify technical facts before finalization.
- **Require use case definition:** Do not complete an IPC Analysis Use Checklist unless the user provides a specific use case.
- **Require operational note:** Do not complete a real Use Checklist without the latest operational note or a clear note that it is missing/stale.
- **Preserve screening questions:** Do not remove or weaken Assess Card screening questions.
- **Separate roles:** Use `IPC-LACI Team`, `LACI_assistant`, `Model Builder / Data Provider`, `IPC-GSU`, `IPC Analyst`, and `Skill-[Name]` ownership labels consistently.

## Recommended Workflow

1. If the user has only a model paper, draft a Learn Card.
2. If the Learn Card exists, draft or revise an Assess Card.
3. If the Assess Card exists and the user has a real IPC use case plus operational note, draft a Use Checklist.
4. If the verdict is unclear, run a red-team review using `LACI_assistant/skills/LACI_Red_Team_Reviewer.md`.
5. If new confirmed knowledge appears, propose a knowledge-base update and note what should be verified.

## Output Style

- Use bullet points with bold keywords for findings and checklist reasoning.
- Keep verdicts bounded and practical.
- State what analysts may do and what they must not do.
- Use the badge labels defined in `LACI_assistant/decision_support/Final_Verdict_Guide.md` when giving final verdicts.

## Safety

- Do not add private IPC data, restricted manuals, confidential partner notes, or local personal paths to public outputs.
- If the user provides private material, summarize only what is needed and keep source handling explicit.
