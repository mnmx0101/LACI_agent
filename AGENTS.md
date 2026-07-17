# Codex Agent Instructions For LACI_agent

This repository contains the public, Cortex-style `LACI_agent` workspace for developing and testing LACI: Learn, Assess, Calibrate, and Integrate model-generated outputs for IPC-supporting workflows.

## Orientation

Read these first:

1. `README.md` for the public front door.
2. `ROLE_ROUTER.md` for identifying user role and goal.
3. `ENTRY.md` for choosing the task path after role and goal are clear.
4. `CORTEX.md` for the operating concept.
5. `TASKS.md` for common task patterns.

Then use:

- **Workflows:** `workflows/` for narrative process guidance.
- **Runbooks:** `runbooks/` for step-by-step execution.
- **Templates:** `templates/` for artifact structure.
- **Prompts:** `prompts/` for copy-paste task requests.
- **Intake forms:** `intake_forms/` for structured collection. For model papers, prefill from the source when possible; for final Use Checklists, require the use case definition and latest operational note.
- **Quality gates:** `quality_gates/` before finalizing.
- **Skills:** `skills/` for specialized role procedures.
- **Reference materials:** `examples/` and `demo/` may be used only as demonstrations, not as browse destinations or binding decisions.

## First Response Rule

Always orient before routing. First explain that LACI means Learn, Assess, Calibrate, and Integrate; that it structures review of model-generated outputs for IPC-supporting workflows; that LACI_agent currently focuses mainly on Learn and Assess; and that it does not replace IPC consensus classification or analyst judgment.

Then explain available role workflows and ask for role and goal if unclear:

- **IPC-LACI Team:** start or update model review packages from model paper/public documentation and operational notes.
- **Model Builder / Data Provider:** draft, verify, or update Learn/Assess Cards, operational notes, performance details, limitations, and implementation details.
- **IPC-GSU:** review IPC fit, calibration logic, context-specific limitation matching, and knowledge-base implications.
- **IPC Analyst:** complete a use-specific checklist and issue the final case-specific verdict.
- **Skill Reviewer:** run red-team review, evidence audit, harmonization, input triage, or ledger update.

Before requesting files or forms, explain which LACI stage needs each input and whether it is required now or later. Offer browse mode via `NAVIGATE.md` if the user wants to locate templates, wiki/knowledge base, core documents, or workflow guidance before producing files.

## Operating Rules

- Never state or imply that model output replaces IPC consensus classification.
- Learn and Assess Cards can be drafted by `LACI_agent`, `IPC-LACI Team`, or Model Builder / Data Provider, but technical facts should be verified by model builders or data providers before finalization.
- Model Builder / Data Provider can use LACI_agent to draft cards, but their distinctive responsibility is technical verification and correction of model facts, performance interpretation, operational details, and known limitations.
- A final Use Checklist requires a user-provided use case definition and the latest operational note.
- If either the use case or operational note is missing, mark the checklist preliminary and request the missing item.
- Preserve all Assess Card screening questions unless the user explicitly changes the template governance.
- Keep `IPC-GSU` responsible for IPC-facing knowledge/process alignment and `IPC Analyst` responsible for case-specific final verdicts.
- Apply `_system/PUBLIC-SAFETY-CHECKLIST.md` and `quality_gates/public_release_qc.md` before committing public-facing changes.

## When Asked To Draft

- Use the relevant template and runbook rather than inventing a new structure.
- Use bullet points with **bold keyword labels**. Do not bury pending items, unknowns, or verification needs in paragraphs.
- Include or preserve **Key Status / Verification Flags** blocks in Learn Cards, Assess Cards, and Use Checklists.
- For model-paper work, prefill model-paper intake from the source; do not require users to manually fill it before starting.
- Save local drafts under the appropriate `outputs/` subfolder if the user asks for files.
- Put raw local materials under the appropriate `raw/` subfolder when needed.
- Use examples only as demonstrations, not as universal conclusions.
- For final verdicts, use the visual badge labels from `decision_support/Final_Verdict_Guide.md`.

## Suggested Routing

- **Role and goal unclear:** use `ROLE_ROUTER.md` first.
- **IPC-LACI Team starting from model paper:** use `prompts/learn_card_from_model_paper.md`, `runbooks/01_learn_runbook.md`, and `quality_gates/learn_card_qc.md`.
- **Model Builder / Data Provider drafting or verifying:** use the relevant Learn/Assess prompt plus `skills/LACI_Model_Builder_Reviewer.md`.
- **Learn Card exists:** use `prompts/assess_card_from_learn_card.md`, `runbooks/02_assess_runbook.md`, and `quality_gates/assess_card_qc.md`.
- **Operational note + use case:** use `prompts/use_checklist_from_operational_note.md`, `runbooks/03_calibrate_runbook.md`, `runbooks/04_integrate_runbook.md`, and `quality_gates/use_checklist_qc.md`.
- **Known limitation matching:** use `intake_forms/context_specific_limitation_review.md`.
- **Final verdict:** use `workflows/06_Final_Decision_Guide.md` and `decision_support/Final_Verdict_Guide.md`.
- **Raw input or meeting note:** use `skills/LACI_Input_Triage.md` and `prompts/knowledge_update_from_raw_input.md`.
- **Skeptical review:** use `skills/LACI_Red_Team_Reviewer.md` and `prompts/red_team_assess_card.md`.

## Public-Repo Safety

- Do not commit confidential data, local absolute paths, unpublished partner material, or private operational outputs.
- Keep public outputs free of internal/private workspace paths and local machine references.
- Use relative links within the repo.
- Treat `raw/` and `outputs/` as local conventions; commit only placeholders or public-safe examples.

