# Skill-Evidence Auditor

## Purpose

Check whether model claims, performance records, limitations, and IPC-facing statements are supported by traceable evidence.

## Trigger

Use this skill when drafting or reviewing Learn Cards, Assess Cards, Use Checklists, knowledge updates, or red-team findings.

## Inputs Needed

- **Artifact to audit:** Learn Card, Assess Card, checklist, review, or knowledge note.
- **Sources:** Model paper, operational note, technical documentation, IPC manual reference, or partner clarification.
- **Claim list:** Explicit or inferred claims requiring verification.

## Steps

1. **Extract claims:** Identify technical, performance, spatial/temporal, and IPC-facing claims.
2. **Match sources:** Link each claim to source evidence or mark unsupported.
3. **Check performance record:** Verify metric values, metric definitions, and interpretation.
4. **Check limitation logic:** Confirm whether known limitations are documented and connected to use-case risks.
5. **Flag uncertainty:** Separate evidence, inference, and unverified claims.

## Output Format

- **Supported claims:** Claim plus source.
- **Unsupported or weak claims:** Claim, risk, and needed evidence.
- **Performance notes:** Metric, value, meaning, and relevance.
- **Verification requests:** Questions for model builder, data provider, IPC-LACI Team, or IPC-GSU.

## Failure / Stop Conditions

- **No source evidence:** Do not present claim as confirmed.
- **Metric unclear:** Do not interpret performance without defining the metric.
- **Operational note missing:** Do not finalize current-use guidance.

## Related Templates

- [Learn Card Template](../templates/LACI_Learn_Card_Template.md)
- [Assess Card Template](../templates/LACI_Assess_Card_Template.md)
- [Use Checklist Template](../templates/LACI_IPC_Analysis_Use_Checklist_Template.md)

## Related Knowledge Base

- [IPC Technical Manual Reference](../core_documents/IPC_Technical_Manual_Reference.md)
- [Knowledge Base](../knowledge_base/)
