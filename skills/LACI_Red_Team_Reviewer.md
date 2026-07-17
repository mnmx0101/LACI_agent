# Skill-Red Team Reviewer

## Purpose

Stress-test LACI artifacts for weak logic, unsupported claims, misuse risk, overclaiming, and vague analyst guidance.

## Trigger

Use this skill before sharing an Assess Card, Use Checklist, final verdict, workflow decision, or public-facing template update.

## Inputs Needed

- **Artifact:** Draft Learn Card, Assess Card, Use Checklist, final verdict, or guidance note.
- **Use case if relevant:** IPC application, geography, time window, current context, and intended analyst action.
- **Sources:** Evidence used to support claims.

## Steps

1. **Find overclaiming:** Identify where the artifact suggests stronger use than the evidence supports.
2. **Stress-test context:** Compare known model limitations with current conditions and analysis environment.
3. **Check actionability:** Ask whether an IPC analyst would know what to do next.
4. **Check missing gates:** Look for absent operational note, use case definition, performance implication, or spatial/temporal alignment.
5. **Challenge verdict:** Test whether the final verdict follows from checklist findings.
6. **Recommend revisions:** Make findings specific and implementable.

## Output Format

- **Severity:** Critical, major, moderate, or minor.
- **Finding:** Concise issue statement.
- **Why it matters:** Operational or IPC-facing risk.
- **Evidence:** Source line, section, or artifact reference.
- **Fix:** Specific revision or required input.

## Failure / Stop Conditions

- **No artifact:** Cannot review abstract intent alone.
- **No use case for checklist:** Cannot judge case-specific guidance.
- **Evidence unavailable:** Mark findings as risk-based, not source-confirmed.

## Related Templates

- [Red-Team Prompt](../prompts/red_team_assess_card.md)
- [Assess Card Quality Gate](../quality_gates/assess_card_qc.md)
- [Use Checklist Quality Gate](../quality_gates/use_checklist_qc.md)

## Related Knowledge Base

- [Final Verdict Guide](../decision_support/Final_Verdict_Guide.md)
- [CORTEX](../CORTEX.md)
