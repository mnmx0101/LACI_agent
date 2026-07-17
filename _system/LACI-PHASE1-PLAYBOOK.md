# LACI Phase 1 Playbook

Use this playbook to test LACI_agent with colleagues during initial rollout.

## Phase 1 Goals

- **Orient users:** Make the repo understandable after cloning.
- **Test workflow:** Confirm Learn -> Assess -> Calibrate -> Integrate can be followed from templates and examples.
- **Stress-test usefulness:** Check whether final checklist verdicts are specific enough for analyst decision support.
- **Capture feedback:** Turn confusing comments, meeting notes, or template gaps into proposed knowledge updates.

## Suggested Sequence

1. **Orientation test:** Ask a new user to read `README.md` and `ENTRY.md`, then describe what LACI_agent can and cannot do.
2. **Demo test:** Run the Yemen walkthrough in `demo/yemen_walkthrough.md`.
3. **Model-paper test:** Draft one Learn Card from a public model paper using `prompts/learn_card_from_model_paper.md`.
4. **Assessment test:** Draft or red-team one Assess Card using `runbooks/02_assess_runbook.md` and `quality_gates/assess_card_qc.md`.
5. **Use checklist test:** Require a use case definition and latest operational note before producing a final verdict.
6. **Public release check:** Run `_system/PUBLIC-SAFETY-CHECKLIST.md` before committing changes.

## Feedback Capture

Store public-safe feedback as proposed updates in `outputs/knowledge_updates/`. Do not commit private notes unless reviewed for public release.
