# LACI Learn Card v2 - Sample: AI Flood Forecasts

**Sample status:** Full-fidelity sample card based on the current LACI Learn Card template and the paper "AI Increases Global Access to Reliable Flood Forecasts." This is not an IPC decision record.

---

## Part 1. Model Metadata, Output & Methodology

### A. Model Summary

| Field | Description |
| :--- | :--- |
| **Model Title** | AI Increases Global Access to Reliable Flood Forecasts |
| **Developer / Organization** | Google-affiliated and ECMWF-affiliated authors; paper reports incorporation into FloodHub |
| **Version and Date** | Published paper; GloFAS v4 benchmark referenced as current operational version from July 2023 |
| **Model Type** | Contributing Factors / Environmental Hazard Forecasting |
| **Operational Readiness** | Operational early warning product reported as producing free/open real-time forecasts in over 80 countries; current operational version and access conditions require verification before IPC workflow use |
| **License and Access Conditions** | Paper states FloodHub forecasts are available without monetary charge or website registration; research implementation and reanalysis/re-forecasts are described as open source/open repository resources. Verify current terms before integration. |
| **Main Contacts** | Source paper authors / operational product owner to be verified before workflow use |
| **Documentation & Links** | Source PDF: `../sources/AI Increases Global Access to Reliable Flood Forecasts.pdf`; FloodHub referenced in paper as `https://g.co/floodhub` |

### B. Model-Generated Output Profile

| Field | Description |
| :--- | :--- |
| **Output Name** | Riverine flood forecasts / streamflow extreme-event forecasts |
| **Output Type** | Daily streamflow forecast and return-period extreme-event warning signal |
| **Output Unit and Interpretation** | Forecasted streamflow and flood event reliability/skill over return-period thresholds. For IPC purposes this is a hazard forecast, not a food security outcome. |
| **Spatial Coverage and Resolution** | Global river basins / watersheds; paper reports operational forecasts in over 80 countries and evaluation across 5,680 streamflow gauges |
| **Temporal Coverage and Update Frequency** | Short-term daily forecasts through a 7-day forecast horizon; paper emphasizes reliability up to 5-day lead time for extreme events |
| **Intended Users** | Flood early warning agencies, disaster risk managers, anticipatory action users, humanitarian risk monitoring teams |

### C. Data and Target Profile

| Field | Description |
| :--- | :--- |
| **Input Data Sources** | Hydrological and meteorological model inputs; paper describes LSTM streamflow forecasting and comparisons with GloFAS. Real-time streamflow data are not used as AI model inputs because they are not available everywhere and GloFAS does not use autoregressive inputs. |
| **Training Target or Ground Truth** | Streamflow gauge observations and return-period flood events |
| **Target Nature** | Environmental hazard target. It does not estimate food security, nutrition, IPC phase, or affected food-security populations. |
| **Geographic and Temporal Training Coverage** | Evaluation uses 5,680 streamflow gauges with data over 1984-2021 and cross-validation across time and location; additional splits include continents, climate zones, and terminal watersheds. |
| **Missing Data Profile** | Ungauged basins are central to the model purpose. Local reliability varies where streamflow observations and hydrological data are limited. |
| **Major Assumptions** | AI streamflow forecasting skill transfers to ungauged basins; return-period flood forecasts can provide actionable warning; flood hazard becomes IPC-relevant only where a credible food-security transmission pathway exists. |

---

## Part 2. Model Typology

### A. Typology Assignment

| Field | Description / Classification |
| :--- | :--- |
| **Content Typology** | Contributing Factors / Environmental Hazard Forecasting |
| **Temporal Typology** | Forecasting |
| **Prediction Horizon** | Up to 7 days; paper emphasizes reliable extreme-event forecasts up to 5 days compared with GloFAS nowcasts |
| **Typology Rationale** | The model predicts riverine flood hazard and streamflow, which may affect IPC drivers such as crop damage, displacement, market access, disease risk, or assistance delivery. It does not predict food security outcomes directly. |
| **Special Assessment Routing** | No under the current IPC Outcome Modeling / IPC-Indicative / Proxy-Trained Food Security Output Special Rule, unless transformed into food security outcome predictions. Requires food-security transmission-pathway review before IPC consideration. |

---

## Part 3. Initial IPC Application Mapping

**Note:** The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.

### A. Initial IPC Mapping

| Potential IPC Application | Suitability (High/Med/Low/None) | Rationale |
| :--- | :--- | :--- |
| **Current Analysis** | Low | A flood forecast is not direct evidence of current food security outcomes, IPC phase, or household food consumption/livelihood conditions. |
| **Projection Analysis** | Medium | Short-term flood hazard forecasts may inform projection assumptions where flooding plausibly affects crops, access, displacement, disease, markets, or assistance delivery. |
| **Risk Monitoring** | High | The model is well suited to contextual hazard monitoring and anticipatory risk signaling where flood exposure is relevant. |

### B. IPC-GSU Summary

| Field | Summary / Decision |
| :--- | :--- |
| **Reviewer Name / Title** | Sample card - to be completed by IPC-GSU / IPC-LACI Team reviewer |
| **Review Date** | Sample card - to be completed |
| **Operational Readiness** | Operationally available flood early warning product per paper; IPC workflow readiness requires verification. |
| **Confirmed Content Typology** | Contributing Factors / Environmental Hazard Forecasting |
| **Confirmed Temporal Typology** | Forecasting |
| **Primary IPC Application(s)** | Risk Monitoring / Contextual Risk Monitoring; short-term Projection Analysis / Projection Assumption Tracking where flood impacts are plausible |
| **Special Routing Required?** | No food-security proxy Special Rule. Yes for context-specific food-security transmission-pathway review. |
| **GSU Notes / Caveats** | Do not treat as food security evidence. IPC relevance depends on local exposure, vulnerability, seasonality, livelihood timing, flood impact pathway, and reliability in the basin/geography under review. |




