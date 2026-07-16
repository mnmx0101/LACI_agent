# LACI Assess Card v2 - Sample: Acute Child Malnutrition Forecasting

**Purpose:** This card supports Step 2 (Assess) of the LACI framework. It evaluates whether the acute child malnutrition forecasting output is technically credible, AMN-relevant, and sufficiently documented for possible context-specific consideration.

**Sample status:** This is a full-fidelity sample card based on the current LACI Assess Card Template and the PNAS 2025 AMN forecasting paper. It is not an IPC AMN decision record, not an IPC Technical Audit Record, and not an approval for use.

**Learn-to-Assess link:** This Assess Card follows the AMN Learn Card typology assignment: **Outcome Indicator Model; AMN-relevant nutrition outcome forecasting; Forecasting; no current food-security Special Rule unless presented as IPC AMN classification support.**

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
| **1. Data Quality** | Are variables, metadata, and source definitions clearly documented? | Yes | No baseline flag. | Paper defines the target as ward/month U5 GAM prevalence generated from MUAC observations and describes secondary predictors. |
| **1. Data Quality** | Is data cleaning and schema handling described? | Partly | Full data pipeline should be reviewed before ingestion. | Paper describes MUAC-derived GAM construction and model families, but operational schema, exclusions, and data-processing code require IPC-LACI Team/model-builder review. |
| **1. Data Quality** | Are outliers handled systematically and transparently? | Unclear | Anthropometric outlier and implausible-value handling must be verified. | The sample review did not confirm a full outlier protocol for MUAC observations or secondary data streams. |
| **1. Data Quality** | Is missing data treatment documented and justified? | Partly | Missingness and continuity of sentinel-site data are central operational risks. | Paper discusses disruptions in data collection and sentinel-site changes; full missing-data treatment needs implementation review. |
| **2. Missing Data & Harmonization** | Is missingness assessed across relevant splits or settings? | Partly | Carry data-collection continuity into Part 2. | The paper discusses subperiods, including sentinel-site location change and changing autocorrelation/performance, but a deployment context needs its own missingness assessment. |
| **2. Missing Data & Harmonization** | Is spatial harmonization documented? | Partly | Ward/admin-boundary mapping and sentinel-site representativeness need review. | Output is ward-level; Kenya administrative changes and sentinel-site sampling are relevant to spatial interpretation. |
| **2. Missing Data & Harmonization** | Is temporal ordering enforced to avoid leakage? | Yes | Verify in code before workflow use. | Forecasts are explicitly evaluated at 1, 3, 6, 9, and 12 months ahead using out-of-sample prediction. |
| **3. Model Design** | Is there an appropriate held-out test strategy? | Yes | No baseline flag. | Paper reports out-of-sample performance over time and forecast horizons. |
| **3. Model Design** | Is hyperparameter tuning documented? | Unclear | Technical reviewer should inspect supplement/code. | The paper describes model comparisons, but this sample did not verify the full tuning protocol. |
| **3. Model Design** | Is class imbalance handled appropriately where relevant? | Yes | Precision tradeoff must be visible to analysts. | Paper discusses oversampling rare high-GAM episodes and notes that it boosts predictive skill only under adequate autocorrelation, with loss of precision. |
| **3. Model Design** | Is feature selection documented or justified? | Partly | Verify exact feature inclusion, timing, and availability. | Paper compares secondary-data, time-series-only, and hybrid models; the preferred hybrid model combines time-series and secondary predictors. |
| **4. Evaluation Rigor** | Do the evaluation metrics match the prediction task? | Yes | No baseline flag. | OOS R2 fits continuous prevalence forecasting; sensitivity, specificity, and precision fit high-GAM alert detection. |
| **4. Evaluation Rigor** | Is the model compared against meaningful baselines? | Yes | No baseline flag. | Paper compares secondary-data-only, time-series-only, and hybrid specifications, plus simple time-series/fixed-effect logic. |
| **4. Evaluation Rigor** | Are subgroup or residual errors examined? | Partly | Local subgroup and vulnerable-population error remain unresolved. | Paper examines performance across time subperiods and changing GAM dynamics, but does not provide a full IPC-style vulnerable-subgroup reliability assessment. |
| **4. Evaluation Rigor** | Is uncertainty quantified? | Partly | Forecast uncertainty needs operational expression. | Performance metrics are reported by horizon and period, but analyst-facing uncertainty intervals or confidence bands are not established in this sample. |
| **5. Transparency** | Is code or implementation sufficiently available for review? | Unclear | IPC-LACI Team/model-builder review required before ingestion. | This sample did not verify code, data access, or current operational implementation. |
| **5. Transparency** | Is there a model card or equivalent technical documentation? | Yes | No baseline flag. | The PNAS paper provides substantial technical documentation; LACI card supplies operational assessment framing. |
| **5. Transparency** | Are limitations clearly stated? | Yes | Carry limitations into Part 2. | Paper highlights performance variation over time, sentinel-site disruptions, autocorrelation dependence, and oversampling precision tradeoffs. |
| **5. Transparency** | Can intended users understand how the output should and should not be used? | Partly | AMN/IP C communication guardrails needed. | The paper is technically interpretable, but IPC-facing use requires clear explanation that forecast GAM is not IPC AMN classification. |

### B. Minimum Requirements Checklist

> [!CAUTION]
> The model **fails** minimum requirements and should not be considered for IPC applications if any of the following critical flags apply. In this sample, none are marked as automatically failed, but several require IPC-LACI Team and IPC AMN technical review before any IPC-facing consideration.

| Minimum Requirement / Critical Flag | Sample Assessment | Rationale |
| :--- | :--- | :--- |
| **Data Quality Failure:** The model output, training target, or ground truth is fundamentally undefined or undocumented, making it impossible to know what the model is actually predicting. | Not triggered | Target is documented as ward/month U5 GAM prevalence generated from MUAC observations. |
| **Data Quality Failure:** Missing data treatment is entirely undocumented despite missingness being a known material issue in the input data. | Not triggered / partial flag | Missingness and data-collection disruptions are discussed, but implementation details require review. |
| **Model Design Failure:** There is a clear, unaddressed risk of temporal leakage. | Not triggered / verify | Forecast horizons are explicit; IPC-LACI Team should verify timestamping and feature availability in implementation. |
| **Evaluation Rigor Failure:** There is no meaningful out-of-sample validation or testing strategy. | Not triggered | OOS evaluation is central to the paper. |
| **Transparency Failure:** There is absolutely no documentation of uncertainty, error bounds, or limitations. | Not triggered | Limitations and performance variation are described, though operational uncertainty communication needs work. |
| **Transparency Failure:** There is no explanation provided for how end-users or analysts are supposed to interpret the output values. | Not triggered / partial flag | GAM prevalence and alert threshold are interpretable, but IPC AMN use boundaries require guidance. |
| **Misalignment Risk:** The output claims to represent a specific high-stakes outcome or hazard severity but lacks validation against established domain protocols or ground truth data. | Not triggered / protocol caveat | It is validated against MUAC-derived GAM, but IPC AMN classification relevance would require IPC AMN protocol review. |
| **Misalignment Risk:** The model is trained on proxy data but is presented as directly translating to the target phenomenon or IPC classification without sufficient evidence or calibration. | Potential communication risk if misused | The model is not proxy-trained on IPC food security outcomes, but it could be over-presented as IPC AMN classification support. |

**Baseline conclusion:** The model-output passes baseline screening for moving into context-specific assessment as an AMN-relevant outcome indicator forecast. It should not proceed to IPC AMN-facing workflow use without IPC-LACI Team verification of implementation and IPC AMN technical review of evidence relevance.

---

## Part 2. Context-Specific Assessment and IPC Application Implications

*Part 2 evaluates whether the model-generated output is relevant and reliable for a specific operational context. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Assessment Context

| Field | User Entry |
| :--- | :--- |
| **Target Geography & Scale** | Kenya ASAL wards monitored through NDMA sentinel-site data in the source paper. Any use outside this setting requires a new context-specific assessment. |
| **Target Crisis Profile** | Drought-related food emergencies, acute child malnutrition, seasonal wasting dynamics, price and conflict stressors, and changing data-collection conditions. |
| **Time Horizon Assessed** | 1, 3, and 6 months are the main operationally meaningful horizons emphasized in the paper; 9 and 12 months are evaluated but weaker and require greater caution. |
| **IPC Application / Working Analytical Function Under Review** | Projection Analysis / nutrition assumption tracking; Risk Monitoring / nutrition risk monitoring. Current Analysis Evidence Support is reviewed only with strict caveats. |
| **Operational Context Status** | Illustrative sample based on published documentation. Not tied to a specific IPC AMN analysis cycle or formal IPC-LACI Team/GSU review. |

### B. Performance Evidence, Localized Performance & Validation

*This section documents reported performance as a record, then interprets whether that performance supports the specific IPC application under review. Performance documentation is required even when the output is not suggested for IPC consideration.*

#### B1. Performance Record

| Performance Field | Response / Details |
| :--- | :--- |
| **Reported performance metric(s)** | Out-of-sample R2 for continuous GAM prevalence forecasts; sensitivity, specificity, and precision for high-GAM alert cases. |
| **Metric definition / interpretation** | OOS R2 measures continuous forecast fit. Sensitivity measures the ability to detect high-GAM episodes and is especially important for early warning. Specificity measures correct identification of non-alert cases. Precision measures how many positive alerts are true positives and matters for resource allocation. |
| **Prediction task measured** | Ward/month U5 GAM prevalence forecasting and high-GAM alert detection. |
| **Evaluation dataset / split** | Kenya NDMA ASAL sentinel-site MUAC-derived ward/month GAM prevalence, January 2006 to December 2020, evaluated out of sample across 1, 3, 6, 9, and 12 month horizons. |
| **Comparator or baseline** | Secondary-data-only model, time-series-only model, hybrid model, and simple time-series / ward fixed-effects comparisons. |
| **Reported performance value(s)** | The paper reports OOS R2 by model and horizon, plus sensitivity/specificity/precision for 1-, 3-, and 6-month horizons. The hybrid model generally improves sensitivity at operational horizons but may reduce precision. |
| **Performance variation by geography/context/subgroup** | Performance is specific to Kenya ASAL wards and NDMA sentinel-site context. The paper emphasizes changes across time periods, including sentinel-site location changes and changes in GAM prevalence/autocorrelation. |
| **Performance variation by prediction horizon** | Performance declines as forecast horizon lengthens. The paper emphasizes 1, 3, and 6 months as more operationally meaningful than 9 and 12 months. |
| **Performance variation by severity threshold/class** | Alert evaluation uses a high-GAM threshold around 15 percent wasting prevalence. Rare high-GAM episodes create sensitivity/precision tradeoffs. |
| **Known failure modes** | Disrupted monitoring, sentinel-site changes, weak temporal autocorrelation, population movement, underrepresented vulnerable groups, and oversampling that boosts sensitivity at the cost of precision. |
| **Source reference** | Source paper pages 1-3 for monitoring data, target, horizons, and metrics; pages 3-6 for period/horizon performance; page 6 for preferred hybrid model; page 8 for operational maps. |

#### B1a. Performance Values Table

| Metric / Result | Reported Value | Model / Horizon | Evaluation Context | Interpretation for Record | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| OOS R2 | 0.39, 0.29, 0.19, 0.13, 0.12 | Secondary-data model; 1, 3, 6, 9, 12 months | Kenya NDMA ward/month GAM prevalence forecasting | Secondary data alone has useful but declining predictive power as horizon increases. | Source extraction lines 296-302 |
| OOS R2 | 0.53, 0.32, 0.23, 0.18, 0.15 | Time-series-only model; 1, 3, 6, 9, 12 months | Same | Exploiting GAM temporal autocorrelation improves short-horizon performance. | Source extraction lines 303-310 |
| OOS R2 | 0.53, 0.33, 0.23, 0.19, 0.15 | Hybrid model; 1, 3, 6, 9, 12 months | Same | Hybrid model performs similarly to time-series-only in OOS R2 while adding secondary-data signal. | Source extraction lines 310-314 |
| Sensitivity | 0.39, 0.29, 0.19 | Secondary-data model; 1, 3, 6 months | High-GAM alert detection | Detection of high-GAM episodes declines with horizon. | Source extraction lines 350-356 |
| Precision | 0.41, 0.32, 0.19 | Secondary-data model; 1, 3, 6 months | Same | Positive alerts become less reliable as horizon increases. | Source extraction lines 350-356 |
| Specificity | 0.97 to 0.99 | Secondary-data model; all considered horizons | Same | Non-alert cases are identified well, partly because high-GAM alerts are rare. | Source extraction lines 354-357 |
| Sensitivity | 0.48, 0.33, 0.20 | Time-series-only model; 1, 3, 6 months | High-GAM alert detection | Time-series-only improves sensitivity over secondary data alone at 1 month. | Source extraction lines 358-363 |
| Sensitivity | 0.53, 0.40, 0.33 | Hybrid model; 1, 3, 6 months | Same | Hybrid model has the strongest extracted sensitivity values, especially at 3 and 6 months. | Source extraction lines 360-363 |
| Precision | 0.54, 0.38, 0.23 | Time-series-only model; 1, 3, 6 months | Same | Time-series-only has higher precision than hybrid across extracted horizons. | Source extraction lines 360-363 |
| Precision | 0.51, 0.32, 0.18 | Hybrid model; 1, 3, 6 months | Same | Hybrid improves sensitivity but loses precision relative to time-series-only. | Source extraction lines 360-366 |
| Specificity | 0.97 to 0.99 | Time-series-only and hybrid models; all considered horizons | Same | Specificity remains very high across models/horizons. | Source extraction lines 363-366 |

#### B1b. Baseline Performance Conclusion

The extracted performance values show credible predictive skill for ward/month GAM prevalence, especially at shorter horizons and when the model uses time-series information. OOS R2 declines as the horizon extends from 1 to 12 months, which means the model is much stronger for near-term monitoring than for longer-range projection. For high-GAM alert detection, the hybrid model improves sensitivity relative to the secondary-data-only and time-series-only approaches at 1, 3, and 6 months, but it has lower precision than the time-series-only model. Specificity remains very high, partly because high-GAM alert cases are rare. Baseline performance is sufficient to proceed to context-specific assessment for nutrition risk monitoring and projection-assumption review, but the sensitivity/precision tradeoff, horizon decay, and sentinel-site dependence must be carried forward. The values do not support treating the output as IPC AMN classification or standalone current evidence.

#### B2. Localized Performance & Validation

| Question | Response / Details |
| :--- | :--- |
| **Context-Specific Validation:** Has the model been explicitly tested and validated in this geography and crisis type? | Yes for the Kenya NDMA ASAL setting represented in the paper. The model is trained and evaluated on NDMA sentinel-site MUAC-derived ward/month GAM prevalence from 2006-2020. |
| **Localized Error & Uncertainty:** How does the model perform here compared to its global baseline? | There is no global baseline. The relevant localized issue is time-period instability: performance varies by subperiod, especially around sentinel-site changes, GAM prevalence levels, and autocorrelation. |
| **Relevance of the Target:** Is the model's training target an appropriate proxy for the intended phenomenon in this specific region? | Yes for nutrition early warning and AMN-relevant risk monitoring, because the target is measured GAM prevalence from MUAC. It is not a proxy for IPC AMN classification unless separately calibrated and reviewed against IPC AMN protocols. |
| **Uncertainty Communication:** Is the uncertainty of the output accurately communicated for this specific context? | Partly. The paper reports OOS R2, sensitivity, specificity, and precision by horizon and period. Operational users would still need a simpler uncertainty display, especially for false positives, missed high-GAM episodes, and confidence in longer horizons. |

#### B3. Performance Implications for IPC Application

| Question | Response / Details |
| :--- | :--- |
| **Does reported performance support the proposed IPC application?** | It supports nutrition risk monitoring and projection-assumption review where high-frequency MUAC monitoring is comparable and current. It does not support direct IPC AMN classification. |
| **Does performance hold in this geography/context?** | It holds best for the Kenya NDMA ASAL monitoring context. Transfer to other countries or non-sentinel contexts requires new validation. |
| **Does performance hold at the needed prediction horizon?** | It is strongest at shorter horizons, especially 1 and 3 months, and more cautious at 6 months. Longer horizons require stronger caveats. |
| **Are the weakest performance dimensions relevant to this IPC use?** | Yes. Low precision can create unnecessary follow-up; low sensitivity can miss deteriorating areas; weak autocorrelation can degrade forecasts. |
| **What performance caveats must be carried into the Suggested Use Guide?** | Carry horizon-specific performance, sensitivity/precision tradeoff, sentinel-site continuity, representativeness, and IPC AMN protocol non-substitution. |

### C. Contextual Limitations & Assumption Risks

| Question | Response / Details |
| :--- | :--- |
| **Data Dependency Risks:** Are the critical input data streams reliable, timely, and representative for this specific region? | The model depends heavily on continuous high-frequency MUAC monitoring and stable sentinel-site sampling. Disruptions in data collection, changes in sentinel-site locations, COVID-era reporting changes, and gaps in secondary data can materially affect reliability. |
| **Assumption Violations:** What local conditions violate the model's core assumptions? | Model reliability may weaken if GAM temporal autocorrelation changes, if sentinel-site sampling changes, if population movement alters representativeness, if disease outbreaks or conflict shocks change malnutrition dynamics, or if secondary predictors are unavailable at forecast time. |
| **Vulnerable Subgroups:** Are there specific populations within this context that the model systematically misrepresents or excludes? | Unclear. The model works at ward/community scale using sentinel monitoring. It may underrepresent mobile pastoralists, newly displaced populations, hard-to-access settlements, urban/peri-urban poor, or groups not well covered by sentinel-site sampling. This requires local analyst review. |

### D. Reassessment Triggers

| Question | Response / Details |
| :--- | :--- |
| **Data Staleness:** Is the input data or ground-truth training data too old to reflect current realities in this context? | Reassessment is recommended if MUAC monitoring has not been updated in the current season/month, if sentinel-site locations or sampling protocols changed, if ward boundaries changed, or if model training has not incorporated recent drought, disease, conflict, displacement, or market shocks. |
| **Shock Triggers:** What specific contextual shocks would immediately invalidate or weaken the model's assumptions here? | Severe drought outside historical range; major disease outbreak affecting wasting; conflict or access shock disrupting monitoring; large displacement into/out of sentinel areas; major food price spike; assistance pipeline break; change in NDMA data collection method; major livelihood disruption affecting pastoral mobility or household food access. |

### E. IPC Application and Working Function Implications

| IPC Application / Working Analytical Function | Context-Specific Finding | Suggested Consideration | Supporting Rationale |
| :--- | :--- | :--- | :--- |
| **Current Analysis / Current Analysis Evidence Support** | Forecasted GAM prevalence is not observed current evidence. The underlying observed MUAC monitoring data may be relevant separately if it meets IPC AMN evidence standards. | Insufficient information / not recommended as model output alone. | IPC AMN current analysis requires observed evidence, protocol-compatible thresholds, data-quality review, and convergence with other evidence. A forecast should not replace this. |
| **Projection Analysis / Projection Assumption Tracking** | Forecasts may help identify areas where GAM prevalence is likely to deteriorate over the projection window, especially at 1-3 months and cautiously at 6 months. | Suggested for consideration with documented limitation. | The model can prompt review of nutrition assumptions, but performance varies by period and depends on current monitoring continuity and local validation. |
| **Risk Monitoring / Contextual Risk Monitoring** | High-GAM alert logic and monthly monitoring make this a plausible nutrition risk signal. | Consider only as contextual nutrition risk signal unless formally calibrated for IPC AMN workflow. | The model is strongest as early warning / attention allocation, not as classification or standalone IPC evidence. |

---

## Part 3. Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs

*The current food-security Special Rule is not triggered because this model predicts GAM prevalence, not IPC phase, IPC-like food security severity, affected food-security populations, or FEWS NET/IPC food security labels. However, this model is AMN-relevant and high-stakes. If it is proposed as IPC AMN classification support, an IPC AMN-specific review should be required.*

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **How do they define the outcome?** Is the target definition correct and aligned with IPC protocols? | The outcome is U5 GAM/wasting prevalence measured using MUAC, with GAM defined per WHO standards as MUAC less than 125 mm. This is nutrition-relevant, but IPC AMN classification alignment would need separate protocol review. |
| **How is data merged?** How is historical IPC data consolidated and prepared alongside predictor data? | IPC historical data are not the training target. The model merges MUAC-derived GAM prevalence with time-series and secondary predictors. Therefore this is not IPC outcome modeling or FEWS NET/IPC proxy-trained food security modeling. |
| **Misinterpretation Risk:** Could the output be misinterpreted as a direct, endorsed IPC classification? | Moderate if deployed poorly. Forecasted GAM prevalence or alert maps could be mistaken as IPC AMN classification support unless explicitly labeled as model-generated nutrition early warning. |
| **Guardrails:** What prevents the output from replacing analyst-led consensus classification? | Required guardrails: label as forecasted GAM only; prohibit use as IPC AMN classification without IPC AMN technical review; require observed nutrition data and convergence of evidence; document horizon-specific performance and local monitoring quality. |

**Special Rule conclusion:** The food-security proxy Special Rule does not apply, but an AMN-specific guardrail is needed before any IPC AMN-facing use.

---

## Part 4. Suggested Use Guide

*This section synthesizes Parts 1-3 into suggested-consideration guidance for downstream analysts and subsequent LACI steps. It does not approve use. It should make limitations, cross-checks, reassessment triggers, and strict non-use rules visible.*

### A. Suggested Context-Specific Consideration

Based on the baseline assessment and context-specific limitations, how should this model-generated output be considered?

- [ ] **Suggested for consideration as assessed:** No additional context-specific limitation identified.
- [X] **Suggested for consideration with documented limitation:** Output may be considered only with specific constraints noted in Part 2.
- [X] **Consider only as contextual risk signal:** Output should not be treated as direct evidence, but may prompt further investigation.
- [X] **Reassessment recommended before consideration:** Current context triggers from Part 2D require re-evaluating the model-output appropriateness for any real IPC AMN cycle.
- [ ] **Not recommended for this context:** Under current conditions, or due to initial exclusion in Part 1, the output is misleading or unsuitable.

### B. Suggested Use Guide for Analysts

| Operational Domain | Suggested Guidance / Instructions | Supporting Rationale |
| :--- | :--- | :--- |
| **Suggested IPC Application(s) / Working Function(s)** | Suggested only for **Risk Monitoring / nutrition risk monitoring** and **Projection Analysis / nutrition assumption tracking** in contexts with comparable high-frequency anthropometric monitoring. Not suggested as standalone Current Analysis Evidence Support. | The model forecasts a nutrition outcome indicator; it does not generate IPC AMN classification. |
| **Suggested Consideration Guidance** | Use forecasted high-GAM signals to prioritize analyst follow-up, review nutrition assumptions, check recent MUAC/survey evidence, and triangulate with disease, food access, market, conflict, displacement, assistance, WASH, and seasonal evidence. | The output can support attention allocation and assumption review, but should not replace observed nutrition evidence or IPC AMN protocols. |
| **Performance Basis for Suggested Guidance** | Suggested consideration is based on OOS R2 plus sensitivity/specificity/precision for GAM forecasting and alert detection, strongest at shorter horizons and dependent on sentinel-site continuity. | Performance supports nutrition risk monitoring and projection assumption review, not IPC AMN classification. |
| **Uncertainty & Risks** | Always document horizon, local monitoring continuity, sentinel-site representativeness, recent data-collection changes, autocorrelation conditions, and whether the model is overpredicting or missing high-GAM episodes in the current period. | The paper shows performance varies by horizon and period, and oversampling can improve sensitivity while reducing precision. |
| **Strict Non-Use / Non-Communication Rules** | Do not present forecasted GAM prevalence as IPC AMN classification. Do not use as standalone IPC evidence. Do not apply outside comparable data contexts without new validation. Do not communicate alert maps without caveats on forecast horizon, uncertainty, and monitoring coverage. | These rules preserve the boundary between model-generated early warning and IPC AMN analyst-led classification. |

### C. Inputs for Step 3: Calibrate

If IPC-GSU and IPC-LACI Team decide the output may proceed beyond Assess for a specific context, the following calibration requirements should be defined before any analyst-facing use:

| Calibration Need | Required Follow-Up |
| :--- | :--- |
| **Threshold interpretation** | Confirm whether the 15 percent high-GAM threshold, or another IPC AMN-relevant threshold, is appropriate for the operational context and communication purpose. |
| **Horizon-specific reliability** | Define which horizons are acceptable for analyst attention: likely 1 and 3 months first, 6 months with caution, and longer horizons only with strong caveats. |
| **Monitoring continuity** | Verify whether sentinel-site sampling, MUAC collection method, administrative geography, and data pipeline are stable enough for current use. |
| **Cross-check requirements** | Define required corroborating evidence before a model signal affects IPC discussion, including observed nutrition data, morbidity, food access, market, assistance, WASH, displacement, and field reports. |
| **Communication guardrails** | Define exact dashboard labels and non-use language: model-generated GAM forecast, not IPC AMN classification. |
| **Reassessment schedule** | Reassess after data-collection changes, major shocks, model updates, major performance drift, or IPC workflow changes. |








