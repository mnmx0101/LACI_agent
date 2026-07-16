# LACI IPC Analysis Use Checklist Template

**Audience:** IPC reviewer / decision-support.

## Verdict Badge Legend

| Badge | Label | Use |
| :--- | :--- | :--- |
| ![RED - Do Not Consider](https://img.shields.io/badge/RED-Do%20Not%20Consider-dc2626) | `RED - Do Not Consider` | Output is unsuitable for this context or fails required gates. |
| ![RED - Not Suggested](https://img.shields.io/badge/RED-Not%20Suggested-dc2626) | `RED - Not Suggested` | Output should not be suggested for this IPC application/function. |
| ![ORANGE - Reassess First](https://img.shields.io/badge/ORANGE-Reassess%20First-f97316) | `ORANGE - Reassess First` | Relevant but current conditions or operational metadata require review. |
| ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) | `YELLOW - Investigation Prompt` | Can help analysts decide where to look harder. |
| ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) | `BLUE - Contextual Supporting Information` | Can support contextual interpretation with documented limitations. |
| ![GREEN - Consider As Assessed](https://img.shields.io/badge/GREEN-Consider%20As%20Assessed-16a34a) | `GREEN - Consider As Assessed` | All gates pass for the defined use case. |
| ![GRAY - Not Applicable](https://img.shields.io/badge/GRAY-Not%20Applicable-6b7280) | `GRAY - Not Applicable` | Output does not apply to the proposed IPC application/function. |

## 1. Use Case Definition

A checklist cannot be completed until the user provides this use case definition.

- **Model Output / Run:** [Enter]
- **Operational Note:** [Link latest Operational Note]
- **IPC Application:** [Current Analysis / Projection Analysis / Risk Monitoring / other]
- **Working Function:** [e.g., Projection Assumption Tracking, Contextual Risk Monitoring]
- **Geography:** [Country, admin level, boundary system, target analysis area]
- **Time Window:** [IPC cycle, current/projection period, review window]
- **Intended Analyst Action:** [What analysts might do with the output]
- **Current Analysis Environment:** [Conflict/access, shocks, assistance changes, market disruption, source lags, epidemics, seasonality]
- **Decision Owner:** [IPC-GSU / country-regional analysts / IPC-LACI Team / authorized IPC process owner]

**Checklist Status:** [Complete / Preliminary - Use Case Incomplete / Preliminary - Operational Note Missing]

## 2. Context-Specific Limitation Match

| Review Item | Evidence / Performance | Current Use-Case Match | Implication | Decision Effect |
| :--- | :--- | :--- | :--- | :--- |
| **Best Reported Performance** | [Best metric value, metric name, measured task] | [How relevant to this use case] | [What use it supports] | [Verdict effect] |
| **Known Model Limitation** | [Evidence] | [Current condition] | [What it means] | [Proceed / downgrade / reassess / do not consider] |
| **Operational Note Status** | [Version, cut-off, source lags] | [Current review window] | [Freshness risk] | [Verdict effect] |
| **Spatial/Temporal Fit** | [Geography/time metadata] | [Use-case match] | [Fit or mismatch] | [Verdict effect] |
| **Threshold / Signal Meaning** | [Threshold type and interpretation] | [Use-case match] | [What it does and does not imply] | [Verdict effect] |
| **Population / 20 Percent Compatibility** | [Denominator and phase-disaggregation status] | [Use-case match] | [Population/area-phase implication] | [Verdict effect] |

## 3. Final Verdict

**Decision Badge:** [Select one badge from the legend]

**Decision Label:** `[RED / ORANGE / YELLOW / BLUE / GREEN / GRAY] - [Verdict]`

**Reasoning From Checklist**

- **Performance:** [Bullet]
- **Use-Case Fit:** [Bullet]
- **Known Limitation Triggered:** [Bullet]
- **Operational Note:** [Bullet]
- **Spatial/Temporal Fit:** [Bullet]
- **Threshold Meaning:** [Bullet]
- **Population Use:** [Bullet]
- **Overall:** [Bullet]

**Allowed**

- **Prioritize:** [Allowed action]
- **Triangulate:** [Allowed action]
- **Stress-Test:** [Allowed action]

**Not Allowed**

- **Classify:** Do not assign IPC phase from the model output.
- **Cite:** Do not cite as direct IPC evidence unless explicitly authorized through LACI and IPC process.
- **Estimate:** Do not use model exposure estimates as official IPC population estimates.





