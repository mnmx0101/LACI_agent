# Skill-IPC-GSU Reviewer

## Purpose

Review LACI artifacts for IPC process fit, practical usability, evidence-convergence implications, and analyst-facing clarity.

## Trigger

Use this skill when assessing IPC application fit, AFI/AMN relevance, spatial/temporal alignment, threshold meaning, or final checklist usefulness.

## Inputs Needed

- **Artifact:** Assess Card, Use Checklist, calibration note, or final verdict.
- **IPC application:** AFI, AMN, other, or exploratory.
- **Use case definition:** Geography, time window, analytical function, analyst action, and decision owner.
- **Current context:** Conditions that may trigger model limitations.

## Steps

1. **Check IPC fit:** Confirm whether the output can support the proposed IPC workflow role.
2. **Check non-replacement:** Ensure no model output is treated as replacing IPC consensus-based classification.
3. **Review spatial/temporal alignment:** Compare model units to IPC analysis requirements.
4. **Review threshold meaning:** Explain what thresholds, alerts, scores, or probabilities imply for IPC interpretation.
5. **Assess practicality:** Decide whether the guidance is actionable for analysts.
6. **Tighten verdict:** Make final guidance specific, bounded, and tied to current context.

## Output Format

- **IPC fit:** Suitable, constrained, unclear, or unsuitable.
- **Key constraints:** Spatial, temporal, threshold, evidence, or context limits.
- **Analyst guidance:** What can be considered, cross-checked, or avoided.
- **Required revisions:** Edits before final use.

## Failure / Stop Conditions

- **No use case:** Cannot judge operational IPC fit.
- **No current context:** Cannot complete context-specific limitation match.
- **Overclaiming:** Block finalization until language is constrained.

## Related Templates

- [Use Case Definition](../intake_forms/use_case_definition.md)
- [Context-Specific Limitation Review](../intake_forms/context_specific_limitation_review.md)
- [Use Checklist Template](../templates/LACI_IPC_Analysis_Use_Checklist_Template.md)

## Related Knowledge Base

- [IPC Technical Manual Reference](../core_documents/IPC_Technical_Manual_Reference.md)
- [Final Verdict Guide](../decision_support/Final_Verdict_Guide.md)
