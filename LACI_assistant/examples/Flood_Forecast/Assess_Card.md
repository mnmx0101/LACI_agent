# LACI Assess Card v2 - Sample: AI Flood Forecasts

**Purpose:** This card supports Step 2 (Assess) of the LACI framework. It evaluates whether the AI flood forecast output is technically credible, IPC-relevant, and sufficiently documented for possible context-specific consideration.

**Sample status:** This is a full-fidelity sample card based on the current LACI Assess Card Template and the paper "AI Increases Global Access to Reliable Flood Forecasts." It is not an IPC decision record, not an IPC Technical Audit Record, and not an approval for use.

**Learn-to-Assess link:** This Assess Card follows the flood Learn Card typology assignment: **Contributing Factors / Environmental Hazard Forecasting; Forecasting; no food-security Special Rule unless transformed into food security outcome prediction.**

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
| **1. Data Quality** | Are variables, metadata, and source definitions clearly documented? | Yes | No baseline flag. | Paper defines streamflow target, return-period event evaluation, gauge data, GloFAS benchmark, lead times, and model architecture. |
| **1. Data Quality** | Is data cleaning and schema handling described? | Partly | Full operational preprocessing and current product pipeline should be reviewed before ingestion. | Paper describes research data, gauge matching, HydroBASINS linkage, and cross-validation design, but IPC integration would need product-version documentation. |
| **1. Data Quality** | Are outliers handled systematically and transparently? | Partly | Extreme-event handling and return-period estimation should be reviewed. | The model is evaluated over return-period events; detailed outlier and extreme-flow treatment should be checked in technical supplement/code. |
| **1. Data Quality** | Is missing data treatment documented and justified? | Partly | Ungauged and data-sparse basins remain central limitations. | Paper explicitly addresses prediction in ungauged basins and notes limited public streamflow gauge data globally. |
| **2. Missing Data & Harmonization** | Is missingness assessed across relevant splits or settings? | Yes | Local reliability still must be assessed for the target basin/country. | Cross-validation includes time/location splits and additional splits by terminal watersheds, climate zones, and continents. |
| **2. Missing Data & Harmonization** | Is spatial harmonization documented? | Partly | Basin-to-IPC-area translation is not covered and must be added for IPC use. | Paper discusses gauge/watershed mapping and GloFAS grid matching, but IPC use requires overlay with livelihoods, settlements, markets, cropland, and administrative areas. |
| **2. Missing Data & Harmonization** | Is temporal ordering enforced to avoid leakage? | Yes | Verify operational forecast timestamping before workflow use. | The forecast task is lead-time based through a 7-day horizon; metrics are calculated with streamflow gauge data from time periods not present in training. |
| **3. Model Design** | Is there an appropriate held-out test strategy? | Yes | No baseline flag. | Paper reports random k-fold cross-validation across 5,680 gauges and additional withheld-location experiments. |
| **3. Model Design** | Is hyperparameter tuning documented? | Unclear | Technical reviewer should inspect supplement/code. | Model architecture is described, but this sample did not verify all tuning procedures. |
| **3. Model Design** | Is class imbalance handled appropriately where relevant? | Partly | Rare extreme events require careful precision/recall interpretation. | Evaluation focuses on return-period events using precision, recall, and F1, but operational alert thresholds require separate review. |
| **3. Model Design** | Is feature selection documented or justified? | Partly | Current input availability and product-version features need review. | The paper describes hydrometeorological inputs and LSTM architecture; exact operational input pipeline requires verification. |
| **4. Evaluation Rigor** | Do the evaluation metrics match the prediction task? | Yes | No baseline flag. | Precision, recall, and F1 over return-period flood events fit flood early warning reliability. |
| **4. Evaluation Rigor** | Is the model compared against meaningful baselines? | Yes | No baseline flag. | The model is benchmarked against GloFAS version 4, a relevant global flood forecasting system. |
| **4. Evaluation Rigor** | Are subgroup or residual errors examined? | Yes | Carry regional/basin reliability into Part 2. | Paper reports continent-level reliability differences and discusses predicting reliability in ungauged basins. |
| **4. Evaluation Rigor** | Is uncertainty quantified? | Partly | User-facing uncertainty and local reliability communication require review. | The paper reports reliability/skill metrics and return-period performance, but IPC users need context-specific uncertainty and impact translation. |
| **5. Transparency** | Is code or implementation sufficiently available for review? | Partly | Verify current operational product and repository before ingestion. | Paper references open-source NeuralHydrology research implementation and open repositories; operational FloodHub code/version may differ. |
| **5. Transparency** | Is there a model card or equivalent technical documentation? | Yes | No baseline flag. | The paper provides substantial technical documentation; LACI card supplies IPC-specific assessment framing. |
| **5. Transparency** | Are limitations clearly stated? | Yes | Carry data and local reliability limits into Part 2. | Paper highlights ungauged basins, limited hydrological data availability, and location-based reliability differences. |
| **5. Transparency** | Can intended users understand how the output should and should not be used? | Partly | IPC translation flag: flood hazard does not directly equal food security impact. | FloodHub may be understandable for flood warning, but IPC use requires additional guidance connecting hazard to exposure, impact, and food-security relevance. |

### B. Minimum Requirements Checklist

> [!CAUTION]
> The model **fails** minimum requirements and should not be considered for IPC applications if any of the following critical flags apply. In this sample, none are marked as automatically failed for hazard monitoring, but IPC relevance requires a separate context-specific food-security transmission-pathway assessment.

| Minimum Requirement / Critical Flag | Sample Assessment | Rationale |
| :--- | :--- | :--- |
| **Data Quality Failure:** The model output, training target, or ground truth is fundamentally undefined or undocumented, making it impossible to know what the model is actually predicting. | Not triggered | Output and target are documented as streamflow / riverine flood events. |
| **Data Quality Failure:** Missing data treatment is entirely undocumented despite missingness being a known material issue in the input data. | Not triggered / partial flag | Ungauged basins are central to the paper; missing hydrological data remain a local reliability concern. |
| **Model Design Failure:** There is a clear, unaddressed risk of temporal leakage. | Not triggered / verify | Forecast lead times and time-based cross-validation are described; operational timestamping should be verified. |
| **Evaluation Rigor Failure:** There is no meaningful out-of-sample validation or testing strategy. | Not triggered | Cross-validation across gauges/time/location is a core part of the study. |
| **Transparency Failure:** There is absolutely no documentation of uncertainty, error bounds, or limitations. | Not triggered | Reliability metrics and limitations are reported, though IPC-facing uncertainty translation is needed. |
| **Transparency Failure:** There is no explanation provided for how end-users or analysts are supposed to interpret the output values. | Not triggered for flood warning / partial IPC flag | Flood warning interpretation is documented at a technical level; IPC use requires additional impact-pathway guidance. |
| **Misalignment Risk:** The output claims to represent a specific high-stakes outcome or hazard severity but lacks validation against established domain protocols or ground truth data. | Not triggered | The hazard target is validated against streamflow gauges and compared with GloFAS. |
| **Misalignment Risk:** The model is trained on proxy data but is presented as directly translating to the target phenomenon or IPC classification without sufficient evidence or calibration. | Potential IPC misuse risk | The model is not food-security proxy trained, but it could be misused if flood hazard is treated as food security severity without exposure/impact evidence. |

**Baseline conclusion:** The model-output passes baseline screening for moving into context-specific assessment as an environmental hazard forecast. It does not, by itself, pass as IPC food security evidence. IPC relevance depends on local exposure, vulnerability, and food-security transmission pathways.

---

## Part 2. Context-Specific Assessment and IPC Application Implications

*Part 2 evaluates whether the model-generated output is relevant and reliable for a specific operational context. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Assessment Context

| Field | User Entry |
| :--- | :--- |
| **Target Geography & Scale** | Basin, river reach, flood-prone livelihood zone, market catchment, settlement area, or administrative unit to be selected by IPC analysts. The source paper is global; this sample does not select a specific IPC country/cycle. |
| **Target Crisis Profile** | Riverine flood hazard that may affect food security through crop loss, asset loss, livestock movement, displacement, disease risk, market access, road access, or humanitarian assistance delivery. |
| **Time Horizon Assessed** | Short-term 1-7 day flood forecast; paper emphasizes reliable extreme-event forecasts up to 5 days for selected return periods. |
| **IPC Application / Working Analytical Function Under Review** | Risk Monitoring / Contextual Risk Monitoring; short-term Projection Analysis / Projection Assumption Tracking where flood impacts are plausible. Current Analysis Evidence Support is reviewed only to rule out direct use. |
| **Operational Context Status** | Illustrative sample based on published documentation. Not tied to a specific IPC cycle, basin, country team, or IPC-LACI Team technical audit. |
| **Food-Security Transmission Pathway** | Required before any IPC-facing consideration: flood hazard -> exposed people/assets/livelihoods -> food access/availability/utilization/stability impact -> IPC application. This pathway is not supplied by the flood model itself. |

### B. Performance Evidence, Localized Performance & Validation

*This section documents reported performance as a record, then interprets whether that performance supports the specific IPC application under review. Performance documentation is required even when the output is not suggested for IPC consideration.*

#### B1. Performance Record

| Performance Field | Response / Details |
| :--- | :--- |
| **Reported performance metric(s)** | Precision, recall, and F1 scores over return-period flood events and forecast lead times; comparisons with GloFAS version 4. |
| **Metric definition / interpretation** | Precision measures how many predicted flood events are true flood events. Recall measures how many true flood events are detected. F1 summarizes the precision/recall balance. Return-period thresholds represent event severity. |
| **Prediction task measured** | Daily streamflow and extreme riverine flood event forecasting through a 7-day horizon. |
| **Evaluation dataset / split** | 5,680 streamflow gauges, 1984-2021, with random k-fold cross-validation and additional splits by time, continents, climate zones, and terminal watersheds. |
| **Comparator or baseline** | GloFAS version 4, a global flood forecasting benchmark. |
| **Reported performance value(s)** | Paper reports AI performance similar to or better than GloFAS nowcasts up to 5-day lead time for selected return periods, and improved performance in many gauges/continents. Exact local values must be reviewed for the target basin. |
| **Performance variation by geography/context/subgroup** | Paper reports location-based differences in reliability, including continent-level differences and exceptions where Africa/Asia performance differences are not statistically significant for some return-period cases. |
| **Performance variation by prediction horizon** | Performance is reported across a 7-day forecast horizon; the strongest operational claim is reliability up to 5-day lead time for extreme events compared with GloFAS nowcasts. |
| **Performance variation by severity threshold/class** | Performance is evaluated over 1-, 2-, 5-, and 10-year return-period events. Interpretation depends on which threshold matters for the IPC context. |
| **Known failure modes** | Local basin reliability uncertainty, ungauged-basin uncertainty, flood type mismatch, hydrological infrastructure changes, exposure/vulnerability not modeled, and over-inference from hazard to food security impact. |
| **Source reference** | Source paper pages 1-5 for headline performance, GloFAS comparison, precision/recall/F1, return periods, lead times, and regional differences; methods section for 5,680 gauges and cross-validation. |

#### B1a. Performance Values Table

| Metric / Result | Reported Value | Model / Horizon / Threshold | Evaluation Context | Interpretation for Record | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Gauges where AI improved over GloFAS | 64% | 1-year return-period events; 0-day lead | Streamflow gauges; GloFAS v4 comparison | AI improves over GloFAS in a majority of gauges for 1-year events. | Source extraction lines 134-139 |
| Gauges where AI was at least equivalent to GloFAS | 65% | 1-year return-period events; 0-day lead | Same | Equivalent-or-better share is slightly higher than improved-only share. | Source extraction lines 134-139 |
| Gauges where AI improved over GloFAS | 70% | 2-year return-period events; 0-day lead | Same | Strong improvement share for 2-year events. | Source extraction lines 137-143 |
| Gauges where AI was at least equivalent to GloFAS | 73% | 2-year return-period events; 0-day lead | Same | AI is equivalent or better in nearly three-quarters of gauges for 2-year events. | Source extraction lines 137-143 |
| Gauges where AI improved over GloFAS | 60% | 5-year return-period events; 0-day lead | Same | Improvement remains positive for 5-year events. | Source extraction lines 137-139 |
| Gauges where AI was at least equivalent to GloFAS | 73% | 5-year return-period events; 0-day lead | Same | Equivalent-or-better performance remains high for 5-year events. | Source extraction lines 137-139 |
| Gauges where AI improved over GloFAS | 49% | 10-year return-period events; 0-day lead | Same | Improved-only share is below half for 10-year events, but equivalence share remains high. | Source extraction lines 137-139; full continuation in source figure/table should be verified |
| Gauges where AI was at least equivalent to GloFAS | 76% | 10-year return-period events; 0-day lead | Same | AI is at least equivalent in most gauges for 10-year events. | Source extraction lines 137-139; full continuation in source figure/table should be verified |
| Precision/recall comparison | Higher precision and recall for all return periods; N > 3,000; p < 1e-5 | Return-period events | AI vs GloFAS | Strong aggregate evidence that AI improves event-detection reliability across return periods. | Source extraction lines 151-158 |
| 5-year AI vs 1-year GloFAS precision | No significant difference at alpha 1%; N = 3,465; p = 0.02; d = -0.01 | 5-year AI events vs 1-year GloFAS events | Cross-severity comparison | AI 5-year-event precision is comparable to GloFAS 1-year-event precision. | Source extraction lines 155-157 |
| 5-year AI vs 1-year GloFAS recall | AI recall better; N = 3,586 | 5-year AI events vs 1-year GloFAS events | Cross-severity comparison | AI detects 5-year events better than GloFAS detects 1-year events by recall. | Source extraction lines 157-158 |
| Lead-time reliability | Better or not statistically different up to 5-day lead | 1-, 2-, 5-year return-period events | AI 5-day forecasts vs GloFAS 0-day nowcasts | Supports short-term risk monitoring up to 5 days, not longer-term IPC outcome inference. | Source extraction lines 172-178 |
| 1-year event, 5-day lead | AI significantly better; N = 2,415; p = 6e-6; d = 0.08 | AI 5-day vs GloFAS 0-day | Lead-time comparison | Statistically significant but small effect size. | Source extraction lines 174-176 |
| 2-year event, 5-day lead | No statistical difference; N = 2,162; p = 0.98; d = 2e-4 | AI 5-day vs GloFAS 0-day | Lead-time comparison | AI 5-day forecast is comparable to GloFAS nowcast. | Source extraction lines 176-177 |
| 5-year event, 5-day lead | No statistical difference; N = 1,298; p = 0.69; d = 0.025 | AI 5-day vs GloFAS 0-day | Lead-time comparison | AI 5-day forecast is comparable to GloFAS nowcast for severe events. | Source extraction lines 177-178 |
| Reliability-classifier predictability | 71% micro-averaged precision/recall for GloFAS; 73% for AI | Classifier predicting above/below-mean F1 in out-of-sample gauges | Reliability predictability | Local forecast reliability is only partly predictable, reinforcing need for basin-specific caution. | Source extraction lines 236-240 |

#### B1b. Baseline Performance Conclusion

The extracted performance values indicate strong baseline technical performance for riverine flood hazard forecasting. The AI model improves over or is at least equivalent to GloFAS in a majority of gauges across several return-period thresholds, and the paper reports better or statistically comparable F1 reliability up to a 5-day lead time for 1-, 2-, and 5-year return-period events. However, the same values also show that performance is threshold-, lead-time-, and location-dependent; for example, improvement over GloFAS is weaker for 10-year return-period events even though equivalence remains high, and local reliability is only partly predictable. Baseline performance is sufficient to proceed to context-specific assessment as a hazard/risk-monitoring signal, but it does not establish food-security impact. IPC relevance still requires basin-specific reliability review plus exposure, vulnerability, and food-security transmission-pathway evidence.

#### B2. Localized Performance & Validation

| Question | Response / Details |
| :--- | :--- |
| **Context-Specific Validation:** Has the model been explicitly tested and validated in this geography and crisis type? | Unknown for any specific IPC geography until selected. The paper provides broad global evaluation across gauges, continents, climates, and watersheds, but basin-specific reliability for an IPC context must be checked. |
| **Localized Error & Uncertainty:** How does the model perform here compared to its global baseline? | The paper shows location-based reliability differences. It reports strong average performance against GloFAS, but local reliability cannot be assumed from global averages. |
| **Relevance of the Target:** Is the model's training target an appropriate proxy for the intended phenomenon in this specific region? | It is appropriate for riverine flood hazard, not for food security outcomes. Relevance to IPC depends on whether riverine flooding is a plausible driver of acute food insecurity in the target area and time window. |
| **Uncertainty Communication:** Is the uncertainty of the output accurately communicated for this specific context? | Partly. The paper reports precision, recall, F1, return-period performance, and lead-time comparisons. IPC users would still need basin-specific reliability, flood exposure, likely impact severity, and uncertainty translated into plain operational guidance. |

#### B3. Performance Implications for IPC Application

| Question | Response / Details |
| :--- | :--- |
| **Does reported performance support the proposed IPC application?** | It supports contextual hazard monitoring where riverine flooding is relevant. It does not support food security classification or direct outcome inference. |
| **Does performance hold in this geography/context?** | Unknown until basin/geography is selected and local reliability is reviewed. |
| **Does performance hold at the needed prediction horizon?** | Best supported for short-term monitoring up to 5 days for extreme events, with 7-day forecasts requiring more caution. |
| **Are the weakest performance dimensions relevant to this IPC use?** | Yes. Missed floods, false alarms, and basin-specific reliability directly affect whether analysts should respond to a signal. |
| **What performance caveats must be carried into the Suggested Use Guide?** | Carry lead time, return-period threshold, local basin reliability, flood type, exposure/vulnerability, and non-use as food security evidence. |

### C. Contextual Limitations & Assumption Risks

| Question | Response / Details |
| :--- | :--- |
| **Data Dependency Risks:** Are the critical input data streams reliable, timely, and representative for this specific region? | Unknown until the operational context is selected. The model is designed partly for ungauged basins, but reliability varies with hydrological data availability, watershed characteristics, meteorological inputs, and local forecast skill. |
| **Assumption Violations:** What local conditions violate the model's core assumptions? | Flash flooding not captured by riverine streamflow, dam releases, levee failures, drainage changes, urban flooding, landslide-related floods, conflict-related access disruptions, or poor basin-to-community exposure mapping may weaken IPC relevance. The model predicts hazard, not exposure or impact. |
| **Vulnerable Subgroups:** Are there specific populations within this context that the model systematically misrepresents or excludes? | The model does not directly represent household vulnerability. Pastoralists, riverine farmers, informal settlements, IDPs, market-dependent households, isolated communities, and communities dependent on flood-recession agriculture may experience very different food-security impacts from the same flood hazard. |

### D. Reassessment Triggers

| Question | Response / Details |
| :--- | :--- |
| **Data Staleness:** Is the input data or ground-truth training data too old to reflect current realities in this context? | Reassessment is recommended if the operational product version has changed, if FloodHub coverage has changed, if new gauge or basin data become available, if local river engineering changes occurred, or if current meteorological inputs are delayed or unreliable. |
| **Shock Triggers:** What specific contextual shocks would immediately invalidate or weaken the model's assumptions here? | Major dam failure or release, levee breach, flash flood event outside riverine model scope, conflict-related access restriction, large displacement into floodplain areas, blocked transport corridors, crop calendar timing at planting/harvest, disease outbreak after flooding, market isolation, or assistance pipeline disruption. |

### E. IPC Application and Working Function Implications

| IPC Application / Working Analytical Function | Context-Specific Finding | Suggested Consideration | Supporting Rationale |
| :--- | :--- | :--- | :--- |
| **Current Analysis / Current Analysis Evidence Support** | The output forecasts flood hazard, not current food security conditions. | Not recommended for Current Analysis Evidence Support. | It does not measure food consumption, livelihood change, nutrition, mortality, market access, displacement impacts, or IPC severity. |
| **Projection Analysis / Projection Assumption Tracking** | Short-term flood forecasts may affect projection assumptions where flooding plausibly disrupts crops, markets, access, health, displacement, or assistance. | Suggested for consideration with documented limitation only where a food-security transmission pathway is specified. | Use as a prompt to revisit assumptions, not as direct evidence of food security deterioration. |
| **Risk Monitoring / Contextual Risk Monitoring** | Flood warnings can identify emerging hazards requiring analyst follow-up. | Consider only as contextual hazard/risk signal. | Strong fit for risk monitoring, but requires triangulation with exposure, vulnerability, and local impact evidence. |

---

## Part 3. Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs

*The current food-security Special Rule is not triggered because this model predicts riverine flood hazard and streamflow, not IPC phase, IPC-like food security severity, affected food-security populations, or FEWS NET/IPC food security labels.*

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **How do they define the outcome?** Is the target definition correct and aligned with IPC protocols? | The outcome is daily streamflow / riverine flood event occurrence over return-period thresholds. This is hydrological, not IPC. It can be relevant to IPC only through a separate food-security impact pathway. |
| **How is data merged?** How is historical IPC data consolidated and prepared alongside predictor data? | IPC data are not used. The model uses hydrological and meteorological inputs and streamflow gauge targets. Any merge with IPC-relevant data would need to happen downstream during context-specific assessment/calibration. |
| **Misinterpretation Risk:** Could the output be misinterpreted as a direct, endorsed IPC classification? | Low as a direct IPC-like output, but moderate as an operational misuse risk. Analysts may over-infer food security deterioration from a flood warning without exposure/impact evidence. |
| **Guardrails:** What prevents the output from replacing analyst-led consensus classification? | Required guardrails: label as flood hazard forecast only; require exposure/vulnerability overlays; require local impact triangulation; prohibit citation as IPC evidence or severity; document lead time, basin reliability, and flood type. |

**Special Rule conclusion:** The food-security proxy Special Rule does not apply. A hazard-model guardrail is needed: no IPC application should be suggested unless the local food-security transmission pathway is documented.

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
| **Suggested IPC Application(s) / Working Function(s)** | Suggested only for **Risk Monitoring / Contextual Risk Monitoring** and, where justified, short-term **Projection Analysis / Projection Assumption Tracking**. Not suggested for Current Analysis Evidence Support. | The model forecasts riverine flood hazard, which is an indirect driver, not a food security outcome. |
| **Suggested Consideration Guidance** | Use flood signals to trigger review of exposed populations, crop calendars, floodplain livelihoods, displacement risk, market/road access, WASH/disease risk, livestock movement, and assistance delivery constraints. | IPC relevance depends on hazard-to-impact-to-food-security translation. |
| **Performance Basis for Suggested Guidance** | Suggested consideration is based on precision/recall/F1 over return-period flood events, GloFAS comparison, and lead-time performance, with local basin reliability still required. | Performance supports contextual hazard monitoring only when a food-security transmission pathway is documented. |
| **Uncertainty & Risks** | Always document forecast lead time, return-period threshold, basin reliability, whether the flood type is riverine vs flash/urban/coastal, and whether the affected area overlaps food-security-relevant livelihoods or infrastructure. | Global skill does not guarantee local IPC relevance. Local exposure and vulnerability are not modeled. |
| **Strict Non-Use / Non-Communication Rules** | Do not cite as food security evidence, IPC severity evidence, IPC phase, or projected food insecurity outcome. Do not infer IPC impact without exposure/vulnerability and corroborating impact evidence. | These rules preserve the boundary between hazard monitoring and IPC analyst-led classification. |

### C. Inputs for Step 3: Calibrate

If IPC-GSU and IPC-LACI Team decide the output may proceed beyond Assess for a specific context, the following calibration requirements should be defined before any analyst-facing use:

| Calibration Need | Required Follow-Up |
| :--- | :--- |
| **Hazard threshold interpretation** | Define which return-period thresholds and lead times matter for the specific IPC workflow and geography. |
| **Food-security transmission pathway** | Document how the flood hazard could affect food availability, access, utilization, or stability in the specific context. |
| **Exposure overlay** | Overlay forecast basin/river reach with population, settlements, cropland, markets, roads, health/WASH facilities, displacement sites, and livelihood zones. |
| **Local reliability check** | Review basin-specific or regional forecast reliability, gauge availability, and whether the model is known to perform differently in the target area. |
| **Cross-check requirements** | Define required corroborating evidence before the hazard signal affects IPC discussion: flood reports, remote sensing inundation, field reports, market access, crop/livestock impacts, displacement, disease reports, and assistance access. |
| **Communication guardrails** | Define dashboard labels and footnotes: flood hazard forecast, not food security classification or IPC evidence. |
| **Reassessment schedule** | Reassess after model/product updates, major hydrological infrastructure changes, new local reliability evidence, major shocks, or IPC workflow changes. |








