# Skill-Orchestrator

## Purpose

Route LACI_agent work across Learn, Assess, Calibrate, and Integrate while keeping ownership, required inputs, and stop conditions visible.

## Trigger

Use this skill when the user asks what to do next, provides mixed materials, wants a workflow plan, or asks for an end-to-end LACI run.

## Inputs Needed

- **Task goal:** Learn Card, Assess Card, Use Checklist, review, knowledge update, or repo maintenance.
- **Available materials:** Model paper, Learn Card, Assess Card, operational note, use case definition, raw notes, or examples.
- **Output destination:** Local `outputs/` folder or public-safe repo file.
- **Human owner:** IPC-LACI Team, IPC-GSU, IPC Analyst, Model Builder, or another named reviewer.

## Steps

1. **Classify stage:** Assign the work to Learn, Assess, Calibrate, Integrate, or knowledge maintenance.
2. **Check prerequisites:** Identify missing use case, operational note, source evidence, or verification owner.
3. **Route skills:** Call the relevant skill role cards and runbooks.
4. **Set output:** Name the output artifact and target folder.
5. **Apply gates:** Select the relevant quality gate before finalizing.
6. **Record follow-up:** Note verification requests and knowledge/ledger updates.

## Output Format

- **Route:** Stage and task type.
- **Inputs present:** Available and missing.
- **Skills to use:** Linked skill files.
- **Next action:** Concrete next step.
- **Stop condition:** Any blocker that prevents final output.

## Failure / Stop Conditions

- **Undefined use case:** Cannot finalize a Use Checklist.
- **Missing operational note:** Checklist must remain preliminary.
- **Confidential input risk:** Stop before committing or quoting sensitive material.
- **Owner ambiguity:** Ask who owns the decision when the final verdict or governance step is unclear.

## Related Templates

- [Learn Card Template](../templates/LACI_Learn_Card_Template.md)
- [Assess Card Template](../templates/LACI_Assess_Card_Template.md)
- [Use Checklist Template](../templates/LACI_IPC_Analysis_Use_Checklist_Template.md)

## Related Knowledge Base

- [CORTEX](../CORTEX.md)
- [TASKS](../TASKS.md)
- [Agents And Skills](../_system/AGENTS-AND-SKILLS.md)
