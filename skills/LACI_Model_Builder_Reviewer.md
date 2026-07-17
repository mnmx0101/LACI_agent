# Skill-Model Builder Reviewer

## Purpose

Review LACI artifacts from the perspective of model builders, data providers, and operationalization feasibility.

## Trigger

Use this skill when technical facts, model implementation details, validation interpretation, or operational notes need review.

## Inputs Needed

- **Artifact:** Learn Card, Assess Card, operational note, or checklist.
- **Model documentation:** Paper, technical note, data dictionary, model card, or API/output description.
- **Operational details:** Version, run date, data cut-off, source lags, output labels, and implementation changes.

## Steps

1. **Check factual accuracy:** Verify target, features, labels, output definitions, training data, and validation design.
2. **Review performance interpretation:** Confirm whether reported metrics are interpreted correctly.
3. **Check operational feasibility:** Confirm output availability, frequency, spatial/temporal units, and reproducibility.
4. **Clarify limitations:** Identify known failure modes, non-represented contexts, and data interruptions.
5. **Separate public-source inference:** Mark where the LACI_agent inferred information from papers rather than provider confirmation.

## Output Format

- **Verified facts:** Confirmed technical content.
- **Corrections:** Incorrect or misleading statements.
- **Missing details:** Information needed to finalize cards.
- **Operational notes:** Versioning, lags, units, or implementation constraints.
- **Recommended wording:** Diplomatic but precise replacements.

## Failure / Stop Conditions

- **No documentation:** Technical review remains preliminary.
- **No operational note:** Current-use checklist cannot be finalized.
- **Unverified implementation:** Do not imply production readiness.

## Related Templates

- [Model Paper Intake](../intake_forms/model_paper_intake.md)
- [Operational Note Intake](../intake_forms/operational_note_intake.md)
- [Learn Card Template](../templates/LACI_Learn_Card_Template.md)

## Related Knowledge Base

- [CORTEX](../CORTEX.md)
- [Quality Gates](../quality_gates/)
