# LACI Learn Card v2 - Sample: High-Frequency Monitoring for Acute Child Malnutrition Forecasting

**Sample status:** Full-fidelity sample card based on the current LACI Learn Card template and the PNAS 2025 paper "High-frequency monitoring enables machine-learning-based forecasting of acute child malnutrition." This is not an IPC AMN decision record.

---

## Part 1. Model Metadata, Output & Methodology

### A. Model Summary

| Field | Description |
| :--- | :--- |
| **Model Title** | High-frequency monitoring enables machine-learning-based forecasting of acute child malnutrition |
| **Developer / Organization** | Constela-Villoslada et al.; PNAS 2025. The paper uses Kenya National Drought Management Authority (NDMA) monitoring data and includes NDMA-affiliated authors. |
| **Version and Date** | PNAS 2025, Vol. 122 No. 23 |
| **Model Type** | Outcome Indicator Model; AMN-relevant nutrition outcome forecasting |
| **Operational Readiness** | Research model / operationally motivated early warning demonstration using high-frequency sentinel-site monitoring data |
| **License and Access Conditions** | Source paper available in project resources. Access to underlying NDMA monitoring data, code, and operational implementation should be verified before ingestion. |
| **Main Contacts** | Source paper authors; implementation owner and data access contact require verification before operational review. |
| **Documentation & Links** | Source PDF: `../sources/constenla-villoslada-et-al-2025-high-frequency-monitoring-enables-machine-learning-based-forecasting-of-acute-child.pdf` |

### B. Model-Generated Output Profile

| Field | Description |
| :--- | :--- |
| **Output Name** | Ward/month U5 GAM prevalence forecasts and high-GAM alert identification |
| **Output Type** | Continuous forecast of GAM/wasting prevalence, with derived alert classification using a threshold |
| **Output Unit and Interpretation** | Predicted prevalence of children under 5 with GAM, measured using MUAC-based wasting definition. The paper also evaluates alert cases where wasting prevalence exceeds a threshold. |
| **Spatial Coverage and Resolution** | Kenya arid and semi-arid lands monitored by NDMA; ward-level / community-scale output in the paper |
| **Temporal Coverage and Update Frequency** | Monthly monitoring data from January 2006 to December 2020; forecasts evaluated at 1, 3, 6, 9, and 12 months ahead |
| **Intended Users** | Nutrition early warning analysts, IPC AMN analysts, drought/food-security monitoring teams, humanitarian targeting and preparedness users |

### C. Data and Target Profile

| Field | Description |
| :--- | :--- |
| **Input Data Sources** | High-frequency NDMA sentinel-site MUAC observations, time-series history of ward-level wasting prevalence, remote sensing and other secondary data, including weather, price, conflict, and food-security-relevant contextual predictors |
| **Training Target or Ground Truth** | Ward/month U5 GAM prevalence generated from child-and-month MUAC observations |
| **Target Nature** | Direct nutrition outcome indicator. It is AMN-relevant but not an IPC AMN classification, not IPC phase, and not an IPC-compatible classification output by itself. |
| **Geographic and Temporal Training Coverage** | Kenya ASAL areas monitored by NDMA; January 2006 to December 2020; 3,616,129 child-and-month MUAC observations used to generate 21,643 ward/month observations |
| **Missing Data Profile** | Sensitive to sentinel-site coverage, administrative boundary changes, household sampling changes, COVID-era data collection changes, and completeness of secondary data streams |
| **Major Assumptions** | High-frequency anthropometric monitoring is representative enough to estimate ward/month GAM; temporal autocorrelation in GAM remains informative; secondary data improve prediction without replacing observed nutrition evidence |

---

## Part 2. Model Typology

### A. Typology Assignment

| Field | Description / Classification |
| :--- | :--- |
| **Content Typology** | Outcome Indicator Model; AMN-relevant nutrition outcome forecasting |
| **Temporal Typology** | Forecasting |
| **Prediction Horizon** | 1, 3, 6, 9, and 12 months; paper emphasizes operational usefulness especially at 1, 3, and 6 months |
| **Typology Rationale** | The model predicts measured GAM prevalence, an acute malnutrition outcome indicator. It does not predict IPC phase, FEWS NET food security phase, or official IPC AMN classification. |
| **Special Assessment Routing** | No under the current food-security Special Rule, unless the output is presented as IPC AMN classification, IPC-compatible AMN outcome status, or a replacement for IPC AMN evidence. IPC AMN protocol review would be required before any such use. |

---

## Part 3. Initial IPC Application Mapping

**Note:** The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.

### A. Initial IPC Mapping

| Potential IPC Application | Suitability (High/Med/Low/None) | Rationale |
| :--- | :--- | :--- |
| **Current Analysis** | Low/Medium | Forecasted GAM is not observed current evidence. However, the underlying high-frequency MUAC monitoring system may be relevant to current AMN analysis if data quality, representativeness, and IPC AMN protocol fit are confirmed. |
| **Projection Analysis** | Medium/High | Forecasted GAM prevalence can support nutrition-related projection assumptions where context-specific validation is available and the time horizon matches the IPC projection window. |
| **Risk Monitoring** | High | The alert logic and monthly forecasting structure are well suited to nutrition risk monitoring and early warning, especially where sentinel-site coverage is stable. |

### B. IPC-GSU Summary

| Field | Summary / Decision |
| :--- | :--- |
| **Reviewer Name / Title** | Sample card - to be completed by IPC-GSU / IPC-LACI Team reviewer |
| **Review Date** | Sample card - to be completed |
| **Operational Readiness** | Research / operationally motivated demonstration. Requires IPC-LACI Team and IPC AMN technical review before workflow use. |
| **Confirmed Content Typology** | Outcome Indicator Model; AMN-relevant nutrition outcome forecasting |
| **Confirmed Temporal Typology** | Forecasting |
| **Primary IPC Application(s)** | Risk Monitoring / nutrition risk monitoring; Projection Analysis / nutrition assumption tracking |
| **Special Routing Required?** | No under the current food-security proxy Special Rule; yes for IPC AMN protocol review if proposed as AMN evidence or classification support. |
| **GSU Notes / Caveats** | Do not treat as IPC AMN classification. The model's usefulness depends heavily on current sentinel monitoring quality, temporal autocorrelation, local seasonality, and whether the target geography resembles the Kenya NDMA data-generating context. |




