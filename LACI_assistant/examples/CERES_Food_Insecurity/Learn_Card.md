# LACI Learn Card v2 - Sample: CERES Probabilistic Early Warning System

**Sample status:** Full-fidelity sample based on `ceres.pdf` in `../sources/`. This is not an IPC decision record.

---

## Part 1. Model Metadata, Output & Methodology

### A. Model Summary

| Field | Description |
| :--- | :--- |
| **Model Title** | CERES: A Probabilistic Early Warning System for Acute Food Insecurity |
| **Developer / Organization** | Tom Danny S. Pedersen, Northflow Technologies AS |
| **Version and Date** | March 2026 paper; live/prospective record reported as beginning March 2026 |
| **Model Type** | IPC Outcome Modeling / IPC-Indicative Model; Proxy-Trained Food Security Output |
| **Operational Readiness** | Live automated research/operational prototype with public API and archive, but prospective performance not yet demonstrated in the paper |
| **License and Access Conditions** | Paper states public API and data are freely accessible; institutional subscriptions are commercial. Conflict of interest disclosed because author founded Northflow Technologies AS. |
| **Main Contacts** | ceres@northflow.no; CERES site and GitHub listed in paper |
| **Documentation & Links** | Source PDF: `../sources/ceres.pdf`; paper lists `https://ceres.northflow.no` and `https://github.com/northflowlabs/ceres` |

### B. Model-Generated Output Profile

| Field | Description |
| :--- | :--- |
| **Output Name** | CERES FamineHypothesis / probabilistic IPC-phase early warning output |
| **Output Type** | Probabilistic output plus alert tier: probabilities for IPC Phase 3+, Phase 4+, and Phase 5; sensitivity intervals; TIER-1/TIER-2/TIER-3 classification; driver decomposition |
| **Output Unit and Interpretation** | 90-day ahead probability estimates for IPC Phase 3+ (Crisis), IPC Phase 4+ (Emergency), and IPC Phase 5 (Famine). TIER-1 is triggered by P(IPC4+) >= 0.50 or CRITICAL convergence. |
| **Spatial Coverage and Resolution** | 43 high-risk countries globally; paper notes country-level ISO output with Admin1 signals computed internally but not exposed in primary output |
| **Temporal Coverage and Update Frequency** | Weekly pipeline; 90-day forecast horizon; prospective verification at T+90 |
| **Intended Users** | Early warning, risk monitoring, anticipatory action, and food security analysts. IPC-facing use would require strict guardrails and technical audit. |

### C. Data and Target Profile

| Field | Description |
| :--- | :--- |
| **Input Data Sources** | CHIRPS precipitation anomalies, MODIS NDVI, ACLED conflict events/fatalities, IPC classifications, WFP food consumption scores/rCSI, and FAO/WFP cereal price indices |
| **Training Target or Ground Truth** | IPC Phase 3+, IPC Phase 4+, and IPC Phase 5 outcomes at 90-day horizon, using IPC Global Platform outcomes for verification. Coefficients are initialized from literature review and 87 IPC transition records, not estimated from a validated held-out dataset. |
| **Target Nature** | Direct IPC-like / IPC-derived food security target. This is a high-risk IPC Outcome Modeling / IPC-Indicative output. |
| **Geographic and Temporal Training Coverage** | Coefficient initialization uses 87 country-season IPC transition records across 31 countries, 2011-2023; paper reports 43 monitored countries. |
| **Missing Data Profile** | Regions with fewer than three of six signals are flagged low-coverage and receive wider perturbation ranges. IPC cadence and WFP survey irregularity are listed as data-gap limitations. |
| **Major Assumptions** | Author-specified coefficients and weights are reasonable initial values; IPC current/projected phases can be used as severity inputs; weekly forward-filled data streams are adequate for 90-day warning; public prospective verification will eventually establish calibration. |

---

## Part 2. Model Typology

### A. Typology Assignment

| Field | Description / Classification |
| :--- | :--- |
| **Content Typology** | IPC Outcome Modeling / IPC-Indicative Model; Proxy-Trained Food Security Output |
| **Temporal Typology** | Forecasting |
| **Prediction Horizon** | 90 days ahead, updated weekly |
| **Typology Rationale** | CERES directly estimates probabilities of IPC Phase 3+, Phase 4+, and Phase 5. This is not merely a driver or hazard model. It approximates IPC analytical outcomes and therefore requires strict guardrails. |
| **Special Assessment Routing** | Yes - route to Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs. |

---

## Part 3. Initial IPC Application Mapping

**Note:** The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.

### A. Initial IPC Mapping

| Potential IPC Application | Suitability (High/Med/Low/None) | Rationale |
| :--- | :--- | :--- |
| **Current Analysis** | None/Low | The output is a model-generated forecast of IPC-like outcomes, not current evidence. Misinterpretation risk is very high. |
| **Projection Analysis** | Low/Medium | The 90-day horizon aligns with projection-relevant monitoring, but prospective performance is not yet demonstrated and coefficients are author-specified. |
| **Risk Monitoring** | Medium | The architecture may support monitored experimental risk signals, but only as non-evidence, non-classification prompts pending prospective validation. |

### B. IPC-GSU Summary

| Field | Summary / Decision |
| :--- | :--- |
| **Reviewer Name / Title** | Sample card - to be completed by IPC-GSU / IPC-LACI Team reviewer |
| **Review Date** | Sample card - to be completed |
| **Operational Readiness** | Live/prototype with public prospective archive; performance not yet established for IPC-facing consideration |
| **Confirmed Content Typology** | IPC Outcome Modeling / IPC-Indicative; Proxy-Trained Food Security Output |
| **Confirmed Temporal Typology** | Forecasting, 90-day horizon |
| **Primary IPC Application(s)** | Experimental risk monitoring only; not Current Analysis Evidence Support |
| **Special Routing Required?** | Yes - Special Rule applies |
| **GSU Notes / Caveats** | Treat as high-risk IPC-like output. No operational IPC use should be suggested until prospective verification produces enough performance evidence and independent technical review is completed. |




