# Skill-Document Harmonizer

## Purpose

Keep LACI language, logic, document roles, and task ownership aligned across README, core documents, templates, workflows, examples, skills, and knowledge-base files.

## Trigger

Use this skill when terminology changes, templates are revised, ownership language shifts, or documents disagree with each other.

## Inputs Needed

- **Documents to compare:** Files or folders.
- **Target concept:** Term, workflow step, ownership rule, template section, or verdict language.
- **Preferred wording:** If supplied by the user or agreed in knowledge base.

## Steps

1. **Map affected documents:** Identify every file using the concept.
2. **Find drift:** Note contradictions, stale terms, and mismatched ownership.
3. **Propose standard wording:** Use concise, diplomatic language that preserves procedural strictness.
4. **Patch documents:** Update only relevant text and links.
5. **Check consistency:** Run targeted search for old terms.
6. **Record update:** Add or propose a ledger/knowledge update when appropriate.

## Output Format

- **Standard wording:** Final preferred language.
- **Files updated:** Path list.
- **Drift resolved:** Summary of conflicts fixed.
- **Remaining questions:** Any unresolved policy or ownership issue.

## Failure / Stop Conditions

- **Preferred wording unclear:** Ask user to confirm before broad replacements.
- **Policy conflict:** Do not harmonize away meaningful disagreement.
- **Public-safety concern:** Stop before exposing internal or restricted wording.

## Related Templates

- [Public Release Quality Gate](../quality_gates/public_release_qc.md)
- [Public Safety Checklist](../_system/PUBLIC-SAFETY-CHECKLIST.md)

## Related Knowledge Base

- [Core Documents](../core_documents/)
- [Workflows](../workflows/)
- [Knowledge Base](../knowledge_base/)
