# LACI_assistant

**LACI_assistant** is a public-facing workspace for developing, testing, and applying LACI: Learning, Assessing, Calibrating, and Integrating model-generated outputs for IPC-supporting workflows.

## What Is LACI?

- **Learn:** Understand what a model output is, what it predicts, how it is produced, and what metadata are needed.
- **Assess:** Evaluate technical credibility, documentation quality, IPC relevance, known limitations, and context-specific suitability.
- **Calibrate:** Translate assessed model outputs into bounded IPC-facing interpretation rules, caveats, and non-use constraints.
- **Integrate:** Decide whether and how the output can be considered in an IPC-supporting workflow for a defined use case.

## Who Is This For?

- **IPC Analyst:** Uses the final checklist and issues the case-specific final verdict for a defined IPC application, geography, time window, and analysis environment.
- **IPC-GSU:** Manages IPC-facing knowledge, process alignment, context-specific review standards, and the knowledge base used to guide analysts.
- **IPC-LACI Team:** Supports technical verification, documentation quality, reproducibility checks, workflow integrity, and implementation readiness.
- **LACI_assistant:** Drafts structured cards, organizes evidence, applies templates, routes tasks to skills, and prepares decision-support outputs for human review.
- **Model Builder / Data Provider:** Provides documentation, operational notes, implementation clarification, and factual verification.
- **Skills:** Specialized role cards used by LACI_assistant and reviewers. Skill-owned tasks are labeled as `Skill-[Name]` and linked below.

## LACI Workflow

| Step | Purpose | Main Input | Main Output | Primary Owner |
| :--- | :--- | :--- | :--- | :--- |
| **L - Learn** | Understand the model/output | Model paper, documentation, source metadata | Learn Card | LACI_assistant / IPC-LACI Team drafts; Model Builder verifies |
| **A - Assess** | Evaluate baseline and context-specific suitability | Learn Card, source evidence, IPC context | Assess Card | IPC-LACI Team for baseline; IPC-GSU and analysts for context |
| **C - Calibrate** | Translate assessed output into bounded IPC-facing interpretation | Assess Card, operational note, current context | Calibration guidance / checklist inputs | IPC-GSU with IPC-LACI Team support |
| **I - Integrate** | Decide whether/how output enters workflow | Checklist, final verdict, governance decision | IPC workflow decision record | IPC Analyst / authorized IPC process owner |

## Roles

| Role | Main Responsibility | Typical Output |
| :--- | :--- | :--- |
| **LACI_assistant** | Draft, organize, route, and structure the review; never replaces human verification or final judgment. | Draft Learn Card, draft Assess Card, draft checklist, structured notes. |
| **IPC-LACI Team** | Verify technical implementation, reproducibility, documentation quality, output integrity, and workflow readiness. | Technical verification notes, readiness checks, implementation review. |
| **Model Builder / Data Provider** | Verify factual model details and provide current operational documentation. | Verified model facts, operational note, clarification responses. |
| **IPC-GSU** | Maintain IPC-facing knowledge and ensure process alignment, context-specific review standards, and interpretation discipline. | Knowledge-base updates, process guidance, context review standards. |
| **IPC Analyst** | Complete the case-specific judgment and final verdict for a defined IPC use case. | Final verdict, allowed/not allowed handling, decision notes. |
| **Skill Roles** | Provide specialized review functions under named skills. | Routed skill findings and recommendations. |

## Task Ownership By L-A-C-I Step

### L - Learn

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Source Intake** | Intake model paper, documentation, operational note, or meeting memo. | LACI_assistant | [Skill-Input Triage](skills/LACI_Input_Triage.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Source note / intake log. |
| **Model Understanding** | Draft Learn Card from public model paper and available documentation. | LACI_assistant / IPC-LACI Team | [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md); [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Public-source Learn Card draft. |
| **Technical Verification** | Verify model facts, output definitions, spatial/temporal metadata, and operational details. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Verified Learn Card facts. |
| **Knowledge Capture** | Store reusable concepts, source notes, and confirmed assumptions. | IPC-GSU | [Skill-Input Triage](skills/LACI_Input_Triage.md); [Skill-Change Ledger](skills/LACI_Change_Ledger.md) | Knowledge-base update. |

### A - Assess

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Baseline Screening** | Draft baseline model-output assessment while preserving all screening questions. | LACI_assistant / IPC-LACI Team | [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md); [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Baseline Assess Card draft. |
| **Model-Method Verification** | Verify methods, performance metrics, limitations, and operational implementation claims. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Model Builder Reviewer](skills/LACI_Model_Builder_Reviewer.md) | Verified technical content. |
| **IPC Compatibility** | Review AFI/AMN/process fit, evidence convergence implications, threshold meaning, and non-replacement guardrails. | IPC-GSU | [Skill-IPC-GSU Reviewer](skills/LACI_IPC_GSU_Reviewer.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | IPC-facing assessment notes. |
| **Context-Specific Assessment** | Compare known model limitations against the actual analysis environment. | IPC-GSU / IPC Analyst | IPC-LACI Team; [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Context-specific limitation match. |

### C - Calibrate

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Use Case Definition** | Define IPC application, working function, geography, time window, intended analyst action, current analysis environment, and decision owner. | IPC Analyst / requester | IPC-GSU; LACI_assistant | Required use-case definition. |
| **Operational Note Check** | Confirm latest operational note, model run/version, data cut-off, source lags, and output labels. | Model Builder / Data Provider | IPC-LACI Team; [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Operational note status. |
| **Signal Translation** | Translate model thresholds, alerts, probabilities, or scores into bounded analyst-facing interpretation. | IPC-GSU | IPC-LACI Team; [Skill-IPC-GSU Reviewer](skills/LACI_IPC_GSU_Reviewer.md) | Calibration guidance. |
| **Limitation Matching** | Determine whether current conditions trigger known limitations or reassessment. | IPC-GSU / IPC Analyst | [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md); [Skill-Evidence Auditor](skills/LACI_Evidence_Auditor.md) | Context-specific limitation match table. |

### I - Integrate

| Subgroup | Task | Primary Owner | Supporting Skills / Roles | Output |
| :--- | :--- | :--- | :--- | :--- |
| **Checklist Completion** | Complete IPC Analysis Use Checklist for the defined use case. | IPC Analyst | LACI_assistant; IPC-GSU; IPC-LACI Team | Completed checklist. |
| **Final Verdict** | Issue final verdict with bullet-point reasoning, allowed actions, and not-allowed actions. | IPC Analyst | IPC-GSU; [Skill-Red Team Reviewer](skills/LACI_Red_Team_Reviewer.md) | Final verdict. |
| **Workflow Decision** | Decide whether the output can enter a specific IPC-supporting workflow. | Authorized IPC process owner | IPC Analyst; IPC-GSU; IPC-LACI Team | Workflow decision record. |
| **Learning Loop** | Record decisions, limitations, template feedback, and updates to knowledge base. | IPC-GSU / LACI_assistant | [Skill-Change Ledger](skills/LACI_Change_Ledger.md); [Skill-Document Harmonizer](skills/LACI_Document_Harmonizer.md) | Ledger entry and knowledge update. |

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

## Partner Vs Reviewer Responsibilities

- **Partners provide evidence:** model papers, documentation, operational notes, implementation clarification, and factual verification.
- **IPC-LACI Team verifies technical implementation:** reproducibility, versioning, data pipeline, output integrity, and documentation quality.
- **IPC-GSU manages IPC-facing knowledge:** context standards, IPC process alignment, and reusable guidance.
- **IPC Analyst makes the case-specific verdict:** final checklist decisions are tied to a defined use case, current context, and analysis environment.
- **No model output replaces IPC consensus classification.**

## Drafting And Verification Rule

LACI_assistant can draft Learn and Assess Cards from public model papers and available documentation. These drafts are useful for structured review, but model builders or data providers should verify technical facts before the cards are treated as final. The IPC Analysis Use Checklist is different: it requires a specific use case definition and the latest operational note because it evaluates whether a model output can be considered for a defined IPC application, geography, time window, and analysis environment.

## Required Operational Note Rule

- **Operational Note Missing:** checklist is preliminary only.
- **Operational Note Stale:** reassess first.
- **Operational Note Current:** proceed to context-specific limitation match.

## Required Use Case Rule

A Use Checklist cannot be completed without a use case definition. If the use case is missing or incomplete, mark the checklist `Preliminary / Use Case Incomplete` and request missing fields.

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

- [Core Documents](core_documents/)
- [Templates](templates/)
- [Workflows](workflows/)
- [Knowledge Base](knowledge_base/)
- [Skills / Role Cards](skills/)
- [Partner Submission](partner_submission/)
- [Decision Support](decision_support/)
- [Examples](examples/)
- [Sources](sources/)

