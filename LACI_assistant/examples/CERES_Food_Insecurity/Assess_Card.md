# LACI Assess Card v2 - Sample: CERES Probabilistic Early Warning System

**Purpose:** This card supports Step 2 (Assess) of the LACI framework. It evaluates whether the CERES model-generated output is technically credible, IPC-relevant, and sufficiently documented for possible context-specific consideration.

**Sample status:** This is a sample assessment based on `ceres.pdf`. It is not an IPC decision record, not an IPC Technical Audit Record, and not an approval for use.

**Learn-to-Assess link:** This Assess Card follows the CERES Learn Card typology assignment: **IPC Outcome Modeling / IPC-Indicative Model; Proxy-Trained Food Security Output; Forecasting; Special Rule required.**

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
| **1. Data Quality** | Are variables, metadata, and source definitions clearly documented? | Yes | No baseline documentation flag. | Paper lists six input streams: CHIRPS, MODIS NDVI, ACLED, IPC classifications, WFP FCS/rCSI, and FAO/WFP cereal price indices. |
| **1. Data Quality** | Is data cleaning and schema handling described? | Unclear | Documentation exists, but implementation should be inspected before any workflow use. | Paper describes typed adapters, 0.25 degree grid normalization, weekly cadence, interpolation/spatial join, and forward filling, but sample review did not verify code behavior. |
| **1. Data Quality** | Are outliers handled systematically and transparently? | Unclear | Stress-score and anomaly handling need technical review. | The paper describes z-scores, regional baselines, and convergence thresholds, but not a complete outlier governance protocol. |
| **1. Data Quality** | Is missing data treatment documented and justified? | Yes | Low-coverage outputs still require strong caution. | Regions with fewer than three of six signals are flagged low-coverage and get wider perturbation ranges; output is not suppressed. |
| **2. Missing Data & Harmonization** | Is missingness assessed across relevant splits or settings? | Unclear | Coverage varies by country and data stream, and split/context-specific missingness is not fully established. | Paper notes irregular IPC cadence and missing WFP survey data; low-coverage regions are logged per API response. |
| **2. Missing Data & Harmonization** | Is spatial harmonization documented? | Yes | Country-level output is too coarse for many IPC uses. | Inputs are normalized to grid and aggregated to ISO country output; Admin1 signals are internal but not exposed in primary output. |
| **2. Missing Data & Harmonization** | Is temporal ordering enforced to avoid leakage? | Unclear | Prospective archive is promising, but current validation is not prospective. | Live predictions are timestamped for T+90 verification, but back-validation cases are in-sample and coefficients were set with knowledge of events. |
| **3. Model Design** | Is there an appropriate held-out test strategy? | No | Major baseline flag. | Paper explicitly states back-validation is not a performance evaluation; held-out split AUC has a wide CI consistent with chance performance. |
| **3. Model Design** | Is hyperparameter tuning documented? | No | Coefficients are author-specified, not empirically estimated. | Full coefficients are provided, but they are initial author-specified values based on literature and an 87-record IPC transition set. |
| **3. Model Design** | Is class imbalance handled appropriately where relevant? | Unclear | Phase 5 and Phase 4+ rare-event treatment is not yet empirically demonstrated. | Paper uses thresholds and monotonicity constraints; prospective precision/recall is planned but not yet available. |
| **3. Model Design** | Is feature selection documented or justified? | Unclear | Feature weights require independent review. | Six signals and weights are documented, but weights are author-specified and not derived from held-out validation. |
| **4. Evaluation Rigor** | Do the evaluation metrics match the prediction task? | Yes | Metrics are appropriate, but many are future commitments. | Brier, Brier Skill Score, CRPS, precision/recall, interval coverage, and reliability diagrams are appropriate for probabilistic forecasts. |
| **4. Evaluation Rigor** | Is the model compared against meaningful baselines? | No | Comparisons are in-sample only. | Paper compares in-sample Brier scores against persistence, climatology, and uninformative baselines, but says not to treat as prospective performance. |
| **4. Evaluation Rigor** | Are subgroup or residual errors examined? | No | Major flag for IPC use. | No prospective subgroup/country/regional error analysis is available in the paper. |
| **4. Evaluation Rigor** | Is uncertainty quantified? | Yes | Uncertainty is quantified, but it is under-specified and explicitly underestimated. | Sensitivity intervals are input-perturbation intervals, not posterior predictive intervals; paper says they underestimate true uncertainty. |
| **5. Transparency** | Is code or implementation sufficiently available for review? | Yes | Repository/API should be independently inspected. | Paper lists GitHub, API, archive, OpenAPI docs, and coefficients. |
| **5. Transparency** | Is there a model card or equivalent technical documentation? | Yes | No documentation flag. | The paper is substantial documentation and includes coefficients, limitations, API examples, and prospective evaluation protocol. |
| **5. Transparency** | Are limitations clearly stated? | Yes | Limitations are severe and must drive the conclusion. | Paper explicitly notes author-specified coefficients, lack of prospective validation, single-author design, underestimated uncertainty, data gaps, and country-level output. |
| **5. Transparency** | Can intended users understand how the output should and should not be used? | Unclear | IPC-like outputs create major misinterpretation risk. | Paper says CERES is not a replacement for IPC/FEWS NET/WFP systems, but probabilities of IPC phases can easily be overread. |

### B. Minimum Requirements Checklist

> [!CAUTION]
> The model **fails** minimum requirements and should not be considered for IPC applications if any of the following critical flags apply. In this sample, several critical flags are triggered for IPC-facing consideration, although the system may still be useful as an experimental tracking object.

| Minimum Requirement / Critical Flag | Sample Assessment | Rationale |
| :--- | :--- | :--- |
| **Data Quality Failure:** The model output, training target, or ground truth is fundamentally undefined or undocumented. | Not triggered | Output and target are clearly defined as IPC 3+/4+/5 probabilities at 90 days. |
| **Data Quality Failure:** Missing data treatment is entirely undocumented despite missingness being material. | Not triggered / partial flag | Missingness handling is documented, but low-coverage output remains risky. |
| **Model Design Failure:** There is a clear, unaddressed risk of temporal leakage. | Potentially triggered for current evidence | Prospective production is timestamped, but current performance evidence relies on in-sample cases selected with knowledge of events. |
| **Evaluation Rigor Failure:** There is no meaningful out-of-sample validation or testing strategy. | Triggered for IPC-facing use | The paper does not yet provide sufficient prospective or robust held-out validation for operational IPC consideration. |
| **Transparency Failure:** There is absolutely no documentation of uncertainty, error bounds, or limitations. | Not triggered | Limitations are clearly documented. |
| **Transparency Failure:** There is no explanation for how users interpret output values. | Not triggered / communication flag | Tiers and probabilities are described, but IPC-like interpretation risk remains high. |
| **Misalignment Risk:** The output claims to represent a high-stakes outcome but lacks validation against established domain protocols or ground truth. | Triggered for operational consideration | It directly estimates IPC-like outcomes without demonstrated prospective calibration. |
| **Misalignment Risk:** The model is trained on proxy data but is presented as directly translating to target phenomenon or IPC classification without sufficient evidence or calibration. | Triggered as communication risk | CERES uses IPC outcomes and current/projected IPC as inputs/targets, but calibration is explicitly not demonstrated yet. |

**Baseline conclusion:** CERES is transparent and architecturally interesting, but it should **not** proceed as an IPC-considerable evidence source at this stage. It may proceed only as an experimental object for monitoring, audit, and prospective performance tracking. No analyst-facing IPC workflow should treat CERES probabilities or tiers as evidence, classification support, or population/severity estimates until enough prospective verification accumulates and independent technical review is completed.

---

## Part 2. Context-Specific Assessment and IPC Application Implications

*Part 2 evaluates whether the model-generated output is relevant and reliable for a specific operational context. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Assessment Context

| Field | User Entry |
| :--- | :--- |
| **Target Geography & Scale** | Generic CERES monitored countries; no specific IPC country/cycle selected in this sample. Output is country-level ISO, with Admin1 signals not exposed in primary output. |
| **Target Crisis Profile** | Acute food insecurity / famine early warning using conflict, drought/vegetation, food access, prices, and IPC stress indicators. |
| **Time Horizon Assessed** | 90-day ahead forecast, updated weekly. |
| **IPC Application / Working Analytical Function Under Review** | Experimental Risk Monitoring only. Current Analysis and Projection Analysis are reviewed mainly to rule out direct consideration. |
| **Operational Context Status** | Illustrative sample based on PDF. Not tied to a real IPC cycle, country team, or IPC-LACI Team technical audit. |

### B. Performance Evidence, Localized Performance & Validation

*This section documents reported performance as a record, then interprets whether that performance supports the specific geography, time window, crisis profile, IPC application, and working analytical function under review. Performance documentation is required even if the output is ultimately not suggested for IPC consideration.*

#### B1. Performance Record

| Performance Field | Response / Details |
| :--- | :--- |
| **Reported performance metric(s)** | In-sample Brier Score, in-sample back-validation tier correctness, coefficient sensitivity tier stability, small held-out AUC, and planned prospective metrics: Brier, Brier Skill Score, TIER-1 precision/recall, interval coverage, CRPS, reliability diagrams. |
| **Metric definition / interpretation** | Brier measures squared probability error; AUC measures discrimination; precision/recall will assess TIER-1 alerts; CRPS will assess full ordered phase distributions. |
| **Prediction task measured** | 90-day probability of IPC Phase 3+, Phase 4+, and Phase 5; TIER alert classification. |
| **Evaluation dataset / split** | Four in-sample historical Phase 4-5 cases selected for completeness; 87 IPC transition records for coefficient initialization; approximate 17-case 20% held-out split for AUC. |
| **Comparator or baseline** | Persistence baseline, climatological baseline, and uninformative 0.5 baseline for in-sample Brier comparison. |
| **Reported performance value(s)** | See B1a. Values are mostly in-sample or preliminary; prospective metrics are not yet available. |
| **Performance variation by geography/context/subgroup** | Not reported prospectively. Four selected historical cases span Somalia, South Sudan, Ethiopia/Tigray, and Yemen. No systematic country/subgroup error analysis. |
| **Performance variation by prediction horizon** | Not reported. Single 90-day horizon is used. |
| **Performance variation by severity threshold/class** | The system outputs IPC3+, IPC4+, IPC5 probabilities and tiers, but prospective precision/recall by tier is planned rather than reported. |
| **Known failure modes** | Author-specified coefficients, in-sample selected cases, small/wide-CI held-out AUC, underestimated sensitivity intervals, low coverage, country-level resolution, single-author design, conflict of interest, and high IPC misinterpretation risk. |
| **Source reference** | `ceres.pdf`, pages 1, 3-8, 10, Appendix C. |

#### B1a. Performance Values Table

| Metric / Result | Reported Value | Model / Horizon / Threshold | Evaluation Context | Interpretation for Record | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TIER correctness | 4/4 selected events flagged TIER-1 | Four historical IPC Phase 4-5 events | In-sample sanity check | Shows the model is not trivially broken on severe, selected cases; explicitly not evidence of prospective skill. | Section 6, lines 307-348 |
| P(IPC3+) / P(IPC4+) | Somalia July 2011: 0.961 / 0.743 | Somalia Famine, observed Phase 5 | In-sample selected event | High probabilities and TIER-1 for known famine case. | Section 6, lines 321-327 |
| P(IPC3+) / P(IPC4+) | South Sudan Feb 2017: 0.934 / 0.681 | South Sudan Famine, observed Phase 5 | In-sample selected event | High probabilities and TIER-1 for known famine case. | Section 6, lines 328-334 |
| P(IPC3+) / P(IPC4+) | Ethiopia Tigray Mar 2022: 0.912 / 0.588 | Observed Phase 4-5 | In-sample selected event | High probabilities and TIER-1 for selected severe case. | Section 6, lines 335-341 |
| P(IPC3+) / P(IPC4+) | Yemen Jun 2021: 0.887 / 0.534 | Observed Phase 4+ | In-sample selected event | High probabilities and TIER-1 for selected severe case. | Section 6, lines 342-348 |
| Mean Brier Score | 0.0066 | CERES | In-sample four-case comparison | Better than baselines in-sample; not a prospective performance claim. | Table 2, lines 349-368 |
| Mean Brier Score | 0.0494 | Persistence baseline | Same | Strong comparator because all four regions were already IPC Phase 3-4 at reference date. | Table 2, lines 349-370 |
| Mean Brier Score | 0.2275 | Climatological baseline | Same | CERES improves over base-rate baseline in-sample. | Table 2, lines 351-364 |
| Mean Brier Score | 0.2500 | Uninformative 0.5 baseline | Same | CERES improves over uninformative baseline in-sample. | Table 2, lines 365-368 |
| Sensitivity interval coverage | 4/4 selected cases contained observed outcome | In-sample sensitivity intervals | Selected historical severe cases | Expected to be optimistic; intervals are not calibrated predictive intervals. | Lines 371-372; Section 3.4 |
| Tier stability under coefficient perturbation | 39/43 regions stable (91%) | +/-20% coefficient perturbation, 100 Monte Carlo draws | March 2026 reference run | Suggests tier robustness to coefficient magnitude perturbation for most regions, but not performance against outcomes. | Lines 204-207 |
| AUC | 0.84; 95% CI [0.63, 1.00] | Approx. 17-case held-out split from 87 records | Discriminative performance check | Paper states CI is consistent with chance performance and should not be read as evidence of skill. | Lines 414-416 |
| Prospective Brier/BSS/precision/recall/CRPS | Not yet reported in paper | Public T+90 grading protocol | Prospective archive beginning March 2026 | These are planned future performance records, not current evidence. | Table 1, lines 260-303 |

#### B1b. Baseline Performance Conclusion

CERES provides unusually transparent performance infrastructure, but the current performance values do not demonstrate prospective forecasting skill. The 4/4 TIER-1 back-validation result and very low in-sample Brier score show that the model flags severe, selected, data-complete historical crises, but the paper explicitly states these are in-sample sanity checks and not performance claims. The held-out AUC of 0.84 is based on about 17 cases and has a wide confidence interval consistent with chance performance. The strongest current evidence is therefore not predictive skill, but auditability: timestamped forecasts, public archive, and a pre-registered prospective scoring plan. Baseline performance is not sufficient for IPC-facing suggested consideration beyond experimental monitoring and future audit. It does not support direct IPC evidence use, IPC classification support, official severity communication, or use in analyst decision workflows.

#### B2. Localized Performance & Validation

| Question | Response / Details |
| :--- | :--- |
| **Context-Specific Validation:** Has the model been explicitly tested and validated in this geography and crisis type? | No for any operational context. The paper reports selected in-sample severe historical cases, not prospective validation for a specific IPC cycle or country. |
| **Localized Error & Uncertainty:** How does the model perform here compared to its global or general baseline? | Not available. No systematic prospective country-level or regional error profile is reported. |
| **Relevance of the Target:** Is the model's training target an appropriate proxy for the intended phenomenon in this specific region? | The target is directly IPC-like, which makes it relevant but also high-risk. It cannot be treated as IPC classification because the model approximates IPC outcomes algorithmically. |
| **Uncertainty Communication:** Is the uncertainty of the output accurately communicated for this specific context? | Only partially. Sensitivity intervals are reported, but the paper says they are input-perturbation intervals and underestimate true uncertainty because they ignore parameter uncertainty and feature correlation. |

#### B3. Performance Implications for IPC Application

| Question | Response / Details |
| :--- | :--- |
| **Does reported performance support the proposed IPC application?** | It supports only experimental prospective tracking, not IPC application. |
| **Does performance hold in this geography/context?** | Not demonstrated. Context-specific performance is unavailable. |
| **Does performance hold at the needed prediction horizon?** | Not demonstrated prospectively at the 90-day horizon. |
| **Are the weakest performance dimensions relevant to this IPC use?** | Yes. Lack of prospective calibration, author-specified coefficients, and IPC-like output risk are decisive. |
| **What performance caveats must be carried into the Suggested Use Guide?** | State that outputs are not IPC evidence, not IPC classification, not validated for operational use, and should be used only for monitoring the model's future track record. |

### C. Contextual Limitations & Assumption Risks

| Question | Response / Details |
| :--- | :--- |
| **Data Dependency Risks:** Are the critical input data streams reliable, timely, and representative for this specific region? | Variable and context-dependent. IPC and WFP data may be irregular; lower coverage triggers wider intervals but does not suppress output. Country-level outputs may mask subnational crises. |
| **Assumption Violations:** What local conditions violate the model's core assumptions? | Any context where national aggregation hides subnational severity, where IPC cadence is stale, where WFP food access data are missing, where conflict/access suppress data collection, or where structural drivers dominate acute signals. |
| **Vulnerable Subgroups:** Are there specific populations within this context that the model systematically misrepresents or excludes? | Very likely possible but not assessed. Country-level outputs may hide IDPs, besieged populations, pastoralists, minority groups, border populations, or other localized severe food insecurity. |

### D. Reassessment Triggers

| Question | Response / Details |
| :--- | :--- |
| **Data Staleness:** Is the input data or ground-truth training data too old to reflect current realities in this context? | Reassessment is required whenever IPC inputs are stale, WFP data are missing, fewer than three signals are available, or the 90-day outcome cannot be matched to a published IPC classification. |
| **Shock Triggers:** What specific contextual shocks would immediately invalidate or weaken the model's assumptions here? | Sudden conflict escalation, access denial, famine review process, mass displacement, data blackout, market collapse, conflict-related obstruction of surveys, or subnational crisis not visible in country-level aggregation. |

### E. IPC Application and Working Function Implications

| IPC Application / Working Analytical Function | Context-Specific Finding | Suggested Consideration | Supporting Rationale |
| :--- | :--- | :--- | :--- |
| **Current Analysis / Current Analysis Evidence Support** | CERES is forecasted IPC-like probability output, not observed current evidence. | Not recommended. | Direct IPC-like probabilities create high misinterpretation risk and lack demonstrated prospective calibration. |
| **Projection Analysis / Projection Assumption Tracking** | 90-day horizon is projection-relevant, but performance is not yet prospectively demonstrated. | Not recommended for analyst use; experimental tracking only. | The output may be compared retrospectively against future IPC outcomes, but should not affect assumptions until validated. |
| **Risk Monitoring / Contextual Risk Monitoring** | Architecture may help monitor future model track record, but not food security risk operationally yet. | Experimental model monitoring only. | Use should focus on evaluating CERES itself, not on supporting IPC decisions. |

---

## Part 3. Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs

*This section applies because CERES directly outputs probabilities of IPC Phase 3+, IPC Phase 4+, and IPC Phase 5 conditions.*

| Guiding Question | Response / Assessment |
| :--- | :--- |
| **How do they define the outcome?** Is the target definition correct and aligned with IPC protocols? | CERES defines outcomes as IPC Phase 3+, Phase 4+, and Phase 5 at 90-day horizon. These are IPC-like targets, but the model does not reproduce IPC consensus analysis. |
| **How is data merged?** How is historical IPC data consolidated and prepared alongside predictor data? | CERES uses IPC classifications as one input signal and as verification outcome. Coefficients are initialized using 87 country-season IPC transition records selected for data coverage. |
| **Misinterpretation Risk:** Could the output be misinterpreted as a direct, endorsed IPC classification? | Extremely high. Probability estimates for IPC 3+/4+/5 and TIER-1 alerts could easily be mistaken as IPC-endorsed severity or famine warnings. |
| **Guardrails:** What prevents the output from replacing analyst-led consensus classification? | Required guardrails: label as non-IPC, non-endorsed, experimental model output; prohibit use in IPC analysis; require prospective validation; require independent technical review; require no external communication as IPC phase/famine evidence. |

**Special Rule conclusion:** CERES should not be suggested for IPC evidence use at this stage. Its only appropriate LACI pathway is technical monitoring of its prospective verification record and possible future reassessment after sufficient independent validation.

---

## Part 4. Suggested Use Guide

*This section synthesizes Parts 1-3 into suggested-consideration guidance for downstream analysts and subsequent LACI steps. It does not approve use. It should make limitations, cross-checks, reassessment triggers, and strict non-use rules visible.*

### A. Suggested Context-Specific Consideration

Based on the baseline assessment and context-specific limitations, how should this model-generated output be considered?

- [ ] **Suggested for consideration as assessed:** No additional context-specific limitation identified.
- [ ] **Suggested for consideration with documented limitation:** Output may be considered only with specific constraints noted in Part 2.
- [ ] **Consider only as contextual risk signal:** Output should not be treated as direct evidence, but may prompt further investigation.
- [X] **Reassessment recommended before consideration:** Current context triggers from Part 2D require re-evaluating the model-output appropriateness for any real IPC cycle.
- [X] **Not recommended for this context:** Under current conditions, or due to initial exclusion in Part 1, the output is misleading or unsuitable.

### B. Suggested Use Guide for Analysts

| Operational Domain | Suggested Guidance / Instructions | Supporting Rationale |
| :--- | :--- | :--- |
| **Suggested IPC Application(s) / Working Function(s)** | No IPC application suggested at this stage. Experimental model monitoring only. | The model directly estimates IPC-like outcomes but lacks demonstrated prospective calibration. |
| **Suggested Consideration Guidance** | Do not use CERES outputs in IPC analysis. If reviewed, track CERES predictions against future IPC outcomes as part of a technical audit/research exercise only. | The model's strongest current contribution is public prospective verification architecture, not proven predictive performance. |
| **Performance Basis for Suggested Guidance** | Current performance values are in-sample sanity checks, selected severe cases, or preliminary small-sample diagnostics. Prospective Brier/BSS/precision/recall/CRPS are planned but not yet reported. | Performance record does not support analyst-facing use. |
| **Uncertainty & Risks** | Author-specified coefficients, underestimated intervals, country-level aggregation, single-author design, commercial conflict of interest, data gaps, and direct IPC-like probability outputs create high operational and communication risk. | These risks are central enough to block IPC-facing consideration until independent validation. |
| **Strict Non-Use / Non-Communication Rules** | Do not present CERES probabilities or TIER alerts as IPC classification, IPC evidence, famine warning, official severity estimate, population estimate, or IPC-endorsed risk. Do not use in Current Analysis, Projection Analysis, or analyst-facing risk monitoring. | Special Rule guardrail for IPC-like model output. |

### C. Inputs for Step 3: Calibrate

CERES should not proceed to Step 3 Calibrate for IPC use at this stage. If IPC-GSU/IPC-LACI Team later decides to reassess after prospective evidence accumulates, minimum prerequisites should include:

| Calibration Need | Required Follow-Up |
| :--- | :--- |
| **Prospective validation threshold** | Require sufficient T+90 outcomes and public Brier/BSS/precision/recall/CRPS reporting before any calibration discussion. |
| **Independent technical review** | Review code, coefficients, data joins, target construction, verification ledger, and conflict-of-interest governance. |
| **Subnational relevance review** | Determine whether country-level output can ever support IPC workflows that require subnational analysis. |
| **Communication guardrails** | Define labels preventing confusion with IPC classifications or famine review outputs. |
| **Error-cost analysis** | Quantify consequences of false TIER-1 alerts and missed Phase 4+/5 cases before considering workflow exposure. |








