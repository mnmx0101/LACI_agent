# Skill-Input Triage

## Purpose

Organize raw inputs, memos, meeting notes, model materials, and comments into public-safe working notes and proposed knowledge updates.

## Trigger

Use this skill when the user provides unsorted input, meeting notes, partner comments, operational notes, or asks to update the knowledge base.

## Inputs Needed

- **Raw input:** File, pasted note, meeting memo, or source material.
- **Sensitivity status:** Public, internal, restricted, unknown.
- **Target:** Learn, Assess, Calibrate, Integrate, wiki/knowledge update, or ledger entry.

## Steps

1. **Separate material:** Distinguish raw claims, confirmed facts, assumptions, questions, and action items.
2. **Check public safety:** Flag confidential or restricted content before any commit.
3. **Assign destination:** Route content to `raw/`, `outputs/knowledge_updates/`, `knowledge_base/`, or a template.
4. **Ask confirmation:** Do not convert raw input into knowledge-base language until the user confirms.
5. **Prepare update:** Draft concise proposed knowledge-base text and cite the source note.

## Output Format

- **Raw summary:** What was provided.
- **Confirmed items:** Facts ready for use.
- **Open questions:** Items requiring user/model-builder/IPC-GSU confirmation.
- **Proposed destination:** Folder or document.
- **Proposed update:** Draft public-safe language.

## Failure / Stop Conditions

- **Sensitivity unknown:** Treat as private until confirmed.
- **No source trace:** Mark as unverified.
- **Conflicting instructions:** Ask the user to choose which source controls.

## Related Templates

- [Knowledge Update Prompt](../prompts/knowledge_update_from_raw_input.md)
- [Public Safety Checklist](../_system/PUBLIC-SAFETY-CHECKLIST.md)

## Related Knowledge Base

- [Knowledge Base](../knowledge_base/)
- [Raw Inputs](../raw/README.md)
