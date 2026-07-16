# LACI Learn Card v2 - Sample: Yemen Data-Driven Early Detection Model

**Audience:** Decision-support preview for IPC/IPC-LACI Team/LACI reviewers. Partner-facing summaries should use the documentation-request language, not final-use verdict language.

**Sample status:** Full-fidelity sample card based on the LACI Learn Card structure, the World Bank method paper, and supplemental JMR Yemen operational metadata. This is not an IPC decision record.

---

## Part 1. Model Metadata, Output & Methodology

### A. Model Summary

| Field | Description |
| :--- | :--- |
| **Model Title** | Yemen Data-Driven Food Security Early Warning Model |
| **Developer / Organization** | World Bank Group authors, including Poverty and Equity Global Practice, Development Data Group, and Agriculture and Food Global Practice |
| **Version and Date** | Method paper: Policy Research Working Paper 10768, May 2024. Supplemental operational metadata: JMR Yemen version 2026-07-15, data cut-off 2026-07-15. |
| **Model Type** | IPC-Indicative Model; Proxy-Trained Food Security Output |
| **Operational Readiness** | JMR operational metadata documents a monthly country dataset, but IPC-facing ingestion still requires IPC-LACI Team verification of the exact extract, code/version, thresholds, source lags, and output labeling. |
| **License and Access Conditions** | Source paper is public. Code/repository and operational access should be verified before ingestion. |
| **Main Contacts** | Listed in the source paper; IPC-LACI Team should verify current contact and implementation owner before workflow use. |
| **Documentation & Links** | Source method paper: `../../resources/A Data-Driven Approach for Early Detection of Food Insecurity in Yemen.pdf`; supplemental operational note: `jmr_yemen_operational_details.md`. |

### B. Model-Generated Output Profile

| Field | Description |
| :--- | :--- |
| **Output Name** | JMR Yemen food-security escalation alerts, transformed indicators, and population exposure estimates |
| **Output Type** | Categorical escalation-risk alert levels, transformed indicators, and modeled population exposure estimates |
| **Output Unit and Interpretation** | JMR alert levels are Typical, Heightened, and Critical risks of escalation. Heightened is calibrated with greater emphasis on reducing false negatives; Critical is more conservative and places greater emphasis on reducing false positives. Population exposure estimates are model outputs, not official IPC population estimates. |
| **Native Signal / Score Definition** | Monthly Admin 2 JMR signals include raw data, transformed indicators, binary alerts, alert levels, and GLM/WMLE population exposure estimates. Method-paper target construction focuses on identifying areas at risk of transition into Phase 4 or 5 emergency status. |
| **Threshold / Decision Rule Used** | Transformed indicators use methods such as z-scores, moving-average divergences, and RSI. Typical/Heightened/Critical thresholds are calibrated to anticipate historical food insecurity escalations using false-negative/false-positive tradeoffs. These are JMR thresholds, not IPC Reference Table thresholds or IPC area-classification rules. |
| **Threshold / Signal Meaning** | Typical = no alert. Heightened = broader escalation-risk signal calibrated to reduce missed deteriorations. Critical = more conservative escalation-risk signal calibrated to reduce false positives. Phase 4+ target labels are historical FEWS NET IPC-compatible proxy labels, not current IPC consensus classification. |
| **Spatial Coverage and Resolution** | Method paper references 333 Yemen districts; JMR operational metadata for version 2026-07-15 records 22 Admin 1 areas and 335 Admin 2 areas using COD administrative boundaries. This boundary/version difference must be reconciled before IPC-facing use. |
| **Temporal Coverage and Update Frequency** | Method paper evidence covers October 2014-July 2023. JMR operational metadata records a monthly time series from 2010-01-01 to 2026-03-01, version 2026-07-15. |
| **Intended Users** | Food security early warning analysts, IPC technical reviewers, monitoring teams, and humanitarian analysts |

### C. Spatial and Temporal Unit Specification

#### C1. Spatial Unit Specification

| Field | Description |
| :--- | :--- |
| **Native Model Spatial Unit** | Mixed source units. FEWS NET IPC-compatible outcomes are reported by livelihood zone and harmonized to Yemen districts; other indicators may originate from markets, administrative areas, event points, or gridded climate data depending on source. |
| **Reporting / Output Spatial Unit** | Method paper reports 333 districts; JMR operational metadata reports 335 Admin 2 areas. Treat this as a boundary/version reconciliation requirement, not as a resolved discrepancy. |
| **Spatial Coding System** | JMR metadata identifies COD administrative boundaries for operational Admin 2 output. Exact COD-AB release/date and any mapping to IPC geography or GAUL/P-code practice must be confirmed before use. |
| **Spatial Coding Version / Boundary Date** | Not recorded in the current sample. Must be documented in a technical audit before ingestion. |
| **Spatial Coverage** | Yemen. Method paper: 333 districts. JMR operational metadata: 22 Admin 1 and 335 Admin 2 areas. Interpretation should distinguish IRG-controlled and AA-controlled areas where data-generating conditions differ, and the boundary/version discrepancy must be reconciled before use. |
| **Aggregation / Disaggregation Method** | FEWS NET livelihood-zone observations are harmonized to districts using spatial overlay and population weighting according to the existing LACI sample. Operational crosswalk must be verified. |
| **Spatial Crosswalk / Mapping File** | Not included in the current LACI sample. Required before analyst-facing workflow use. |
| **Known Spatial Mismatch Risks** | Livelihood-zone-to-district translation may introduce approximation error; district-level output may hide within-district populations, inaccessible groups, IDPs, and control-area differences. |

#### C2. Temporal Unit Specification

| Field | Description |
| :--- | :--- |
| **Input Data Frequency** | Source-dependent but operationally harmonized to monthly Admin 2 series: weekly IOM displacement to monthly, dekadal rainfall to monthly, dated ACLED events to monthly, monthly price/exchange/fuel series, and yearly WorldPop held constant within year. Source-specific latest input dates still require review. |
| **Model Update Frequency** | JMR country pages are updated monthly according to the operational metadata; exact extract date and version should be recorded for each checklist. |
| **Output Time Step / Reporting Period** | Monthly Admin 2 reporting period, with forecast/escalation-risk interpretation requiring output-specific horizon documentation. |
| **Prediction Horizon / Lead Time** | Existing LACI notes refer to a 5-month-ahead signal; exact horizon and horizon-specific performance should be verified before use. |
| **Training Period** | October 2014 to July 2023, based on source documentation summarized in the Assess Card. |
| **Validation Period** | Historical validation within the 2014-2023 Yemen dataset; exact split/cross-validation setup should be verified from source tables and implementation. |
| **Current Output Vintage Fields Required** | Operational note is required before any checklist: record version, extract date, data cut-off, latest input date by source, threshold version, boundary version, and publication-delay caveats. |
| **Known Temporal Mismatch Risks** | Stale FEWS NET/IPC-compatible labels, irregular input cadence, post-COVID relationship shifts, horizon mismatch with IPC projection windows, and current shocks changing historical relationships. |

### D. Data and Target Profile

| Field | Description |
| :--- | :--- |
| **Input Data Sources** | Food prices, fuel prices, exchange rates, drought indicators, conflict fatalities/incidents, displacement indicators, and FEWS NET IPC-compatible food security outcome data |
| **Training Target or Ground Truth** | Emergency transition defined using FEWS NET IPC-compatible phase data, with Phase 4 or 5 treated as emergency status |
| **Target Nature** | Proxy-trained food security target. The target is IPC-compatible/FEWS NET-derived, not direct IPC consensus classification for the current operational cycle. |
| **Target Threshold / Label Construction** | Historical FEWS NET IPC-compatible ratings are transformed into a binary emergency-transition target: Phase 4 or 5 = emergency status; lower phases = non-emergency. This collapses phase distribution into a binary proxy target and does not reproduce IPC convergence or the IPC 20 percent area-classification rule. |
| **Population Denominator / Unit of Analysis** | Primary unit is district-period early-warning status. If population-style outputs are produced, the denominator, population vintage, assistance assumptions, and whether Phase 3+, Phase 4+, or Phase 5 are separately estimated must be documented before any IPC-facing consideration. |
| **Geographic and Temporal Training Coverage** | Method paper: Yemen districts, October 2014-July 2023. JMR operational metadata: Yemen COD Admin 2 monthly series, 2010-01-01 to 2026-03-01. |
| **Missing Data Profile** | Paper describes harmonization and imputation approaches, including challenges in food price and IPC-compatible outcome data. Operational data gaps, especially by control area and time period, remain central to context-specific assessment. |
| **Major Assumptions** | FEWS NET IPC-compatible phase ratings are a usable proxy for historical emergency status; selected indicators remain informative of deterioration; historical relationships remain meaningful under current Yemen conditions. |

---

## Part 2. Model Typology

### A. Typology Assignment

| Field | Description / Classification |
| :--- | :--- |
| **Content Typology** | IPC-Indicative Model and Proxy-Trained Food Security Output |
| **Temporal Typology** | Forecasting |
| **Prediction Horizon** | Early warning of future emergency transition. Existing LACI notes describe a 5-month-ahead signal; exact operational horizon should be verified from implementation and paper tables before use. |
| **Typology Rationale** | The model is not merely estimating drivers such as prices or drought. It uses those drivers to predict an IPC-compatible food security outcome, namely transition into emergency status. |
| **Special Assessment Routing** | Yes - route to Part 3 Special Rule in the Assess Card because the output could be interpreted as IPC-like food security evidence or as affected-population estimates. |

---

## Part 3. Initial IPC Application Mapping

**Note:** The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.

### A. Initial IPC Mapping

| Potential IPC Application | Suitability | Visual Tag | Rationale |
| :--- | :--- | :--- | :--- |
| **Current Analysis** | Low | ![RED - Not Suggested](https://img.shields.io/badge/RED-Not%20Suggested-dc2626) `RED - Not Suggested` | The model forecasts/escalation-monitors risk. It is not direct current evidence and should not substitute for observed food security evidence or IPC convergence. |
| **Projection Analysis** | Medium/High | ![YELLOW - Investigation Prompt](https://img.shields.io/badge/YELLOW-Investigation%20Prompt-eab308) `YELLOW - Investigation Prompt` | The forecast/escalation-risk signal may help analysts revisit projection assumptions, especially when indicators point to emerging deterioration. |
| **Risk Monitoring** | High | ![BLUE - Contextual Supporting Information](https://img.shields.io/badge/BLUE-Contextual%20Supporting%20Information-2563eb) `BLUE - Contextual Supporting Information` | The Typical/Heightened/Critical alert structure is well suited to contextual risk monitoring between IPC cycles, provided data streams remain reliable and current context is checked. |

### B. IPC-GSU Summary

| Field | Summary / Decision |
| :--- | :--- |
| **Reviewer Name / Title** | Sample card - to be completed by IPC-GSU / IPC-LACI Team reviewer |
| **Review Date** | Sample card - to be completed |
| **Operational Readiness** | Research / pilot. Requires IPC-LACI Team verification before operational ingestion. |
| **Confirmed Content Typology** | IPC-Indicative Model; Proxy-Trained Food Security Output |
| **Confirmed Temporal Typology** | Forecasting |
| **Primary IPC Application(s)** | Projection Analysis / Projection Assumption Tracking; Risk Monitoring / Contextual Risk Monitoring |
| **Special Routing Required?** | Yes - Special Rule applies |
| **GSU Notes / Caveats** | Treat output as modeled escalation-risk information only. Do not present JMR alerts, predicted phase-like values, or population exposure estimates as IPC classification, IPC evidence, or official IPC population estimates. |









