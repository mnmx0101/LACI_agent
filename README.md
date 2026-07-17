# LACI_agent

**LACI_agent** is a public, Cortex-style agent workspace for developing, testing, and applying LACI: **Learn, Assess, Calibrate, and Integrate** model-generated outputs for IPC-supporting workflows. It gives AI assistants structured instructions, skills, templates, examples, and knowledge-base anchors so they can help users draft LACI artifacts consistently.

This repository is intentionally flat: after cloning, the main content is visible immediately in the repo root.

## Start Here

1. **Read this page first.** It is the main front door for the repo.
2. **Open the task entrypoint:** [ENTRY.md](ENTRY.md) helps you choose what to do based on what material you have.
3. **Understand the operating concept:** [CORTEX.md](CORTEX.md) explains how this repo functions as an agent workspace rather than a standalone app.
4. **Choose your assistant:**
   - Claude users: read [CLAUDE.md](CLAUDE.md), then [setup/CLAUDE.md](setup/CLAUDE.md).
   - Codex users: read [AGENTS.md](AGENTS.md), then [setup/CODEX.md](setup/CODEX.md).
   - Cursor or other assistants: read [README.md](README.md), [ENTRY.md](ENTRY.md), [CORTEX.md](CORTEX.md), and [TASKS.md](TASKS.md).
5. **Choose your task:**
   - Model paper -> Learn Card.
   - Learn Card -> Assess Card.
   - Assess Card + operational note + use case -> IPC Analysis Use Checklist.
6. **Use the working conventions:** put local inputs under `raw/` and local generated artifacts under `outputs/`. Keep private material out of public commits.

## Cortex-Style Operating Layer

- **Entrypoints:** [ENTRY.md](ENTRY.md), [CORTEX.md](CORTEX.md), and [TASKS.md](TASKS.md).
- **System playbooks:** [_system/](_system/) for install, phase-1 testing, agent/skill routing, and public-safety checks.
- **Prompts:** [prompts/](prompts/) for copy-paste tasks across Codex, Claude, Cursor, ChatGPT, and similar tools.
- **Intake forms:** [intake_forms/](intake_forms/) for model papers, operational notes, use cases, and context-specific limitation review.
- **Runbooks:** [runbooks/](runbooks/) for the Learn, Assess, Calibrate, and Integrate stages.
- **Quality gates:** [quality_gates/](quality_gates/) for pre-finalization checks.
- **Local work areas:** [raw/](raw/) and [outputs/](outputs/) are conventions for local/private work, not public data dumps.
- **Demo path:** [demo/](demo/) gives a first walkthrough.

## What Is LACI?

- **Learn:** Understand what a model output is, what it predicts, how it is produced, and what metadata are needed.
- **Assess:** Evaluate technical credibility, documentation quality, IPC relevance, known limitations, and context-specific suitability.
- **Calibrate:** Translate assessed model outputs into bounded IPC-facing interpretation rules, caveats, and non-use constraints.
- **Integrate:** Decide whether and how the output can be considered in an IPC-supporting workflow for a defined use case.

## I Want To...

| I want to... | Open this | Use this template / guide |
| :--- | :--- | :--- |
| Understand the LACI workflow | [workflows/01_What_Is_LACI.md](workflows/01_What_Is_LACI.md) | [core_documents/LACI_Overview.md](core_documents/LACI_Overview.md) |
| Draft a Learn Card from a model paper | [workflows/02_Model_Paper_To_Learn_Card.md](workflows/02_Model_Paper_To_Learn_Card.md) | [templates/LACI_Learn_Card_Template.md](templates/LACI_Learn_Card_Template.md) |
| Draft an Assess Card | [workflows/03_Model_Paper_To_Assess_Card.md](workflows/03_Model_Paper_To_Assess_Card.md) | [templates/LACI_Assess_Card_Template.md](templates/LACI_Assess_Card_Template.md) |
| Draft a Use Checklist | [workflows/04_Operational_Note_To_Use_Checklist.md](workflows/04_Operational_Note_To_Use_Checklist.md) | [templates/LACI_IPC_Analysis_Use_Checklist_Template.md](templates/LACI_IPC_Analysis_Use_Checklist_Template.md) |
| Match known limitations to a current context | [workflows/05_Context_Specific_Limitation_Match.md](workflows/05_Context_Specific_Limitation_Match.md) | [decision_support/Context_Specific_Limitation_Review.md](decision_support/Context_Specific_Limitation_Review.md) |
| Produce or review a final verdict | [workflows/06_Final_Decision_Guide.md](workflows/06_Final_Decision_Guide.md) | [decision_support/Final_Verdict_Guide.md](decision_support/Final_Verdict_Guide.md) |
| Run a skeptical review | [skills/LACI_Red_Team_Reviewer.md](skills/LACI_Red_Team_Reviewer.md) | Assess Card or Use Checklist |
| Prepare a partner request | [partner_submission/README.md](partner_submission/README.md) | Partner submission templates |

## Using An AI Assistant

- **Claude:** use [CLAUDE.md](CLAUDE.md) as the instruction file and [setup/CLAUDE.md](setup/CLAUDE.md) as the user quickstart.
- **Codex:** use [AGENTS.md](AGENTS.md) as the instruction file and [setup/CODEX.md](setup/CODEX.md) as the user quickstart.

## Who Is This For?

- **IPC Analyst:** Uses the final checklist and issues the case-specific final verdict for a defined IPC application, geography, time window, and analysis environment.
- **IPC-GSU:** Manages IPC-facing knowledge, process alignment, context-specific review standards, and the knowledge base used to guide analysts.
- **IPC-LACI Team:** Supports technical verification, documentation quality, reproducibility checks, workflow integrity, and implementation readiness.
- **LACI_agent:** Drafts structured cards, organizes evidence, applies templates, routes tasks to skills, and prepares decision-support outputs for human review.
- **Model Builder / Data Provider:** Provides documentation, operational notes, implementation clarification, and factual verification.
- **Skills:** Specialized role cards used by LACI_agent and reviewers. Skill-owned tasks are labeled as `Skill-[Name]` and linked below.

## LACI Workflow

| Step | Purpose | Main Input | Main Output | Primary Owner |
| :--- | :--- | :--- | :--- | :--- |
| **L - Learn** | Understand the model/output | Model paper, documentation, source metadata | Learn Card | LACI_agent / IPC-LACI Team drafts; Model Builder verifies |
| **A - Assess** | Evaluate baseline and context-specific suitability | Learn Card, source evidence, IPC context | Assess Card | IPC-LACI Team for baseline; IPC-GSU and analysts for context |
| **C - Calibrate** | Translate assessed output into bounded IPC-facing interpretation | Assess Card, operational note, current context | Calibration guidance / checklist inputs | IPC-GSU with IPC-LACI Team support |
| **I - Integrate** | Decide whether/how output enters workflow | Checklist, final verdict, governance decision | IPC workflow decision record | IPC Analyst / authorized IPC process owner |

## Task Ownership By L-A-C-I Step

### L - Learn

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Source Intake** | Intake model paper, documentation, operational note, or meeting memo. | LACI_agent | [Skill-Input Triage](skills/LACI_Input_Triage.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Source note / intake log. |
| **Model Understanding** | Draft Learn Card from public model paper and available documentation. | LACI_agent / IPC-LACI Team | [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md); [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Public-source Learn Card draft. |
| **Technical Verification** | Verify model facts, output definitions, spatial/temporal metadata, and operational details. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Verified Learn Card facts. |
| **Knowledge Capture** | Store reusable concepts, source notes, and confirmed assumptions. | IPC-GSU | [Skill-Input Triage](skills/LACI_Input_Triage.md); [Skill-Change Ledger](skills/LACI_Change_Ledger.md) | Knowledge-base update. |

### A - Assess

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Baseline Screening** | Draft baseline model-output assessment while preserving all screening questions. | LACI_agent / IPC-LACI Team | [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md); [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Baseline Assess Card draft. |
| **Model-Method Verification** | Verify methods, performance metrics, limitations, and operational implementation claims. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Verified technical content. |
| **IPC Compatibility** | Review AFI/AMN/process fit, evidence convergence implications, threshold meaning, and non-replacement guardrails. | IPC-GSU | [Skill-IPC-GSU Reviewer](skills/LACI_IPC_GSU_Reviewer.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | IPC-facing assessment notes. |
| **Context-Specific Assessment** | Compare known model limitations against the actual analysis environment. | IPC-GSU / IPC Analyst | IPC-LACI Team; [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Context-specific limitation match. |

### C - Calibrate

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Use Case Definition** | Define IPC application, working function, geography, time window, intended analyst action, current analysis environment, and decision owner. | IPC Analyst / requester | IPC-GSU; LACI_agent | Required use-case definition. |
| **Operational Note Check** | Confirm latest operational note, model run/version, data cut-off, source lags, and output labels. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Operational note status. |
| **Signal Translation** | Translate model thresholds, alerts, probabilities, or scores into bounded analyst-facing interpretation. | IPC-GSU | IPC-LACI Team; [Skill-IPC-GSU Reviewer](skills/LACI_IPC_GSU_Reviewer.md) | Calibration guidance. |
| **Limitation Matching** | Determine whether current conditions trigger known limitations or reassessment. | IPC-GSU / IPC Analyst | [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Context-specific limitation match table. |

### I - Integrate

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Checklist Completion** | Complete IPC Analysis Use Checklist for the defined use case. | IPC Analyst | LACI_agent; IPC-GSU; IPC-LACI Team | Completed checklist. |
| **Final Verdict** | Issue final verdict with bullet-point reasoning, allowed actions, and not-allowed actions. | IPC Analyst | IPC-GSU; [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Final verdict. |
| **Workflow Decision** | Decide whether the output can enter a specific IPC-supporting workflow. | Authorized IPC process owner | IPC Analyst; IPC-GSU; IPC-LACI Team | Workflow decision record. |
| **Learning Loop** | Record decisions, limitations, template feedback, and updates to knowledge base. | IPC-GSU / LACI_agent | [Skill-Change Ledger](skills/LACI_Change_Ledger.md); [Skill-Document Harmonizer](skills/LACI_Document_Harmonizer.md) | Ledger entry and knowledge update. |

## Skill Roles

| Skill Label | Link | Main Use |
| :--- | :--- | :--- |
| **Skill-Orchestrator** | [LACI_Orchestrator](skills/LACI_Orchestrator.md) | Oversees routing across Learn, Assess, Calibrate, and Integrate. |
| **Skill-Input Triage** | [LACI_Input_Triage](skills/LACI_Input_Triage.md) | Sorts raw inputs, memos, meeting notes, and source materials. |
| **Skill-Evidence Auditor** | [LACI_Evidence_Auditor](skills/LACI_Evidence_Auditor.md) | Checks evidence support, performance records, and source traceability. |
| **Skill-IPC-GSU Reviewer** | [LACI_IPC_GSU_Reviewer](skills/LACI_IPC_GSU_Reviewer.md) | Reviews IPC process fit, practical usability, and IPC-facing constraints. |
| **Skill-Model Builder Reviewer** | [LACI_Model_Builder_Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Reviews model-method feasibility, operationalization, and technical facts. |
| **Skill-Red Team Reviewer** | [LACI_Red_Team_Reviewer](skills/LACI_Red_Team_Reviewer.md) | Stress-tests misuse risk, weak logic, overclaiming, and failure modes. |
| **Skill-Document Harmonizer** | [LACI_Document_Harmonizer](skills/LACI_Document_Harmonizer.md) | Keeps language, logic, and document roles aligned across LACI. |
| **Skill-Change Ledger** | [LACI_Change_Ledger](skills/LACI_Change_Ledger.md) | Records document updates, archive references, and checksum manifests. |

## Required Rules

- **Drafting and verification:** LACI_agent can draft Learn and Assess Cards from public model papers and available documentation. Model builders or data providers should verify technical facts before cards are final.
- **Operational note:** A real IPC Analysis Use Checklist requires the latest operational note. If the note is missing or stale, mark the checklist preliminary or reassess first.
- **Use case definition:** A Use Checklist cannot be completed without a specific use case definition.
- **Non-replacement:** No model output replaces IPC consensus classification.

## Final Verdict System

| Badge | Verdict | Meaning |
| :--- | :--- | :--- |
| ![RED - Do Not Consider](https://img.shields.io/badge/RED-Do%20Not%20Consider-dc2626) | `RED - Do Not Consider` | Output is unsuitable for this context or fails required gates. |
| ![ORANGE - Reassess First](https://img.shields.io/badge/ORANGE-Reassess%20First-f97316) | `ORANGE - Reassess First` | Relevant but current conditions or operational metadata require review. |
| ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) | `YELLOW - Investigation Prompt` | Can help analysts decide where to look harder. |
| ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) | `BLUE - Contextual Supporting Information` | Can support contextual interpretation with documented limitations. |
| ![GREEN - Consider As Assessed](https://img.shields.io/badge/GREEN-Consider%20As%20Assessed-16a34a) | `GREEN - Consider As Assessed` | All gates pass for the defined use case. |
| ![GRAY - Not Applicable](https://img.shields.io/badge/GRAY-Not%20Applicable-6b7280) | `GRAY - Not Applicable` | Output does not apply to the proposed IPC application/function. |

## Repository Map

- [Entry](ENTRY.md)
- [Cortex Operating Concept](CORTEX.md)
- [Task Patterns](TASKS.md)
- [System Playbooks](_system/)
- [Core Documents](core_documents/)
- [Templates](templates/)
- [Workflows](workflows/)
- [Runbooks](runbooks/)
- [Prompt Library](prompts/)
- [Intake Forms](intake_forms/)
- [Quality Gates](quality_gates/)
- [Knowledge Base](knowledge_base/)
- [Skills / Role Cards](skills/)
- [Partner Submission](partner_submission/)
- [Decision Support](decision_support/)
- [Examples](examples/)
- [Demo](demo/)
- [Sources](sources/)
- [Local Raw Input Convention](raw/)
- [Local Output Convention](outputs/)
- [Setup Guides](setup/)
## Data And Source Safety

This repository is public. Do not commit confidential IPC analysis, restricted partner material, unpublished operational data, local machine paths, or private notes. The IPC Technical Manual is included as a core source reference only because the repository owner indicated the repo is public and requested inclusion.



