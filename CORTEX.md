# LACI_agent Cortex

`LACI_agent` is a Cortex-style agent workspace. It is not a standalone software application and it does not make IPC decisions by itself. It is an operating environment that helps AI assistants and human reviewers run LACI workflows consistently using shared instructions, templates, skills, examples, and knowledge-base anchors.

## What Cortex Means

In this repository, **Cortex** means the organized working layer that lets an AI assistant operate with context, procedure, and guardrails. It is similar to a shared project brain: not because it decides for people, but because it keeps the documents, skills, prompts, runbooks, examples, and quality checks in one place.

A Cortex-style workspace answers five practical questions for the assistant and the user:

- **What should I read first?** Entrypoints and core documents establish context.
- **What task am I doing?** Task routes and prompts identify the LACI stage.
- **How should I do it?** Runbooks, templates, and skills provide the method.
- **How do I know it is good enough?** Quality gates and review roles define checks.
- **When must a human decide?** Human gates keep IPC judgment, technical verification, and final verdicts with the appropriate people.

For LACI_agent, Cortex-style means the repo is not just a library of documents. It is a structured workspace that helps Codex, Claude, Cursor, ChatGPT, or another assistant support LACI work consistently while preserving human review and IPC governance.

## Operating Concept

- **Learn:** Convert model documentation into a structured Learn Card.
- **Assess:** Evaluate baseline credibility, IPC relevance, known limitations, and context-specific suitability.
- **Calibrate:** Translate assessed outputs into bounded analyst-facing interpretation for a defined use case.
- **Integrate:** Support a final analyst decision record for a specific IPC-supporting workflow.

## What Makes This Cortex-Style

- **Entrypoints:** `README.md`, `ENTRY.md`, and `TASKS.md` tell users and assistants where to begin.
- **Agent instructions:** `AGENTS.md`, `CLAUDE.md`, setup guides, and `_system/` files define how assistants should operate.
- **Skills:** `skills/` provides role-specific procedures for routing, evidence review, red-team review, IPC process review, and ledger updates.
- **Runbooks:** `runbooks/` turns L-A-C-I stages into repeatable procedures.
- **Prompt library:** `prompts/` gives copy-paste task prompts for Codex, Claude, Cursor, ChatGPT, and similar tools.
- **Intake forms:** `intake_forms/` makes required inputs explicit before drafting or finalizing outputs.
- **Raw/output conventions:** `raw/` and `outputs/` guide local work while keeping the public repo clean.
- **Quality gates:** `quality_gates/` gives pre-finalization checks before a card, checklist, or public release is accepted.

## Agent Loop

1. **Intake:** Identify task, source material, use case, and missing inputs.
2. **Route:** Select the relevant LACI stage, skill, runbook, template, and quality gate.
3. **Draft:** Populate the requested card, checklist, review, or knowledge update.
4. **Check:** Apply evidence, IPC process, context-specific limitation, and public-safety checks.
5. **Human review:** Send technical claims to model builders/data providers and IPC-facing judgments to IPC-GSU or IPC analysts as appropriate.
6. **Finalize:** Store the final artifact in the appropriate output location and record any knowledge update or ledger entry.

## Non-Replacement Rule

No model output, including IPC Outcome Modeling or IPC-indicative outputs, replaces IPC consensus-based actual outcome classification. LACI_agent supports documentation, review, and decision support. It does not replace IPC protocols, analyst judgment, or authorized IPC governance.

