# LACI Assess Card v2 - Sample: Yemen Data-Driven Early Detection Model

**Audience:** Decision-support preview for IPC/IPC-LACI Team/LACI reviewers. Partner-facing summaries should use documentation-status and clarification language rather than final-use verdict language.

**Purpose:** This card supports Step 2 (Assess) of the LACI framework. It evaluates whether the Yemen data-driven early warning output is technically credible, IPC-relevant, and sufficiently documented for possible context-specific consideration.

**Sample status:** This is a full-fidelity sample card based on the current LACI Assess Card Template and the earlier Yemen sample. It is not an IPC decision record, not an IPC Technical Audit Record, and not an approval for use.

**Learn-to-Assess link:** This Assess Card follows the Yemen Learn Card typology assignment: **IPC-Indicative Model; Proxy-Trained Food Security Output; Forecasting; Special Rule required.**

---

## Part 1. Baseline Model-Output Assessment (Technical Screening & Initial Exclusion)

*This section uses the full technical screening questions to identify whether the model-generated output should proceed to context-specific assessment. Screening questions are preserved and should not be removed, skipped, or weakened.*

### A. Technical Screening Questions

**Response format:**

- `Yes` = there is clear evidence that the issue has been addressed in a credible and reviewable way.
- `No` = there is a clear weakness, gap, or unresolved concern.
- `Unclear` = the available documentation is too limited to judge confidently.

> [!IMPORTANT]
> Any `No` or `Unclear` response generates a **Flag**. A flag does not automatically disqualify a model-generated output unless it violates Minimum Requirements, but it should be documented in the **Flag Point** column and carried into the Context-Specific Assessment.

| Screening Dimension | Screening Question | Response (Yes/No/Unclear) | Flag Point (If not addressed/considered) | Justification / Link |
| :--- | :--- | :--- | :--- | :--- |
| **1. Data Quality** | Are variables, metadata, and source definitions clearly documented? | Yes | No baseline flag. | The paper identifies FEWS NET IPC-compatible outcome data and indicator sources including food prices, fuel prices, exchange rates, drought, conflict, and displacement. |
| **1. Data Quality** | Is data cleaning and schema handling described? | Yes | Spatial and temporal transformations should still be inspected by IPC-LACI Team before ingestion. | FEWS NET livelihood-zone observations are mapped to districts; price and other indicators are transformed into alert/alarm-relevant signals. |
| **1. Data Quality** | Are outliers handled systematically and transparently? | Yes | Review exact implementation of smoothing/threshold rules before operational use. | The earlier Yemen sample records use of Exponential Moving Averages and Relative Strength Index style transformations to reduce noise and identify abnormal movements. |
| **1. Data Quality** | Is missing data treatment documented and justified? | Yes | Missingness remains an operational risk, especially where current data access is weak. | The earlier Yemen sample records machine-learning imputation for high-frequency price data and LOCF for IPC-compatible data gaps. |
| **2. Missing Data & Harmonization** | Is missingness assessed across relevant splits or settings? | Yes | Carry control-area and access-related missingness into Part 2. | The documentation acknowledges access constraints and evidence scarcity, including sensitivity around AA-controlled areas. |
| **2. Missing Data & Harmonization** | Is spatial harmonization documented? | Yes | Minor flag: livelihood-zone to district mapping introduces approximation error. | FEWS NET livelihood-zone data are harmonized to 333 districts using spatial overlay and population weighting in the previous sample. |
| **2. Missing Data & Harmonization** | Is temporal ordering enforced to avoid leakage? | Yes | IPC-LACI Team should verify the implementation reproduces this. | The model is designed to issue warnings before observed emergency transitions; previous sample notes warnings use information available at time t. |
| **3. Model Design** | Is there an appropriate held-out test strategy? | Yes | No baseline flag. | Historical validation focuses on transition cases where the prior rating is below emergency status and later moves to Phase 4+. |
| **3. Model Design** | Is hyperparameter tuning documented? | Yes | Threshold choices should be reviewed because they reflect operational tradeoffs. | Thresholds are optimized using false-negative and false-positive tradeoffs; alerts and alarms use different sensitivity/specificity emphases. |
| **3. Model Design** | Is class imbalance handled appropriately where relevant? | Yes | Tradeoff must be communicated to analysts. | Emergency transitions are relatively rare; the model distinguishes alerts and alarms to manage false-negative and false-positive priorities. |
| **3. Model Design** | Is feature selection documented or justified? | Yes | No baseline flag. | Recursive Feature Elimination and indicator-combination testing are reported in the source and previous sample. |
| **4. Evaluation Rigor** | Do the evaluation metrics match the prediction task? | Yes | No baseline flag. | Balanced accuracy, F1, false-positive/false-negative rates, and Brier-style metrics fit binary early warning of emergency transition. |
| **4. Evaluation Rigor** | Is the model compared against meaningful baselines? | Yes | No baseline flag. | The paper compares univariate indicators, combined indicator models, and GLM/logit specifications. |
| **4. Evaluation Rigor** | Are subgroup or residual errors examined? | Yes | Carry localized error differences into Part 2. | The previous sample records analysis across the IRG/AA divide and differences in inflation/drought relationships. |
| **4. Evaluation Rigor** | Is uncertainty quantified? | Yes | The uncertainty is threshold/tradeoff based, not a complete operational uncertainty envelope. | False-positive and false-negative tradeoffs are explicitly tracked through alert/alarm design. |
| **5. Transparency** | Is code or implementation sufficiently available for review? | Yes | IPC-LACI Team should verify the current repository, code version, and reproduction instructions before ingestion. | The previous sample records a reproducibility package; v2 treats this as requiring operational verification rather than assuming deployment readiness. |
| **5. Transparency** | Is there a model card or equivalent technical documentation? | Yes | No baseline flag. | The working paper is substantial technical documentation, and this LACI card provides the model-output assessment layer. |
| **5. Transparency** | Are limitations clearly stated? | Yes | Carry data-quality and changing-context limits into Part 2. | The paper notes intrinsic limits of data-driven approaches, dependency on data quality/availability, and need for continuous refinement. |
| **5. Transparency** | Can intended users understand how the output should and should not be used? | Unclear | Major communication flag: IPC-like and population-style outputs need strict guardrails. | Early warning framing is understandable, but Phase 4+ and population-style outputs can be overread as IPC classification or official population estimates. |

### A1. Spatial and Temporal Metadata Check

*This check uses the Yemen Learn Card spatial-temporal specification. It does not replace the 19 screening questions above; it makes spatial/temporal documentation visible before context-specific use decisions.*

| Metadata Check | Response (Yes/No/Unclear) | Flag Point / Required Follow-Up | Justification / Link |
| :--- | :--- | :--- | :--- |
| **Spatial unit is explicit:** native and reporting/output units are named. | Yes | Native source units are mixed; reporting output is district-level. | Learn Card records FEWS NET livelihood-zone outcomes harmonized to 333 Yemen districts, with other indicators originating from source-specific units. |
| **Spatial coding system is explicit:** GAUL, GADM, P-code, ISO, custom shapefile ID, raster grid, lat/lon, or other system is recorded. | Unclear | Operational use requires explicit boundary system and ID field. | The sample records district-level output but does not verify whether GAUL, GADM, OCHA P-code, or a custom district boundary is used. |
| **Spatial coding version or boundary date is recorded.** | No | Boundary vintage must be documented before ingestion. | The sample does not record boundary version/date. |
| **Aggregation/disaggregation or crosswalk method is documented.** | Yes | Crosswalk file should be reviewed by IPC-LACI Team. | The sample records livelihood-zone-to-district harmonization using spatial overlay and population weighting; operational crosswalk file is not attached. |
| **Temporal units are explicit:** input frequency, model update frequency, output time step, and prediction horizon are recorded. | Unclear | Exact input cadences and update schedule must be verified. | Training period and approximate 5-month horizon are documented, but live update cadence and source-specific daily/dekadal/monthly/irregular frequencies are not fully verified. |
| **Training, validation, model run, data cut-off, and latest-input dates are recorded where applicable.** | Unclear | Live use requires run date, data cut-off, and latest input date by source. | Historical coverage is October 2014-July 2023, but this demo does not identify a live output run or data vintage. |
| **Known spatial or temporal mismatch risks are documented.** | Yes | Carry into Part 2 and checklist. | Risks include livelihood-zone/district translation, AA/IRG differences, stale labels, horizon mismatch, and current shocks changing historical relationships. |
### B. Minimum Requirements Checklist

> [!CAUTION]
> The model-output **does not meet minimum requirements** for IPC-facing consideration if any of the following critical flags apply. In this sample, none are marked as automatically disqualifying, but several require IPC-LACI Team verification and context-specific review before any IPC-facing consideration.

| Minimum Requirement / Critical Flag | Sample Assessment | Rationale |
| :--- | :--- | :--- |
| **Data Quality Failure:** The model output, training target, or ground truth is fundamentally undefined or undocumented, making it impossible to know what the model is actually predicting. | Not triggered | The output and target are documented as emergency transition risk based on FEWS NET IPC-compatible outcomes. |
| **Data Quality Failure:** Missing data treatment is entirely undocumented despite missingness being a known material issue in the input data. | Not triggered | Missing-data handling is documented, though operational missingness remains a limitation. |
| **Model Design Failure:** There is a clear, unaddressed risk of temporal leakage. | Not triggered / verify | Forecasting design is intended to use prior information; IPC-LACI Team should verify code and data timestamping. |
| **Evaluation Rigor Failure:** There is no meaningful out-of-sample validation or testing strategy. | Not triggered | Historical validation and cross-validated balanced accuracy are reported. |
| **Transparency Failure:** There is absolutely no documentation of uncertainty, error bounds, or limitations. | Not triggered | Error tradeoffs and limitations are documented, though user-facing uncertainty needs strengthening. |
| **Transparency Failure:** There is no explanation provided for how end-users or analysts are supposed to interpret the output values. | Not triggered / partial flag | Alerts and alarms are interpretable, but population-style outputs need strict guidance. |
| **Misalignment Risk:** The output claims to represent a specific high-stakes outcome or hazard severity but lacks validation against established domain protocols or ground truth data. | Not triggered / sensitive | It is validated against FEWS NET IPC-compatible data, but that is still a proxy for IPC operational decision-making. |
| **Misalignment Risk:** The model is trained on proxy data but is presented as directly translating to the target phenomenon or IPC classification without sufficient evidence or calibration. | Potential communication risk | This is the main guardrail issue. The model must be presented as proxy-trained early warning, not as IPC classification. |

**Baseline conclusion:** The model-output passes baseline screening for moving into context-specific assessment, provided the Special Rule is applied and IPC-LACI Team verifies the current implementation, reproducibility package, and data-update process.

---

## Part 2. Context-Specific Assessment and IPC Application Implications

*Part 2 evaluates whether the model-generated output is relevant and reliable for a specific operational context. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Assessment Context

| Field | User Entry |
| :--- | :--- |
| **Target Geography & Scale** | Yemen, 333 districts. Where possible, interpretation should distinguish IRG-controlled and AA-controlled areas because economic and data-generating conditions differ. |
| **Target IPC Analysis Unit / Boundary System** | District-level review for the sample; exact IPC analysis area mapping and boundary system are not verified. GAUL/GADM/OCHA P-code/custom boundary version must be recorded for real use. |
| **Model Output Spatial Unit / Coding System** | District-level output for 333 Yemen districts. Coding system and boundary vintage are not confirmed in this sample. |
| **Spatial Crosswalk Required?** | Yes. FEWS NET livelihood-zone outcomes are harmonized to districts; operational use requires the crosswalk, method, and boundary version to be available for audit. |
| **Target Crisis Profile** | Protracted conflict, macroeconomic fragmentation, dual currency dynamics, high import dependence, displacement, market price shocks, drought, disrupted assistance, and access constraints. |
| **Time Horizon Assessed** | Early warning / projection-relevant monitoring. Existing LACI notes refer to a 5-month-ahead signal; implementation should confirm the exact horizon used for operational outputs. |
| **IPC Analysis Period / Review Window** | Not tied to a specific IPC cycle or review window in this sample. A live review must record the exact analysis period, season, or projection window. |
| **Model Output Temporal Unit / Cadence** | Not fully verified. Source inputs may be daily, dekadal/10-day, monthly, event-based, or irregular depending on source; live update cadence must be documented. |
| **Model Run Date / Data Cut-Off / Latest Input Date(s)** | Not available in this sample. Required before operational analyst use. |
| **IPC Application / Working Analytical Function Under Review** | Projection Analysis / Projection Assumption Tracking; Risk Monitoring / Contextual Risk Monitoring. Current Analysis Evidence Support is reviewed only to rule out direct use. |
| **Operational Context Status** | Illustrative sample based on published documentation and previous LACI Yemen review. Not tied to a specific IPC analysis cycle, analyst meeting, or formal IPC-LACI Team audit. |

### B. Performance Evidence, Localized Performance & Validation

*This section documents reported performance as a record, then interprets whether that performance supports the specific IPC application under review. Performance documentation is required even when the output is not suggested for IPC consideration.*

#### B1. Performance Record

| Performance Field | Response / Details |
| :--- | :--- |
| **Reported performance metric(s)** | Balanced accuracy, F1, false-positive rate, false-negative rate, Brier-style calibration measures, and alert/alarm threshold performance are reported or referenced in the paper and previous LACI Yemen sample. |
| **Metric definition / interpretation** | Balanced accuracy summarizes performance across imbalanced emergency/non-emergency classes. False-negative rate is critical for alerts because missed emergency transitions carry high operational risk. False-positive rate is critical for alarms because unnecessary escalation can misdirect scarce attention. |
| **Prediction task measured** | District-level early warning of transition into IPC-compatible emergency status, especially Phase 4 or 5, using observable indicators. |
| **Evaluation dataset / split** | Historical FEWS NET IPC-compatible district-level data for Yemen, October 2014 to July 2023, with validation focused on emergency transitions. |
| **Comparator or baseline** | Indicator-specific thresholds and combined GLM/logit model performance; recursive feature elimination used to test incremental indicator contribution. |
| **Reported performance value(s)** | The paper reports cross-validated balanced accuracy and indicator/model performance tables. Exact operational values should be carried into the final IPC technical audit from the source tables or implementation output. |
| **Performance variation by geography/context/subgroup** | The previous LACI Yemen review flags different relationships in IRG and AA areas: inflation/exchange-rate dynamics are more informative in IRG areas, while drought indicators carry more weight in AA areas. |
| **Performance variation by prediction horizon** | Existing LACI notes refer to a 5-month-ahead warning signal. The exact horizon-specific performance should be verified from implementation and source tables before operational use. |
| **Performance variation by severity threshold/class** | The model focuses on transition into Phase 4+ emergency status. Alert and alarm thresholds intentionally trade sensitivity against specificity. |
| **Known failure modes** | Sparse or stale FEWS NET outcome data, AA-area evidence constraints, post-COVID data staleness, shifts in currency/aid/conflict relationships, and overinterpretation of Phase 4+ or population-style outputs. |
| **Source reference** | Source paper pages 6-7 for target construction, pages 16-17 for GLM/RFE and cross-validated balanced accuracy, and previous Yemen LACI sample for alert/alarm interpretation. |

#### B1a. Performance Values Table

| Metric / Result | Reported Value | Model / Indicator / Threshold | Evaluation Context | Interpretation for Record | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Accuracy | 0.73 alert; 0.88 alarm | Food prices | Yemen emergency-transition warning; univariate risk indicator validation | Food price alarms are more conservative and more accurate than alerts, but alerts are designed for broader warning coverage. | Table 3, source extraction lines 573-587 |
| Balanced Accuracy | 0.70 alert; 0.61 alarm | Food prices | Same | Alert threshold is more balanced across classes; alarm threshold reduces false positives but misses more emergencies. | Table 3, lines 581-586 |
| F1 Score | 0.32 alert; 0.30 alarm | Food prices | Same | Modest F1 reflects difficult rare-event prediction and the alert/alarm tradeoff. | Table 3, line 583 |
| Precision | 0.21 alert; 0.34 alarm | Food prices | Same | Alarm improves precision relative to alert. | Table 3, line 584 |
| FPR / FNR | FPR 0.27 and FNR 0.33 for alert; FPR 0.05 and FNR 0.73 for alarm | Food prices | Same | Alarm strongly reduces false positives but substantially increases missed emergencies. | Table 3, lines 585-586 |
| Accuracy | 0.71 alert; 0.81 alarm | Fuel prices | Yemen emergency-transition warning; univariate validation | Fuel price alarms are more accurate than alerts and are described as more predictive for critical risks. | Table 3, lines 573-587 |
| Balanced Accuracy | 0.68 alert; 0.70 alarm | Fuel prices | Same | Fuel price alarm maintains balanced discrimination better than food price alarm. | Table 3, line 582 |
| FPR / FNR | FPR 0.28 and FNR 0.36 for alert; FPR 0.16 and FNR 0.45 for alarm | Fuel prices | Same | Fuel price alarms reduce false positives while retaining fewer missed emergencies than food price alarms. | Table 3, lines 585-587 |
| Accuracy | 0.64 alert; 0.80 alarm | Drought | Yemen emergency-transition warning; univariate validation | Drought alarms are more conservative and accurate than alerts but with weaker balanced accuracy. | Table 3, lines 588-600 |
| Balanced Accuracy | 0.62 alert; 0.57 alarm | Drought | Same | Indicates weaker class-balanced discrimination than key price indicators. | Table 3, line 597 |
| Brier score | 0.082; 0.074; 0.075 | Foundational GLM models (1)-(3) | Combined model validation | Lower Brier indicates better probabilistic calibration; model (2) has the lowest Brier among foundational GLMs. | Table 4, lines 723-727 |
| Pseudo R2 / Brier / Balanced Accuracy | Pseudo R2 0.698; Brier 0.057; Balanced Accuracy 0.824 | Model (8) with broader food-security dimensions/interactions | Final enhanced model described in text | Strongest extracted combined-model performance; should be verified against full table before audit. | Source extraction lines 869-874 |

#### B1b. Baseline Performance Conclusion

- **Overall Signal:** The Yemen model shows meaningful early-warning signal for emergency-transition risk, especially when indicators are combined.
- **Best-Supported Use:** Performance supports limited Risk Monitoring and Projection Assumption Tracking, not direct IPC evidence use.
- **Weakest Area:** Performance is uneven across indicators, thresholds, control areas, and periods with sparse or stale evidence.
- **Metric Caveat:** Heightened/alert-style thresholds reduce missed deteriorations but raise false positives; Critical/alarm-style thresholds reduce false positives but may miss emergencies.
- **Context Caveat:** Proxy-label dependence, AA/IRG differences, post-COVID shifts, and changing conflict/access dynamics must be checked in the current analysis environment.
- **Carry Forward:** Threshold tradeoffs, stale data, boundary mismatch, and proxy-label limitations must appear in the checklist and final verdict.
- **Not Supported:** Performance does not justify IPC classification, direct Current Analysis evidence, convergence by itself, area-phase reasoning, or official population estimates.

#### B2. Localized Performance & Validation

| Question | Response / Details |
| :--- | :--- |
| **Context-Specific Validation:** Has the model been explicitly tested and validated in this geography and crisis type? | Yes. Unlike a global model applied to Yemen after the fact, this model is Yemen-specific and is validated historically over 2014-2023 using Yemen district-level outcome and indicator data. |
| **Localized Error & Uncertainty:** How does the model perform here compared to its global baseline? | There is no global baseline because the model is Yemen-specific. The relevant localized issue is within-country heterogeneity: performance and indicator relevance differ across IRG and AA areas and across periods with different evidence access. |
| **Relevance of the Target:** Is the model's training target an appropriate proxy for the intended phenomenon in this specific region? | Partly yes, with strict caveat. FEWS NET IPC-compatible emergency transition is directly relevant to acute food insecurity early warning, but it is still a proxy-trained target and cannot be treated as current IPC consensus classification. |
| **Uncertainty Communication:** Is the uncertainty of the output accurately communicated for this specific context? | Partly. Alerts and alarms communicate a sensitivity/specificity tradeoff, but analysts still need clear information on false-positive risk, false-negative risk, data staleness, and whether the current district/context resembles validation conditions. |

#### B3. Performance Implications for IPC Application

| Question | Response / Details |
| :--- | :--- |
| **Does reported performance support the proposed IPC application?** | It supports cautious risk monitoring and projection-assumption review, not current classification evidence. |
| **Does performance hold in this geography/context?** | It is Yemen-specific, but within-Yemen performance and target reliability may not hold equally across control areas, access conditions, and recent periods. |
| **Does performance hold at the needed prediction horizon?** | The 5-month horizon may align with projection review, but final operational use should verify horizon-specific metrics. |
| **Are the weakest performance dimensions relevant to this IPC use?** | Yes. False negatives matter for missed deterioration; false positives matter for unnecessary escalation; proxy-label staleness matters for both. |
| **What performance caveats must be carried into the Suggested Use Guide?** | Carry threshold tradeoffs, AA/IRG differences, FEWS NET proxy-target limitations, data staleness, and non-use as official IPC evidence/population estimates. |

#### B4. Spatial and Temporal Fit for IPC Application

| Question | Response / Details |
| :--- | :--- |
| **Does the model output match the IPC analysis geography?** | Partly. District-level output is relevant for Yemen review, but the sample does not verify mapping to the exact IPC analysis areas used in any specific cycle. |
| **Are GAUL, GADM, P-code, ISO, raster grid, point, polygon, or custom units clearly recorded and compatible with IPC analysis units?** | No for operational use. The sample does not confirm GAUL/GADM/OCHA P-code/custom boundary version. This must be resolved before analyst-facing ingestion. |
| **Does the model output match the IPC analysis period or projection/review window?** | Not confirmed. The model is forecast-oriented and approximately 5-month-ahead in existing notes, but a live review must match the horizon to the IPC projection or monitoring window. |
| **Are model run date, data cut-off date, and latest input dates current enough for this use?** | Not confirmed. The sample does not include a live run date or source-by-source data vintage. |
| **Could spatial or temporal aggregation hide localized severity, shocks, or vulnerable groups?** | Yes. District aggregation and livelihood-zone crosswalks may hide inaccessible populations, IDPs, control-area differences, and recent shocks. |
| **What spatial/temporal caveats must be carried into the Suggested Use Guide?** | Analysts must document boundary system, crosswalk, output run date, data cut-off, latest input dates, horizon fit, stale/low-coverage districts, and any area/time mismatch before considering the output. |
### C. Contextual Limitations & Assumption Risks

| Question | Response / Details |
| :--- | :--- |
| **Data Dependency Risks:** Are the critical input data streams reliable, timely, and representative for this specific region? | Partly. Food prices, fuel prices, exchange rates, ACLED conflict data, displacement data, drought indicators, and FEWS NET IPC-compatible targets are relevant, but each may have timeliness, access, coverage, or measurement issues. AA-controlled areas and periods after COVID-19 require particular scrutiny because the previous sample flagged sparse or less variable ground-truth signals. |
| **Assumption Violations:** What local conditions violate the model's core assumptions? | Major changes in currency regimes, humanitarian assistance flows, import pipelines, conflict front lines, market access, displacement patterns, or survey/data collection access could break historical relationships. A shock that changes the relationship between food prices and access, or between drought and emergency transitions, should trigger reassessment. |
| **Vulnerable Subgroups:** Are there specific populations within this context that the model systematically misrepresents or excludes? | Unclear. The paper and previous sample evaluate spatial/political-economy distinctions more than demographic or livelihood subgroup performance. IDPs, marginalized livelihood groups, urban poor, pastoralists, and populations in inaccessible areas may not be adequately represented unless separate validation is conducted. |

#### C1. Known Limitation Handoff to Use Checklist

| Known Model Limitation | Checklist Comparison Required | Decision Implication If Triggered |
| :--- | :--- | :--- |
| **Conflict/access relationship shift:** Historical conflict/access relationships may not hold during major escalation, ceasefire collapse, new access restrictions, or control-area changes. | Compare current conflict/access conditions in the target IPC analysis area against model training/evaluation assumptions. | `TRIGGERED - Reassess` if conflict/access conditions are materially different or not represented in current input data. |
| **Source-data lag:** JMR metadata warns that source publication delays vary and data may not reflect all events up to cut-off. | Check latest input date by source for prices, exchange rates, displacement, rainfall, conflict, population, and food-security labels. | `TRIGGERED - Downgrade` if current decision period depends on lagged or stale sources. |
| **Boundary/version mismatch:** Method paper references 333 districts; JMR operational note records 335 Admin 2 areas. | Reconcile COD boundary version, Admin 2 unit list, crosswalks, and IPC analysis geography. | `UNKNOWN - Cannot rely` until boundary/crosswalk reconciliation is complete. |
| **Proxy-label target:** FEWS NET IPC-compatible labels are useful but do not reproduce IPC consensus classification. | Check whether analysts are treating JMR signals as direct IPC evidence, phase classification, or convergence. | `TRIGGERED - Downgrade` if the output is being interpreted beyond contextual risk/projection prompt use. |
| **Population exposure limits:** JMR population exposure estimates are model outputs and are not phase-disaggregated enough for IPC 20 percent reasoning in this demo. | Check denominator, phase disaggregation, uncertainty, and whether Phase 3+/Phase 4+/Phase 5 are separately available. | `TRIGGERED - Do Not Use For Population/Area Phase` unless IPC-compatible population logic is documented and reviewed. |
| **Unmodeled current shock:** Epidemic, abrupt aid suspension, port/import disruption, market closure, or sudden policy shock may change relationships not captured by the model. | Compare current analysis environment against model inputs and documented assumptions. | `TRIGGERED - Reassess` if the current driver is outside the model's documented signal set or historical relationships. |

### D. Reassessment Triggers

| Question | Response / Details |
| :--- | :--- |
| **Data Staleness:** Is the input data or ground-truth training data too old to reflect current realities in this context? | Reassessment is recommended if FEWS NET IPC-compatible outcome data, price data, exchange-rate data, displacement data, or conflict data are stale for the target districts or if the model has not been refreshed since major contextual shifts. The post-2020 period, AA-area evidence constraints, and any period with limited field access should be treated as high-scrutiny. |
| **Shock Triggers:** What specific contextual shocks would immediately invalidate or weaken the model's assumptions here? | Major currency or central-bank policy change; sudden port/import disruption; large-scale conflict escalation or ceasefire collapse; abrupt humanitarian assistance scale-up/scale-down; major displacement wave; severe drought outside historical range; major market closure; disease or epidemic shock affecting labor, access, or malnutrition; major change in FEWS NET/IPC data collection access. |

### E. IPC Application and Working Function Implications

| IPC Application / Working Analytical Function | Context-Specific Finding | Suggested Consideration | Supporting Rationale |
| :--- | :--- | :--- | :--- |
| **Current Analysis / Current Analysis Evidence Support** | The output forecasts emergency transition risk and may include Phase 4+ or population-style framing. This is not direct current evidence. | Not recommended for Current Analysis Evidence Support. | The output should not be treated as observed food consumption, livelihood change, nutrition, mortality, or official IPC classification evidence. |
| **Projection Analysis / Projection Assumption Tracking** | The output can identify districts where modeled deterioration risk conflicts with, supports, or raises questions about projection assumptions. | Suggested for consideration only as a projection-assumption prompt, with documented limitations. | Analysts may use alerts/alarms to revisit assumptions about price shocks, drought, conflict, displacement, assistance, and access. It should prompt triangulation, not substitute for convergence of evidence. |
| **Risk Monitoring / Contextual Risk Monitoring** | The alert/alarm structure is well aligned with monitoring emerging deterioration between IPC cycles. | Consider only as contextual risk signal. | The model can help prioritize follow-up review, especially where multiple indicators move together, but it remains proxy-trained and context-sensitive. |

---

## Part 3. Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs

*This section applies because the Yemen model is assigned as an IPC-Indicative Model and Proxy-Trained Food Security Output. The model uses FEWS NET IPC-compatible food security outcomes and may produce IPC-like emergency or population-style outputs.*

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **How do they define the outcome?** Is the target definition correct and aligned with IPC protocols? | The target is emergency transition, with IPC-compatible Phase 4 or 5 treated as emergency status and lower phases treated as non-emergency for the binary task. This is operationally meaningful for early warning, but it simplifies the full IPC analytical process and should not be interpreted as IPC classification. |
| **How is data merged?** How is historical IPC data consolidated and prepared alongside predictor data? | FEWS NET livelihood-zone outcomes are harmonized to Yemen districts and paired with indicator streams such as prices, exchange rates, drought, conflict, and displacement. This creates a usable historical modeling frame but introduces spatial approximation and target-proxy limitations. |
| **Threshold / signal interpretation:** What does each modeled threshold, anomaly, probability cutoff, class, alert, or outcome-trained label mean before IPC interpretation? | Alerts and alarms are model/indicator decision rules designed around sensitivity/specificity tradeoffs. Alert means broader potential emergency-transition warning with more false positives; alarm means narrower higher-confidence warning with more missed events. The Phase 4+ label is a historical FEWS NET IPC-compatible emergency-status proxy, not an IPC Reference Table threshold or direct IPC area-classification rule. |
| **IPC implication of threshold / signal:** What can the threshold or signal imply for IPC analysis, and what can it not imply? | The signal may imply that analysts should revisit projection assumptions or investigate contextual risk in flagged districts. It does not imply current IPC phase, IPC convergence, official IPC classification, official population estimates, or that the IPC 20 percent rule has been satisfied. |
| **Misinterpretation Risk:** Could the output be misinterpreted as a direct, endorsed IPC classification? | Yes. Any predicted Phase 4+ transition, emergency-risk score, alert/alarm, or modeled population-style output can be misread as official IPC classification or official IPC population estimates if not clearly labeled. |
| **Guardrails:** What prevents the output from replacing analyst-led consensus classification? | Required guardrails: label as modeled early warning only; keep IPC/FEWS-derived target provenance visible; prohibit external communication as IPC classification; require analyst triangulation; require IPC-LACI Team technical audit before operational workflow integration; include reassessment triggers for data staleness and context shifts. |

**Special Rule conclusion:** The model may be considered only as a proxy-trained early warning and contextual risk/projection prompt. It must not be represented as an IPC classification model, official IPC evidence stream, or official affected-population estimate.

---

## Part 4. Suggested Use Guide

*This section synthesizes Parts 1-3 into suggested-consideration guidance for downstream analysts and subsequent LACI steps. It does not approve use. It should make limitations, cross-checks, reassessment triggers, and strict non-use rules visible.*

### A. Suggested Context-Specific Consideration

Based on the baseline assessment and context-specific limitations, how should this model-generated output be considered?

- [ ] **Suggested for consideration as assessed:** No additional context-specific limitation identified.
- [X] **Suggested for consideration with documented limitation:** Output may be considered only with specific constraints noted in Part 2.
- [X] **Consider only as contextual risk signal:** Output should not be treated as direct evidence, but may prompt further investigation.
- [X] **Reassessment recommended before consideration:** Current context triggers from Part 2D require re-evaluating the model-output appropriateness for any real IPC cycle.
- [ ] **Not recommended for this context:** Under current conditions, or due to initial exclusion in Part 1, the output is misleading or unsuitable.

### B. Suggested Use Guide for Analysts

| Operational Domain | Suggested Guidance / Instructions | Supporting Rationale |
| :--- | :--- | :--- |
| **Suggested IPC Application(s) / Working Function(s)** | ![RED - Not Suggested](https://img.shields.io/badge/RED-Not%20Suggested-dc2626) `RED - Not Suggested` Current Analysis; ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) `YELLOW - Investigation Prompt` Projection Analysis / Projection Assumption Tracking; ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) `BLUE - Contextual Supporting Information` Risk Monitoring / Contextual Risk Monitoring. | The model is forecast-oriented and proxy-trained against FEWS NET IPC-compatible emergency transitions. |
| **Suggested Consideration Guidance** | Analysts may use Typical/Heightened/Critical signals to identify Admin 2 areas requiring closer review, compare modeled escalation risk against current projection assumptions, and prioritize triangulation with market, assistance, conflict, displacement, drought, nutrition, and field-access evidence. | The output can support attention allocation and assumption review, but not direct classification. |
| **Performance Basis for Suggested Guidance** | Suggested consideration is based on documented early-warning performance against FEWS NET IPC-compatible emergency transitions, with alert/alarm threshold tradeoffs and known AA/IRG differences. | Performance supports use only as a risk/projection prompt, not IPC evidence or population estimates. |
| **Operational Note and Spatial / Temporal Handling Rules** | The most recent operational note is required. Before analyst-facing use, record exact JMR extract, COD boundary version, livelihood-zone-to-Admin 2 crosswalk, model run/version, data cut-off, latest input date by source, threshold version, and horizon match to the IPC review window. Exclude or downgrade districts with stale, imputed, or unmapped inputs. | Spatial/temporal fit and operational currency are decisive for whether the output can support a specific IPC application. |
| **Uncertainty & Risks** | Always document whether the target district and period have reliable current input data, whether FEWS NET/IPC-compatible historical labels are adequate for that area, whether AA/IRG dynamics affect interpretation, and whether recent shocks have changed historical relationships. | The strongest risks are proxy-label dependence, data staleness, differential performance by control area, and misinterpretation of Phase 4+ or population-style outputs. |
| **Strict Non-Use / Non-Communication Rules** | Do not use as standalone evidence for Current Analysis. Do not communicate alerts, alarms, predicted Phase 4+ risk, or population-style outputs as official IPC classification, IPC population estimates, or IPC-endorsed severity. Do not use without context-specific review and IPC-LACI Team technical audit for operational workflow integration. | These non-use rules are required by the Special Rule and by the separation between model-output assessment and formal IPC decision-making. |

### C. Inputs for Step 3: Calibrate - Alignment and Translation Requirements

*This demo calibration section translates the Yemen Assess findings into bounded analyst-facing interpretation rules. It does not approve use and does not convert the model into IPC evidence or IPC classification.*

#### Gate 1. Spatial-Temporal Alignment

| Calibration Question | Yemen Demo Documentation / Decision |
| :--- | :--- |
| **IPC application and working analytical function being considered** | Projection Analysis / Projection Assumption Tracking and Risk Monitoring / Contextual Risk Monitoring. Current Analysis Evidence Support remains not suggested. These working functions may be revised as LACI is tested with TDT and IPC-LACI Team. |
| **IPC analysis unit and period** | Not specified for this demo. A real review must name the IPC analysis area/unit, boundary system, review period, and whether the output is being considered for current, projection, or inter-cycle monitoring. |
| **Model output unit and period** | Yemen district-level output for 333 districts; GAUL/GADM/P-code/custom boundary not verified. Historical training period is October 2014-July 2023. Existing notes refer to a 5-month-ahead signal; live run date, data cut-off, output cadence, and horizon must be recorded. |
| **Alignment decision** | Weakly aligned for demo purposes only. District-level Yemen output is relevant to IPC workflows, but boundary version, livelihood-zone-to-district crosswalk, model run date, data vintage, and horizon fit are not verified. |
| **Risk of hidden mismatch** | High enough to require safeguards. Livelihood-zone-to-district harmonization, AA/IRG control-area dynamics, inaccessible populations, IDPs, within-district variation, stale FEWS NET proxy labels, and changing shock relationships could hide localized severity or make the signal stale. |

#### Gate 2. Threshold / Signal Interpretation Alignment

| Calibration Question | Yemen Demo Documentation / Decision |
| :--- | :--- |
| **What is the model signal?** | District-level early-warning alert/alarm or emergency-transition risk signal based on prices, exchange rates, drought, conflict, displacement, and FEWS NET IPC-compatible historical food-security labels. |
| **What threshold or decision rule is applied?** | Alert/alarm thresholds selected around false-positive and false-negative tradeoffs. The outcome-trained/proxy target treats FEWS NET IPC-compatible Phase 4 or 5 as emergency status and lower phases as non-emergency. |
| **What does the threshold/signal mean in the source system?** | Alert = broader warning intended to catch more potential emergency transitions with higher sensitivity. Alarm = narrower warning intended to identify higher-confidence risk with fewer false positives. Phase 4+ target = historical proxy label for emergency-status transition, not an IPC Reference Table threshold used directly by analysts. |
| **What is the IPC-facing implication?** | Contextual risk signal and projection-assumption prompt only. A flagged district should trigger triangulation and assumption review; it should not be cited as direct IPC evidence. |
| **What does it not imply?** | It does not imply current IPC phase, IPC area classification, IPC convergence of evidence, official affected-population estimate, official IPC communication, or that the IPC 20 percent rule has been met. |
| **Calibration translation note** | Analysts may read an alert/alarm as: "This district warrants follow-up review of projection assumptions and current contextual evidence; confirm geography, data vintage, horizon fit, current shocks, and corroborating evidence before any analytical consideration." |

#### Gate 3. Population Estimate and 20 Percent Rule Compatibility

| Calibration Question | Yemen Demo Documentation / Decision |
| :--- | :--- |
| **Does the model estimate people, households, children, area phase, or affected population?** | The primary reviewed output is a district-period early-warning status/risk signal. The sample notes possible population-style or Phase 4+ outputs, but denominator, population vintage, and phase-disaggregated construction are not verified. |
| **Does the output provide phase-disaggregated or threshold-disaggregated shares/counts?** | Not verified. The sample target collapses historical FEWS NET IPC-compatible ratings into binary emergency/non-emergency status; it does not document Phase 3+, Phase 4+, Phase 5, or phase-specific population shares for current operational use. |
| **Can it support IPC 20 percent rule reasoning?** | No, not as currently documented. It may flag possible emergency-transition risk, but it cannot inform IPC area-phase reasoning unless denominator, population distribution, phase/threshold disaggregation, and method are documented and reviewed. |
| **Is Phase 3+ separated from Phase 4+?** | No for the documented proxy target. The model focuses on Phase 4 or 5 emergency status versus lower phases, and does not document the full phase distribution. Any Phase 3+ aggregate would be insufficient to infer Phase 4+ without separate Phase 4+ information. |
| **Population estimate limitations** | Do not use as official IPC population/caseload estimate. Before any population-style output is displayed, record denominator, population vintage, assistance assumptions, uncertainty, missing groups, and whether Phase 3+, Phase 4+, and Phase 5 are separately estimated. |
| **Calibration consequence** | Population/20 percent compatibility blocks any use for IPC population estimation or area-phase reasoning in this demo. The allowed role remains contextual risk signal / projection-assumption prompt only. |

#### Gate 4. Calibrated Analyst-Facing Output

| Calibration Output | Yemen Demo Required Wording |
| :--- | :--- |
| **Bounded role after calibration** | Investigation prompt for Projection Assumption Tracking and Contextual Risk Monitoring only, conditional on run-specific spatial, temporal, data-vintage, and IPC-LACI Team verification checks. |
| **Required cross-checks** | Compare with current market prices, exchange rates, assistance changes, conflict/access, displacement, drought/vegetation, food consumption/livelihood evidence, nutrition signals, field analyst knowledge, and any access/coverage caveats. |
| **Required caveat in analyst materials** | "This is a proxy-trained model alert/alarm based on historical FEWS NET IPC-compatible emergency-transition labels. It is not IPC classification, not direct IPC evidence, and not an official affected-population estimate." |
| **Strict non-use rule** | Do not use the output to classify areas, estimate official IPC populations, communicate IPC-endorsed severity, satisfy convergence of evidence, or infer Phase 4+ from a Phase 3+ aggregate or binary risk signal. |














