# IPC Technical Manual Reference

The IPC Technical Manual is a core reference for LACI_agent because LACI assessments must understand IPC process, convergence of evidence, AFI/AMN logic, evidence reliability, geography, thresholds, and the non-replacement boundary between model outputs and IPC consensus classification.

## Included Source

- **File:** [IPC_Technical_Manual_3_Final.pdf](../sources/IPC_Technical_Manual_3_Final.pdf)
- **Role in LACI_agent:** Core source grounding for IPC-facing review, especially AFI, AMN, evidence reliability, convergence, threshold/signal interpretation, and calibration guardrails.

## Use In LACI_agent

Use the manual to inform:

- **Learn:** Whether model targets, geography, time units, and metadata are meaningful for IPC workflows.
- **Assess:** Whether model outputs align with IPC evidence logic without replacing consensus classification.
- **Calibrate:** Whether thresholds, alerts, model scores, and population estimates have bounded IPC-facing interpretation.
- **Integrate:** Whether analysts may consider the output for a specific IPC application and use case.

## Non-Replacement Rule

No model output, including IPC outcome modeling or IPC-indicative outputs, replaces consensus-based IPC classification. The manual grounds LACI_agent review; it does not turn model outputs into IPC outcomes.
