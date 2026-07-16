# IPC Protocols 2.4 and 2.5 as LACI Evidence Reliability Analogue

- Status: confirmed wiki anchor
- Source: IPC Technical Manual Version 3.1. Keep the manual in the private `sources/` workspace or a repository-approved source location.
- Source location: Protocol 2.4 appears around extracted PDF page 60; Protocol 2.5 appears around extracted PDF page 65.
- Confirmed by: user request on 2026-07-15
- Affects: Framework, Assess Card, IPC-GSU review, Evidence Auditor, future Calibrate/Integrate guidance

## Anchor Text

IPC Protocol 2.4 evaluates evidence reliability by considering the soundness of the method and the time relevance of the evidence. Protocol 2.5 then uses the reliability and number of evidence pieces to define minimum evidence and analysis requirements for IPC classification.

For LACI, these protocols are a key analogue for thinking about model-generated outputs. LACI should learn from the IPC logic that evidence must be assessed for methodological soundness, time relevance, directness, and sufficiency before it can support analysis.

LACI should not directly import or apply IPC evidence reliability scores to model-generated outputs. Model-output assessment needs its own translation because a model-generated output is not the same object as an IPC evidence piece. Any future LACI scoring, rating, or threshold system must be explicitly defined and justified rather than assumed from IPC Protocols 2.4 and 2.5.

## Concepts LACI Should Borrow Carefully

- Method soundness matters: LACI should ask whether the model method, validation design, input data, and output generation process are credible for the intended use.
- Time relevance matters: LACI should ask whether the model output, training data, inputs, validation period, and assumptions remain relevant to the current or projected IPC use context.
- Directness matters: LACI should distinguish outputs that estimate IPC-like outcomes from outputs that represent contributing factors, contextual signals, or proxy-trained alerts.
- Sufficiency matters: LACI should avoid letting one model output substitute for a body of convergent evidence.
- Documentation matters: LACI should preserve source, date, assumptions, limitations, and interpretation guidance for every assessed model-generated output.

## Concepts LACI Should Not Copy Directly

- Do not assign IPC R2/R1/R0 evidence reliability scores directly to model-generated outputs.
- Do not treat a model-output assessment as equivalent to IPC evidence-level classification requirements.
- Do not imply that passing LACI Assess makes an output official IPC evidence or authorizes IPC phase classification.
- Do not use Protocol 2.5 minimum evidence counts as LACI minimum model-output requirements without a separate LACI rationale.

## Implications For LACI Assess

LACI Assess should develop its own model-output reliability language while staying intelligible to IPC users. A strong Assess Card should make clear:

- what the model output is and is not
- whether the method is sound for the intended IPC-adjacent use
- whether the output is temporally relevant to the analysis cycle or projection horizon
- whether validation supports the specific geography, shock context, and application pathway
- whether uncertainty, limitations, and reassessment triggers are documented
- whether the output can support analysis only alongside other evidence

## Open Design Question

Should LACI eventually define model-output reliability levels that are inspired by IPC Protocols 2.4 and 2.5 but explicitly separate from IPC evidence reliability scores?




