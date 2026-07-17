# Skill-Model Builder Reviewer

## Purpose

Draft, verify, or update LACI artifacts from the perspective of model builders, data providers, and operationalization feasibility. This skill can help create cards, but its distinctive role is technical verification and correction.

## Trigger

Use this skill when a model builder or data provider wants to draft a card, verify an existing card, update operational details, correct technical facts, clarify validation interpretation, or document known limitations.

## Inputs Needed

- **Artifact:** Existing Learn Card, Assess Card, operational note, or checklist if the task is verification/update; not required when drafting from model documentation.
- **Model documentation:** Paper, technical note, data dictionary, model card, or API/output description.
- **Operational details:** Version, run date, data cut-off, source lags, output labels, and implementation changes.

## Steps

1. **Confirm task mode:** Draft new card, verify existing card, update operational note, or correct technical details.
2. **Check factual accuracy:** Verify target, features, labels, output definitions, training data, and validation design.
3. **Review performance interpretation:** Confirm whether reported metrics are interpreted correctly.
4. **Check operational feasibility:** Confirm output availability, frequency, spatial/temporal units, and reproducibility.
5. **Clarify limitations:** Identify known failure modes, non-represented contexts, and data interruptions.
6. **Separate public-source inference:** Mark where the LACI_agent inferred information from papers rather than provider confirmation.

## Output Format

- **Task mode:** Draft, verify, update, or correction.

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

