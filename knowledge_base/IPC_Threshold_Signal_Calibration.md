# IPC Threshold / Signal Calibration Anchor

## Confirmed Rule

LACI calibration must document what a model threshold, score, anomaly, alert, class, or outcome-trained label means before it is interpreted for IPC use. This applies whether the signal is an IPC Reference Table threshold, a non-IPC statistical threshold, a model-internal cutoff, or a proxy-trained label.

## Threshold Types To Record

- IPC Reference Table thresholds where directly applicable, such as selected AFI food consumption or AMN anthropometric thresholds.
- Non-IPC statistical thresholds, such as long-term-average anomalies, LTA - 2 SD, z-scores, percentiles, return periods, or anomaly bands.
- Model-internal thresholds, such as probability cutoffs, severity bands, alert classes, or risk categories.
- Outcome-trained or proxy-trained labels, including FEWS NET, IPC-like, AMN-like, crisis, severity, or food-security labels.

## Calibration Questions

For any modeled signal being considered in LACI, reviewers should ask:

1. What exactly is the model signal?
2. What threshold or decision rule is being applied?
3. What does that threshold or signal mean in its source system?
4. What can it imply for IPC analysis?
5. What can it not imply?
6. What analyst-facing translation, caveat, cross-check, or non-use rule is required?

## IPC Interpretation Guardrail

IPC Reference Table thresholds help analysts interpret evidence within IPC convergence. Non-IPC thresholds and modeled cutoffs may still be relevant, but only after their meaning and limitations are documented. No single threshold, anomaly, model score, probability, or trained label can substitute for IPC convergence of evidence or consensus-based IPC classification.

## AFI Population And 20 Percent Compatibility

When a model output may be interpreted as supporting AFI area phase or affected-population reasoning, LACI must document whether the output is compatible with IPC population distribution logic. Reviewers should check whether the output:

- identifies the relevant denominator, such as people, households, children, or administrative-area population;
- separates Phase 3+, Phase 4+, Phase 5, or other phase-like categories when such interpretation is being proposed;
- can inform, but not determine, the IPC logic that an area phase is based on the most severe phase affecting at least 20 percent of the relevant population or households;
- avoids inferring Phase 4+ or more severe implications from a Phase 3+ aggregate alone; and
- clearly states that model-derived population outputs are not official IPC population estimates unless accepted through IPC processes.

## LACI Placement

- Learn Card: records native spatial/temporal units, signal definitions, thresholds, label construction, and population denominator.
- Assess Card: evaluates whether those records align with the intended IPC application, current context, IPC threshold logic, and population/20 percent compatibility.
- Calibrate: translates the assessed output into bounded analyst-facing interpretation rules, cross-checks, caveats, and non-use constraints.



