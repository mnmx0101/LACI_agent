# Skill-Change Ledger

## Purpose

Record meaningful changes to LACI documents, templates, skills, examples, and knowledge-base anchors so development remains traceable.

## Trigger

Use this skill when documents are updated, templates are revised, examples are changed, knowledge-base entries are added, or public repo structure changes.

## Inputs Needed

- **Files changed:** Path list or git diff summary.
- **Reason for change:** User request, review finding, template refinement, public-safety cleanup, or knowledge update.
- **Version/archive need:** Whether a previous current version should be archived.

## Steps

1. **Summarize change:** Capture what changed and why.
2. **Check scope:** Distinguish content change, structural change, naming cleanup, or safety cleanup.
3. **Record source:** Link to user request, review note, or source evidence when available.
4. **Archive if needed:** Preserve prior version when working in versioned document areas.
5. **Update ledger:** Write concise entry or prepare a ledger proposal.

## Output Format

- **Date:** YYYY-MM-DD.
- **Files:** Changed files.
- **Change type:** Content, structure, template, example, skill, safety, or repo organization.
- **Reason:** Why it changed.
- **Follow-up:** Verification or review still needed.

## Failure / Stop Conditions

- **Unclear provenance:** Mark source as unknown rather than inventing rationale.
- **Private source:** Do not quote confidential material in public ledger.
- **Archive ambiguity:** Ask before deleting or overwriting prior versions.

## Related Templates

- [Public Release Quality Gate](../quality_gates/public_release_qc.md)

## Related Knowledge Base

- [CORTEX](../CORTEX.md)
- [Public Safety Checklist](../_system/PUBLIC-SAFETY-CHECKLIST.md)
