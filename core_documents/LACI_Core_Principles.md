# LACI Core Principles

**Audience:** Public / partner-facing summary and IPC reviewer orientation.

## What LACI Does

- **Purpose:** LACI supports Learning, Assessing, Calibrating, and Integrating model-generated outputs for IPC-supporting workflows.
- **Boundary:** LACI does not authorize IPC classification and does not replace consensus-based IPC protocols.
- **Primary Output:** LACI produces structured documentation, assessment, use-checklist decisions, and final verdicts for bounded analytical consideration.

## Core Terms

- **Model-Generated Output:** A model score, forecast, alert, probability, class, indicator, exposure estimate, or other output proposed for analytical consideration.
- **Learn Card:** A structured model/output metadata record. It can be drafted from public sources, but should be verified by the model builder or data provider before finalization.
- **Assess Card:** A baseline and context-specific assessment record. Technical/model-method sections can be drafted from public sources, but should be verified by the model builder or data provider before finalization.
- **Operational Note:** The latest run/version-specific metadata needed before completing a use checklist.
- **IPC Analysis Use Checklist:** A concise decision aid for a specific use case, geography, time window, and analysis environment.
- **Final Verdict:** The simplified decision outcome from the checklist. It is not IPC classification approval.

## Non-Replacement Rule

- **No Replacement:** No model output can replace IPC consensus classification.
- **No Shortcut:** No model threshold, score, alert, or predicted phase can satisfy IPC convergence by itself.
- **No Official Population Estimate:** Model exposure or population outputs are not official IPC population estimates unless accepted through IPC processes.

## Drafting And Verification Rule

- **Drafting:** LACI_agent and the IPC-LACI Team may draft Learn and Assess Cards from public papers, public documentation, operational notes, and available metadata.
- **Model-Builder Verification:** Model builders or data providers should verify model purpose, data inputs, target construction, thresholds, validation, limitations, and intended interpretation before Learn/Assess cards are treated as final.
- **IPC-LACI Team Verification:** The IPC-LACI Team verifies implementation, reproducibility, data pipeline, operational output integrity, and documentation quality.
- **IPC Context Review:** IPC-GSU / country-regional analysts complete context-specific interpretation.
- **Workflow Decision:** Authorized IPC process owners decide whether and how a model output may be considered in IPC workflow.

## Status Labels

- `Drafted from public sources`
- `Awaiting model-builder verification`
- `Model-builder verified`
- `IPC-LACI Team technical verification complete`
- `IPC context-specific review complete`
- `Final for this use case`

## Use Checklist Rule

- **Use Case Required:** A checklist cannot be completed without a user-provided use case definition.
- **Operational Note Required:** A checklist requires the latest operational note.
- **Missing Use Case:** Mark `Preliminary / Use Case Incomplete` and request missing fields.
- **Missing Operational Note:** Mark `Preliminary only` and request current run metadata.




