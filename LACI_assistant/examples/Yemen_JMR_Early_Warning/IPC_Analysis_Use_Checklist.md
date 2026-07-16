# IPC Analysis Use Checklist Result - Demo

**Audience:** IPC reviewer / decision-support.

**Model-output under review:** Yemen Joint Food Security Monitor / Data-Driven Early Detection Model.

**Source cards:** `Learn_Card.md`; `Assess_Card.md`.

**Operational note:** `Operational_Note.md`.

**Demo status:** Synthetic use case for testing the checklist format. This is not an IPC workflow decision.

## 1. Use Case Definition

- **Synthetic Use Case:** Review whether July 2026 JMR Yemen Admin 2 alerts can be considered during an IPC projection review for selected AA-controlled areas.
- **Model Output / Run:** JMR Yemen `YEM_2010-2025_JMR_v01_M`, version 2026-07-15, data cut-off 2026-07-15.
- **Operational Note:** Latest available JMR operational note is present, but exact extract, source-specific lags, and IPC-cycle matching still need reviewer confirmation before real use.
- **IPC Application:** Projection Analysis; Risk Monitoring.
- **Working Function:** Projection Assumption Tracking; Contextual Risk Monitoring. These analytical functions are working categories and may be revised as LACI is tested with TDT, IPC-LACI Team, and IPC workflows.
- **Geography:** Selected AA-controlled Admin 2 areas in Yemen. JMR reports COD Admin 2 coverage with 335 areas; the method paper refers to 333 districts. IPC geography, boundary vintage, and area crosswalk are not yet reconciled.
- **Time Window:** Synthetic IPC projection review using July 2026 JMR metadata. Exact IPC cycle, current-period window, and projection-period window are not specified.
- **Intended Analyst Action:** Use alerts only to identify areas where analysts should review current assumptions, seek corroborating evidence, or investigate possible deterioration.
- **Current Analysis Environment:** Conflict/access constraints, market disruption, displacement, source-data lags, and known AA-area evidence limitations. Current assistance changes, epidemic events, severe access deterioration, or other new shocks are not fully specified in this demo.
- **Decision Owner:** IPC-GSU / country-regional analysts, with IPC-LACI Team technical support. The authorized IPC process owner decides any workflow use.

**Checklist Status:** `Preliminary - Synthetic Use Case`.

## 2. Context-Specific Limitation Match

| Review Item | Evidence / Performance | Current Use-Case Match | Implication | Decision Effect |
| :--- | :--- | :--- | :--- | :--- |
| **Best Reported Performance** | Enhanced model reports balanced accuracy `0.824`, Brier score `0.057`, and pseudo R2 `0.698` for historical emergency-transition risk. | Relevant to attention-setting because the synthetic use case asks whether alerts should prompt analyst review. It is not sufficient for direct evidence use or area-phase reasoning. | Performance supports bounded investigation and projection-assumption review, not IPC classification, direct evidence weighting, or population estimates. | `Supports YELLOW - Investigation Prompt`. |
| **Threshold Tradeoff** | Food-price alert threshold reported balanced accuracy `0.70`; food-price alarm threshold reported balanced accuracy `0.61` and false negative rate `0.73`. | If analysts only attend to the strongest alarm category, deterioration may be missed. | Heightened/Critical signals should be read as prioritization prompts, not as severity categories equivalent to IPC phases. | `Keep Bounded`. |
| **AA-Controlled Area Reliability** | Assess Card documents concern that FEWS NET and other ground-truth evidence may be weaker, less variable, or more constrained in AA-controlled areas. | The synthetic use case is specifically for selected AA-controlled areas. | The current use case directly matches a known context-specific limitation. | `TRIGGERED - Downgrade`. |
| **Operational Note Freshness** | JMR version and data cut-off are documented as 2026-07-15, but source-specific update lags and the exact analyst extract are not verified here. | Projection review depends on recent conflict, access, price, assistance, displacement, and market conditions. | The output may lag the conditions analysts are trying to assess. | `TRIGGERED - Reassess Freshness`. |
| **Spatial / Boundary Fit** | JMR operational details indicate COD Admin 2 coverage with 335 areas; the method paper references 333 districts. | IPC analysis geography and boundary vintage are not reconciled in this demo. | Area matching may be incomplete or misleading if the crosswalk is not confirmed. | `TRIGGERED - Reassess Before Consideration`. |
| **Threshold / Signal Meaning** | JMR thresholds are model-derived alert/alarm signals. They are not IPC reference-table thresholds and do not implement IPC convergence of evidence. | The use case is bounded to monitoring and assumption review, not phase assignment. | Analysts may consider the signal only as a prompt to examine evidence; no model threshold substitutes IPC analysis. | `Allows Prompt-Only Handling`. |
| **Population / 20 Percent Compatibility** | JMR includes model-based population exposure estimates, but phase-disaggregated Phase 3+, Phase 4+, or Phase 5 population logic is not established for IPC 20 percent reasoning. | Any temptation to use exposure estimates for area phase or population counts would exceed the documented use case. | Model exposure estimates are not official IPC population estimates and cannot define area phase. | `Do Not Use For Population / Area Phase`. |
| **Unmodeled Current Shock** | Model features include prices, conflict, displacement, drought and other predictors, but unusual events may still be weakly captured or absent. | If current deterioration is driven by a new access shock, assistance change, port disruption, epidemic, or localized event not represented in the latest inputs, the signal may understate risk. | Current analysis environment must be checked against model inputs before any consideration. | `UNKNOWN - Cannot Rely Without Context Review`. |

## 3. Final Verdict

**Decision:** ![YELLOW - Investigation Prompt Only](https://img.shields.io/badge/YELLOW-Investigation%20Prompt%20Only-eab308) `YELLOW - Investigation Prompt Only`.

**Plain-language meaning:** For this synthetic use case, the JMR output may help analysts decide where to look more closely, but it should not be treated as direct IPC evidence or as a basis for IPC phase, population, or area classification decisions.

**Reasoning From Checklist**

- **Performance:** Reported model performance is strong enough to justify attention-setting, but the metrics evaluate historical emergency-transition prediction, not IPC phase assignment or official population estimation.
- **Use-Case Fit:** The proposed use is limited to Projection Assumption Tracking and Contextual Risk Monitoring, which is compatible with prompt-only handling.
- **Known Limitation Triggered:** The synthetic use case focuses on AA-controlled areas, where the Assess Card identifies reliability and ground-truth limitations.
- **Operational Note:** The operational note is present, but exact extract, source-specific lags, and IPC-cycle alignment still need confirmation.
- **Spatial / Temporal Fit:** Admin 2 boundary mismatch and IPC-cycle timing are unresolved.
- **Threshold Meaning:** JMR alert/alarm thresholds are not IPC reference-table thresholds and do not imply IPC phase severity.
- **Population Use:** Model exposure estimates do not satisfy IPC population-estimate or 20 percent area-phase logic.
- **Overall:** The model output can support investigation priorities only after analysts verify current conditions against known limitations.

**Allowed**

- **Prioritize:** Flag areas for closer review by IPC analysts.
- **Triangulate:** Compare alerts against market data, conflict/access evidence, displacement, assistance changes, nutrition/public-health signals, and analyst judgment.
- **Stress-Test:** Use disagreement between JMR output and analyst evidence to review projection assumptions.

**Not Allowed**

- **Classify:** Do not assign or imply IPC phase from the JMR output.
- **Cite:** Do not cite the output as direct IPC evidence unless a future LACI decision explicitly authorizes such use.
- **Estimate:** Do not use JMR exposure estimates as official IPC population estimates.
- **Override:** Do not use the model output to override IPC consensus-based convergence of evidence.


