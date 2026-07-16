# LACI Assess Card Template

**Purpose:** This card supports Step 2 (Assess) of the LACI framework. It unifies two distinct but sequentially related assessment functions:
- **Part 1 (Baseline Model-Output Assessment):** A technical screening of the underlying model-generated output to identify critical integrity problems, flag warning signs, and establish initial exclusion criteria. This baseline layer may be drafted by the model builder, data provider, and/or IPC-LACI Team technical reviewer.
- **Part 2 (Context-Specific Assessment):** An evaluation led by IPC-GSU, country/regional analysts, and IPC-LACI Team as needed to determine whether the output is relevant and reliable for a specific geography, time window, IPC cycle, shock context, and IPC application or working analytical function.

**General Operational Guide:**
- **When is this done?** This card is completed *after* the Learn step (Step 1) has mapped the initial typology, and *before* the output can proceed to the Calibrate (Step 3) and Integrate (Step 4) steps.
- **Who completes it?** Part 1 may be drafted by the model builder, data provider, and/or IPC-LACI Team technical reviewer. Part 2 is led by IPC-GSU, country/regional analysts, and IPC-LACI Team as needed. Part 4 is synthesized by IPC-GSU and/or IPC-LACI Team for downstream decision support.
- **What is the operational output?** The completed Assess Card provides the structured technical and context-specific assessment of a model-generated output. Its Part 4 Suggested Use Guide records suggested consideration pathways, limitations, cross-checks, and non-use constraints. Formal documentation-quality review is completed separately through the IPC Technical Audit Record.

---

## Part 1. Baseline Model-Output Assessment (Technical Screening & Initial Exclusion)

*This section uses the full technical screening questions to provide flagged points that indicate whether a model-generated output should proceed to context-specific assessment. A failure in the Minimum Requirements Checklist acts as an initial exclusion criterion. Screening questions should not be removed, skipped, or weakened.*

### A. Technical Screening Questions

*These questions are simplified operational readings of the fuller assessment metrics and are intended to support consistent flagging and documentation. This technical screening provides the evidence base for context-specific limitations and the minimum requirements checklist.*

**The function of this screening is to:**

- Identify technical warning signs
- Surface integrity problems
- Flag issues that may weaken trust, traceability, or later IPC use

**Response format:**

- `Yes` = there is clear evidence that the issue has been addressed in a credible and reviewable way
- `No` = there is a clear weakness, gap, or unresolved concern
- `Unclear` = the available documentation is too limited to judge confidently

> [!IMPORTANT]
> Any `No` or `Unclear` response generates a **Flag**. A flag does not automatically disqualify a model generated output (unless it violates Minimum Requirements), but it should be documented in the **Flag Point** column and carried into the Context-Specific Assessment.

| Screening Dimension                       | Screening Question                                                          | Response (Yes/No/Unclear) | Flag Point (If not addressed/considered) | Justification / Link |
| :---------------------------------------- | :-------------------------------------------------------------------------- | :------------------------ | :--------------------------------------- | :------------------- |
| **1. Data Quality**                 | Are variables, metadata, and source definitions clearly documented?         |                           |                                          |                      |
| **1. Data Quality**                 | Is data cleaning and schema handling described?                             |                           |                                          |                      |
| **1. Data Quality**                 | Are outliers handled systematically and transparently?                      |                           |                                          |                      |
| **1. Data Quality**                 | Is missing data treatment documented and justified?                         |                           |                                          |                      |
| **2. Missing Data & Harmonization** | Is missingness assessed across relevant splits or settings?                 |                           |                                          |                      |
| **2. Missing Data & Harmonization** | Is spatial harmonization documented?                                        |                           |                                          |                      |
| **2. Missing Data & Harmonization** | Is temporal ordering enforced to avoid leakage?                             |                           |                                          |                      |
| **3. Model Design**                 | Is there an appropriate held-out test strategy?                             |                           |                                          |                      |
| **3. Model Design**                 | Is hyperparameter tuning documented?                                        |                           |                                          |                      |
| **3. Model Design**                 | Is class imbalance handled appropriately where relevant?                    |                           |                                          |                      |
| **3. Model Design**                 | Is feature selection documented or justified?                               |                           |                                          |                      |
| **4. Evaluation Rigor**             | Do the evaluation metrics match the prediction task?                        |                           |                                          |                      |
| **4. Evaluation Rigor**             | Is the model compared against meaningful baselines?                         |                           |                                          |                      |
| **4. Evaluation Rigor**             | Are subgroup or residual errors examined?                                   |                           |                                          |                      |
| **4. Evaluation Rigor**             | Is uncertainty quantified?                                                  |                           |                                          |                      |
| **5. Transparency**                 | Is code or implementation sufficiently available for review?                |                           |                                          |                      |
| **5. Transparency**                 | Is there a model card or equivalent technical documentation?                |                           |                                          |                      |
| **5. Transparency**                 | Are limitations clearly stated?                                             |                           |                                          |                      |
| **5. Transparency**                 | Can intended users understand how the output should and should not be used? |                           |                                          |                      |

### A1. Spatial and Temporal Metadata Check

*Complete this check using the Learn Card's Spatial and Temporal Unit Specification. This does not replace the 19 baseline screening questions above; it records whether the output has enough spatial and temporal documentation for later IPC context-fit decisions.*

| Metadata Check | Response (Yes/No/Unclear) | Flag Point / Required Follow-Up | Justification / Link |
| :--- | :--- | :--- | :--- |
| **Spatial unit is explicit:** native and reporting/output units are named. | | | |
| **Spatial coding system is explicit:** GAUL, GADM, P-code, ISO, custom shapefile ID, raster grid, lat/lon, or other system is recorded. | | | |
| **Spatial coding version or boundary date is recorded.** | | | |
| **Aggregation/disaggregation or crosswalk method is documented.** | | | |
| **Temporal units are explicit:** input frequency, model update frequency, output time step, and prediction horizon are recorded. | | | |
| **Training, validation, model run, data cut-off, and latest-input dates are recorded where applicable.** | | | |
| **Known spatial or temporal mismatch risks are documented.** | | | |
### B. Minimum Requirements Checklist

> [!CAUTION]
> The model **fails** minimum requirements and should not be considered for IPC applications if any of the following critical flags apply. These points represent severe technical or conceptual flaws identified during the screening above.

- [ ] **Data Quality Failure:** The model output, training target, or ground truth is fundamentally undefined or undocumented, making it impossible to know what the model is actually predicting.
- [ ] **Data Quality Failure:** Missing data treatment is entirely undocumented despite missingness being a known material issue in the input data.
- [ ] **Data Quality Failure:** The output's spatial unit, temporal unit, coding system, or data vintage is undefined, making it impossible to determine whether the output matches the IPC geography or review window.
- [ ] **Model Design Failure:** There is a clear, unaddressed risk of temporal leakage (e.g., training data contains future information that would not be available in real-world forecasting).
- [ ] **Evaluation Rigor Failure:** There is no meaningful out-of-sample validation or testing strategy (e.g., the model is only evaluated on the data it was trained on).
- [ ] **Transparency Failure:** There is absolutely no documentation of uncertainty, error bounds, or limitations, making the output unsafe for high-stakes IPC decision-making.
- [ ] **Transparency Failure:** There is no explanation provided for how end-users or analysts are supposed to interpret the output values.
- [ ] **Misalignment Risk:** The output claims to represent a specific high-stakes outcome or hazard severity (e.g., direct IPC phases, acute malnutrition, extreme drought) but lacks validation against established domain protocols or ground truth data.
- [ ] **Misalignment Risk:** The model is trained on proxy data (e.g., NDVI for drought, or FEWS NET outcomes for food security) but is presented as directly translating to the target phenomenon or IPC classification without sufficient evidence or calibration.

---

## Part 2. Context-Specific Assessment and IPC Application Implications

*While Part 1 evaluates baseline technical soundness, Part 2 evaluates whether the model-generated output is relevant and reliable for a **specific operational context** (e.g., a specific country, region, IPC cycle, crisis type, season, or shock context). This section must directly inform whether the output should be suggested for consideration for specific IPC applications and working analytical functions. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Assessment Context

*Define the specific operational environment being evaluated. (Do not repeat the model's global characteristics from the Learn Card; specify the exact context under review).*

| Field                                 | User Entry                                             |
| :------------------------------------ | :----------------------------------------------------- |
| **Target Geography & Scale**          | [e.g., South Sudan, ADM2 level]                        |
| **Target IPC Analysis Unit / Boundary System** | [e.g., IPC analysis area, ADM2, district, livelihood zone; record GAUL/GADM/P-code/custom boundary version if applicable] |
| **Model Output Spatial Unit / Coding System** | [e.g., ADM2 with OCHA P-code, 0.25 degree grid, market point, basin polygon, custom district ID] |
| **Spatial Crosswalk Required?** | [Yes/No. If yes, link to crosswalk and summarize aggregation/disaggregation method] |
| **Target Crisis Profile**             | [e.g., Conflict-driven displacement, prolonged drought]|
| **Time Horizon Assessed**             | [e.g., Current monitoring, 3-month projection]         |
| **IPC Analysis Period / Review Window** | [Specific IPC cycle, analysis period, season, projection period, or monitoring window under review] |
| **Model Output Temporal Unit / Cadence** | [e.g., daily, dekadal/10-day, weekly, monthly, seasonal, annual, event-based] |
| **Model Run Date / Data Cut-Off / Latest Input Date(s)** | [Record output run date, data cut-off, and latest input date by key source where available] |
| **IPC Application / Working Analytical Function Under Review** | [e.g., Current Analysis / Current Analysis Evidence Support; Projection Analysis / Projection Assumption Tracking; Risk Monitoring / Contextual Risk Monitoring] |

### B. Performance Evidence, Localized Performance & Validation

*Document reported performance as a record, then interpret whether that performance supports the specific geography, time window, crisis profile, IPC application, and working analytical function under review. Performance documentation is required even if the output is ultimately not suggested for IPC consideration.*

#### B1. Performance Record

| Performance Field | Response / Details |
| :--- | :--- |
| **Reported performance metric(s)** | [List metrics reported by the model documentation, e.g., F1, precision, recall, sensitivity, specificity, balanced accuracy, OOS R2, RMSE, calibration error, Brier score] |
| **Metric definition / interpretation** | [Explain what each metric means in plain operational terms] |
| **Prediction task measured** | [Specify the task evaluated, e.g., phase/severity prediction, binary alert, prevalence forecast, flood event detection] |
| **Evaluation dataset / split** | [Describe test data, out-of-sample split, temporal split, spatial split, validation period, or benchmark dataset] |
| **Comparator or baseline** | [Describe baseline/comparator, e.g., expert forecast, naive time series, current operational system, no-text model, GloFAS] |
| **Reported performance value(s)** | [Record key values and source references; if not reported, state Not reported] |
| **Performance variation by geography/context/subgroup** | [Report variation by country, region, livelihood zone, basin, admin unit, population subgroup, crisis type, or season if available] |
| **Performance variation by prediction horizon** | [Report performance by horizon, e.g., 1 month vs 6 months, 3 months vs 12 months, 5-day vs 7-day] |
| **Performance variation by severity threshold/class** | [Report variation by class, threshold, return period, IPC phase, alert/alarm level, rare event, or high-severity category if available] |
| **Known failure modes** | [Summarize contexts where performance weakens or where the model is known to misclassify, overpredict, underpredict, or become unstable] |
| **Source reference** | [Page, table, figure, repository, model card, or documentation link] |

#### B1a. Performance Values Table

| Metric / Result | Reported Value | Model / Horizon / Threshold | Evaluation Context | Interpretation for Record | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [Metric name] | [Numeric value or Not reported] | [Model variant, horizon, threshold, class, region, subgroup, or severity level] | [Evaluation dataset/split and comparator if applicable] | [Plain-language interpretation of what this value does and does not show] | [Page/table/figure/repository/model card] |
| [Metric name] | [Numeric value or Not extracted yet] | [Model variant, horizon, threshold, class, region, subgroup, or severity level] | [Evaluation dataset/split and comparator if applicable] | [Plain-language interpretation] | [Source reference] |


#### B1b. Baseline Performance Conclusion

[Summarize what the performance values above mean before moving to localized/context-specific assessment. This should be a technical conclusion, not a use decision. State whether the values show meaningful signal, where performance is strongest, where it is weakest, which metric tradeoffs matter, whether performance varies by horizon/geography/subgroup/severity threshold, and what limitations must be carried into Parts 2B-2C and Part 4. Clearly state what the performance record does **not** support, such as direct IPC evidence use, official IPC classification, population estimates, or use outside the evaluated context.]

#### B2. Localized Performance & Validation

*Evaluate whether the model's reported performance holds up in this specific context.*

| Question | Response / Details |
| :--- | :--- |
| **Context-Specific Validation:** Has the model been explicitly tested and validated in this geography and crisis type? | |
| **Localized Error & Uncertainty:** How does the model perform here compared to its global or general baseline? | [Include context-specific metrics if available] |
| **Relevance of the Target:** Is the model's training target an appropriate proxy for the intended phenomenon (e.g., acute food insecurity, acute malnutrition, drought severity, flood hazard, market stress, displacement) in this specific region? | |
| **Uncertainty Communication:** Is the uncertainty of the output accurately communicated for this specific context? | |

#### B3. Performance Implications for IPC Application

*Translate the performance record and localized validation into implications for the specific IPC application and working analytical function under review.*

| Question | Response / Details |
| :--- | :--- |
| **Does reported performance support the proposed IPC application?** | [Explain whether the performance evidence is strong enough for the proposed application/function] |
| **Does performance hold in this geography/context?** | [Explain whether validation covers the target country, region, population, crisis profile, season, or shock context] |
| **Does performance hold at the needed prediction horizon?** | [Explain whether the model is reliable at the relevant current/projection/risk-monitoring time window] |
| **Are the weakest performance dimensions relevant to this IPC use?** | [Explain whether false positives, false negatives, rare-class weakness, subgroup errors, or calibration issues matter for this use] |
| **What performance caveats must be carried into the Suggested Use Guide?** | [List performance limitations that must appear in Part 4] |

#### B4. Spatial and Temporal Fit for IPC Application

*Determine whether the output's units, coding system, cadence, vintage, and horizon fit the specific IPC application and working analytical function under review.*

| Question | Response / Details |
| :--- | :--- |
| **Does the model output match the IPC analysis geography?** | [Explain exact match, mismatch, aggregation/disaggregation, or crosswalk requirement] |
| **Are GAUL, GADM, P-code, ISO, raster grid, point, polygon, or custom units clearly recorded and compatible with IPC analysis units?** | [Record coding system/version and any boundary mismatch] |
| **Does the model output match the IPC analysis period or projection/review window?** | [Explain time-step and horizon fit] |
| **Are model run date, data cut-off date, and latest input dates current enough for this use?** | [Identify stale inputs or missing vintage information] |
| **Could spatial or temporal aggregation hide localized severity, shocks, or vulnerable groups?** | [Explain where aggregation or cadence weakens use] |
| **What spatial/temporal caveats must be carried into the Suggested Use Guide?** | [List caveats for Part 4] |
### C. Contextual Limitations & Assumption Risks

*Identify the local conditions, data gaps, performance caveats, or assumption violations that weaken the output's reliability. This section should explain why the performance documented in Part 2B may or may not hold in the operational context.*

| Question | Response / Details |
| :--- | :--- |
| **Data Dependency Risks:** Are the critical input data streams (e.g., market prices, rainfall) reliable, timely, and representative for this specific region? | |
| **Assumption Violations:** What local conditions (e.g., border closures, informal markets, sudden displacement) violate the model's core assumptions? | |
| **Vulnerable Subgroups:** Are there specific populations (e.g., IDPs, pastoralists, riverine/coastal communities) within this context that the model systematically misrepresents or excludes? | |

### D. Reassessment Triggers

*Define the thresholds that require immediate re-evaluation of the output's appropriateness.*

| Question | Response / Details |
| :--- | :--- |
| **Data Staleness:** Is the input data or ground-truth training data too old to reflect current realities in this context? | [Enter date / frequency thresholds] |
| **Shock Triggers:** What specific contextual shocks (e.g., sudden conflict escalation, major currency devaluation) would immediately invalidate the model's assumptions here? | [List specific trigger events] |

### Visual Tag Legend

| Badge | Label | Use |
| :--- | :--- | :--- |
| ![RED - Do Not Consider](https://img.shields.io/badge/RED-Do%20Not%20Consider-dc2626) | `RED - Do Not Consider` | Output is unsuitable for this context or fails required gates. |
| ![RED - Not Suggested](https://img.shields.io/badge/RED-Not%20Suggested-dc2626) | `RED - Not Suggested` | Output should not be suggested for this IPC application/function. |
| ![ORANGE - Reassess First](https://img.shields.io/badge/ORANGE-Reassess%20First-f97316) | `ORANGE - Reassess First` | Relevant but current conditions or operational metadata require review. |
| ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) | `YELLOW - Investigation Prompt` | Can help analysts decide where to look harder. |
| ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) | `BLUE - Contextual Supporting Information` | Can support contextual interpretation with documented limitations. |
| ![GREEN - Consider As Assessed](https://img.shields.io/badge/GREEN-Consider%20As%20Assessed-16a34a) | `GREEN - Consider As Assessed` | All gates pass for the defined use case. |
| ![GRAY - Not Applicable](https://img.shields.io/badge/GRAY-Not%20Applicable-6b7280) | `GRAY - Not Applicable` | Output does not apply to the proposed IPC application/function. |
### E. IPC Application and Working Function Implications

*Translate the context-specific findings above into implications for each relevant IPC application and working analytical function. This table should make clear whether the output is suggested for consideration, should be downgraded, requires reassessment, or is not recommended in this specific context.*

| IPC Application / Working Analytical Function | Context-Specific Finding | Visual Tag | Suggested Consideration | Supporting Rationale |
| :--- | :--- | :--- | :--- | :--- |
| **Current Analysis / Current Analysis Evidence Support** | [Summarize relevance, validation, and current-context fit] | [Badge / label] | [Suggested for consideration / Not recommended / Insufficient information] | [Explain why] |
| **Projection Analysis / Projection Assumption Tracking** | [Summarize relevance, horizon fit, and assumption validity] | [Badge / label] | [Suggested for consideration with limitations / Reassessment recommended / Not recommended] | [Explain why] |
| **Risk Monitoring / Contextual Risk Monitoring** | [Summarize relevance for anomaly, deterioration, or emerging-risk monitoring] | [Badge / label] | [Consider only as contextual risk signal / Suggested for consideration with limitations / Not recommended] | [Explain why] |

---

## Part 3. Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained AFI/AMN Outputs

*Complete this section ONLY if the model falls under **IPC Outcome Modeling**, **IPC-Indicative Models**, or **Proxy-Trained Food Security / Acute Malnutrition Outputs**. Because these outputs can be interpreted as IPC-like evidence, IPC outcomes, AMN severity, affected-population estimates, or phase-like alerts, separate assessment and guardrails are needed.*

* **IPC Outcome Modeling:** Models that directly estimate IPC phase, IPC phase-like severity, affected populations, IPC-compatible outcome status, AMN phase-like severity, or official-looking caseload/population estimates. These outputs approximate IPC analytical outcomes and therefore require strict guardrails.
* **IPC-Indicative Models:** Models trained against IPC severity, IPC-compatible severity, IPC-like labels, AMN thresholds, FEWS NET labels, or related proxy labels to estimate or indicate potential phase, severity level, warning score, alert status, or deterioration risk. These outputs are indicative only and do not constitute IPC classification.
* **Protocol grounding:** AFI outputs must be read against the Food Security Analytical Framework and convergence of evidence logic. AMN outputs must be read against AMN outcome evidence, WHZ/MUAC distinctions, contributing factors, and convergence logic. Thresholds and reference tables guide IPC analysis; they do not mechanically convert model output into IPC classification.
* **Non-replacement premise:** No model output can replace consensus-based IPC classification or become the actual IPC outcome by itself. Assess only bounded support roles and misuse controls.

### A. AFI / AMN Protocol Fit

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **AFI, AMN, both, or neither?** Is the model output relevant to Acute Food Insecurity, Acute Malnutrition, both, or another hazard/driver? | |
| **Target definition:** Does the model estimate IPC phase, IPC-like severity, affected population, FEWS NET/IPC-compatible labels, GAM, WHZ, MUAC, caseload, contributing factors, or another proxy? | |
| **Outcome vs contributing factor:** Does the model distinguish outcome evidence from contributing factors, or does it collapse them into one score? | |
| **Convergence risk:** Could the output be mistaken for convergence of evidence when it is only one model, one indicator, or one threshold? What labeling or workflow controls are needed? | |
| **Threshold / signal interpretation:** What does each modeled threshold, anomaly, probability cutoff, class, alert, or outcome-trained label mean before IPC interpretation? Where applicable, is it an IPC Reference Table threshold, a non-IPC statistical rule (e.g., LTA - 2 SD), a model-internal cutoff, or a proxy/outcome-trained label? | |
| **IPC implication of threshold / signal:** What can the threshold or signal imply for IPC analysis (direct evidence, indirect evidence, contextual risk, projection assumption, or no IPC-facing implication), and what can it not imply? | |
| **AMN WHZ/MUAC handling, if relevant:** Does the model distinguish WHZ-based GAM, MUAC-based GAM, oedema, and caseload/population estimates? | |
| **AFI-AMN relationship, if relevant:** Is AFI used as a contributing factor for AMN rather than being treated as AMN classification, and is malnutrition/mortality used for AFI only when food consumption deficits plausibly explain it? | |
| **Geography and validity period:** Are GAUL/GADM/P-code/custom units, boundary version, unit of analysis, crosswalk, and validity period documented? | |

### B. Data, Labels, and Guardrails

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **How is data merged?** How is historical IPC, FEWS NET, AMN, nutrition, survey, administrative, or predictor data consolidated and prepared alongside model inputs? | |
| **Label provenance:** Are target labels official IPC, FEWS NET, IPC-compatible, survey-derived, model-derived, programme/caseload-derived, or another proxy? | |
| **Misinterpretation Risk:** Could the output be misinterpreted as a direct, endorsed IPC classification, AMN classification, famine warning, severity estimate, or official population/caseload estimate? | |
| **Bounded-role guardrails:** Since the output cannot replace IPC consensus classification, what exact bounded role, non-use rules, labels, access controls, and analyst-facing caveats prevent misuse as an IPC outcome? | |
| **Required analyst-facing wording:** What exact non-use statement must appear in the Suggested Use Guide and IPC Analysis Use Checklist? | |

---
## Part 4. Suggested Use Guide

*This section synthesizes Parts 1-3 into suggested-consideration guidance for downstream analysts and subsequent LACI steps. It does not approve use. It should make limitations, cross-checks, reassessment triggers, and strict non-use rules visible.*

### A. Suggested Context-Specific Consideration

Based on the baseline assessment and context-specific limitations, how should this model-generated output be considered? *(Select one or more)*:

- [ ] **Suggested for consideration as assessed:** No additional context-specific limitation identified.
- [ ] **Suggested for consideration with documented limitation:** Output may be considered only with specific constraints noted in Part 2.
- [ ] **Consider only as contextual risk signal:** Output should not be treated as direct evidence, but may prompt further investigation.
- [ ] **Reassessment recommended before consideration:** Current context triggers (from Part 2D) require re-evaluating the model-output appropriateness.
- [ ] **Not recommended for this context:** Under current conditions, or due to initial exclusion in Part 1, the output is misleading or unsuitable.

### B. Suggested Use Guide for Analysts
*This section translates the assessment findings into suggested consideration guidance. It maps the output against potential IPC applications and working analytical functions and provides inputs for **Step 3: Calibrate** if the output remains suitable for consideration.*

| Operational Domain | Suggested Guidance / Instructions | Supporting Rationale |
| :--- | :--- | :--- |
| **Suggested IPC Application(s) / Working Function(s)** | [Specify exact IPC application(s), working analytical function(s), and badge label(s), e.g., Risk Monitoring / Contextual Risk Monitoring with `BLUE - Contextual Supporting Information`] | [Narrative rationale derived from Part 2E] |
| **Suggested Consideration Guidance** | [Specify how analysts may consider the output in the current cycle] | [Narrative rationale based on baseline and context-specific assessment] |
| **Performance Basis for Suggested Guidance** | [Summarize the specific performance evidence and caveats that justify the suggested consideration level] | [Link back to Part 2B and Part 2C] |
| **Spatial / Temporal Handling Rules** | [Specify the exact geography, coding system, boundary version, output cadence, run date/data vintage requirements, and any crosswalk or exclusion rules analysts must apply] | [Link back to Part 2A and Part 2B4] |
| **Uncertainty & Risks** | [Specify how to account for uncertainty and known risks] | [Narrative rationale based on limitations/assumptions] |
| **Strict Non-Use / Non-Communication Rules** | [Specify what analysts must NOT do or communicate with this output] | [Narrative rationale based on initial exclusions or guardrails] |

### C. Inputs for Step 3: Calibrate - Alignment and Translation Requirements

*Complete this section only if the output remains suitable for some form of consideration. Step 3 Calibrate does not calibrate a model into an IPC outcome or approval. It translates the assessed model output into bounded, analyst-facing interpretation rules for a specific IPC application, geography, period, and function.*

#### Gate 1. Spatial-Temporal Alignment

| Calibration Question | Required Documentation / Decision |
| :--- | :--- |
| **IPC application and working analytical function being considered** | [Specify the IPC application and working analytical function. These are working categories and may be revised as LACI is tested with TDT and IPC-LACI Team.] |
| **IPC analysis unit and period** | [Record IPC analysis area/unit, geography system where known, current/projection/review period, and population reference period if relevant.] |
| **Model output unit and period** | [Carry forward from Learn: native/output spatial unit, coding system, boundary version, output time step, model run date, data cut-off, and prediction horizon.] |
| **Alignment decision** | [Aligned / aligned with transformation / weakly aligned / not aligned. Explain any crosswalk, aggregation, disaggregation, temporal interpolation, or exclusion rule.] |
| **Risk of hidden mismatch** | [State whether spatial or temporal handling could hide localized severity, shocks, vulnerable groups, or stale evidence.] |

#### Gate 2. Threshold / Signal Interpretation Alignment

| Calibration Question | Required Documentation / Decision |
| :--- | :--- |
| **What is the model signal?** | [Indicator value, anomaly, probability, class, severity score, risk score, predicted outcome, forecast category, alert, etc.] |
| **What threshold or decision rule is applied?** | [IPC Reference Table threshold where applicable; non-IPC statistical threshold such as LTA - 2 SD, percentile, z-score, return period, or anomaly band; model-internal probability cutoff/risk class; proxy-trained or outcome-trained label.] |
| **What does the threshold/signal mean in the source system?** | [Explain the native meaning and evidence basis before IPC interpretation.] |
| **What is the IPC-facing implication?** | [Direct evidence candidate / indirect evidence / contributing-factor signal / contextual risk signal / projection-assumption input / no IPC-facing implication. Explain why.] |
| **What does it not imply?** | [State limits explicitly, including whether it cannot imply IPC phase, official IPC classification, official population estimate, or convergence by itself.] |
| **Calibration translation note** | [Write the exact interpretation rule analysts should use, including caveats, cross-checks, and downgrade/non-use rules.] |

#### Gate 3. Population Estimate and 20 Percent Rule Compatibility

*Complete this gate for AFI outputs, IPC Outcome Modeling, affected-population outputs, phase-like outputs, or any model that may be interpreted as supporting area phase or population estimates. Skip or mark Not applicable for outputs that do not touch area phase, affected population, or AFI population distribution.*

| Calibration Question | Required Documentation / Decision |
| :--- | :--- |
| **Does the model estimate people, households, children, area phase, or affected population?** | [Specify unit and denominator.] |
| **Does the output provide phase-disaggregated or threshold-disaggregated shares/counts?** | [Record whether it separates Phase 3+, Phase 4+, Phase 5, phase-specific categories, or only provides a single risk score/aggregate.] |
| **Can it support IPC 20 percent rule reasoning?** | [State whether the output can inform, but not determine, whether the most severe phase affecting at least 20 percent of the relevant population/households is Phase 3, Phase 4, Phase 5, etc. Explain constraints.] |
| **Is Phase 3+ separated from Phase 4+?** | [If only Phase 3+ is available, state that Phase 4+ or more severe area-phase implications cannot be inferred from the aggregate alone.] |
| **Population estimate limitations** | [Record denominator, population vintage, assistance assumptions where relevant, uncertainty, missing groups, and whether estimates are unsuitable for official IPC population/caseload reporting.] |
| **Calibration consequence** | [Directly state whether population/20 percent compatibility supports bounded analytical consideration, requires triangulation, or blocks IPC-facing consideration.] |

#### Gate 4. Calibrated Analyst-Facing Output

| Calibration Output | Required Wording |
| :--- | :--- |
| **Bounded role after calibration** | [State the narrow role, such as contextual risk signal, projection-assumption prompt, indirect evidence candidate, or experimental monitoring only.] |
| **Required cross-checks** | [List IPC evidence, local analyst checks, survey/admin data, field reports, partner information, or other signals needed before consideration.] |
| **Required caveat in analyst materials** | [Exact text analysts should see.] |
| **Strict non-use rule** | [Exact text describing what the output must not be used for.] |





















