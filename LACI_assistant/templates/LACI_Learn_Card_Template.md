# LACI Learn Card Template

**Purpose:** This card supports Step 1 (Learn) of the LACI framework. It establishes the foundational understanding of the model before any technical evaluation occurs. It consists of three main components:
- **Part 1 (Model Metadata, Output & Methodology):** Captures essential metadata, operational readiness, the definition of the model-generated output, spatial/temporal units, and the underlying data sources and assumptions.
- **Part 2 (Model Typology):** Assigns the model/output analytical focus and temporal dimension to determine assessment routing.
- **Part 3 (IPC Application Mapping):** Performs an initial alignment of the output against potential IPC applications and working analytical functions (e.g., Risk Monitoring / Contextual Risk Monitoring) and provides the IPC-GSU summary.

**General Operational Guide:**
- **When is this done?** This is the very first step in the LACI process. It must be completed *before* moving to the Assess step (Step 2).
- **Who completes it?** It is typically drafted by the model builder or data provider, and reviewed by the IPC-LACI Team or designated Learn Agent.
- **What is the operational output?** The completed Learn Card serves as the definitive reference document (a "metadata dictionary") for the model. It provides the necessary context and initial IPC mapping required to conduct the rigorous technical screening in the subsequent Assess step.

---

## Part 1. Model Metadata, Output & Methodology

### A. Model Summary

| Field                                   | Description                                                                     |
| :-------------------------------------- | :------------------------------------------------------------------------------ |
| **Model Title**                   | [Enter Model Title]                                                             |
| **Developer / Organization**      | [Enter Developer or Organization]                                               |
| **Version and Date**              | [Enter Version and Date]                                                        |
| **Model Type**                    | [e.g., Contributing Factors, Outcome Indicators, IPC Outcome Modeling, IPC-Indicative] |
| **Operational Readiness**         | [e.g., Demo/Prototype, Pilot, Fully Operational]                                |
| **License and Access Conditions** | [Enter License Details]                                                         |
| **Main Contacts**                 | [Enter Contact Information]                                                     |
| **Documentation & Links**         | [Provide links to papers, repos, dashboards, or technical docs]                 |

### B. Model-Generated Output Profile

| Field                                            | Description                                                   |
| :----------------------------------------------- | :------------------------------------------------------------ |
| **Output Name**                            | [Enter Output Name]                                           |
| **Output Type**                            | [e.g., continuous, probabilistic, categorical, signal, index] |
| **Output Unit and Interpretation**         | [Explain how to read the output value]                        |
| **Native Signal / Score Definition**       | [Define the model signal precisely: indicator value, anomaly, probability, class, index, risk score, predicted outcome, forecast category, etc.] |
| **Threshold / Decision Rule Used**         | [Record any IPC Reference Table threshold, non-IPC statistical threshold such as LTA - 2 SD, percentile/z-score, model-internal cutoff, alert class, or outcome-trained label rule. State Not applicable if no threshold is used.] |
| **Threshold / Signal Meaning**             | [Explain what the threshold or signal means in the model's own terms before IPC interpretation is attempted.] |
| **Spatial Coverage and Resolution**        | [Brief summary only; complete detailed spatial unit fields in Part 1C] |
| **Temporal Coverage and Update Frequency** | [Brief summary only; complete detailed temporal unit fields in Part 1C] |
| **Intended Users**                         | [Who is this output built for?]                               |

### C. Spatial and Temporal Unit Specification

*Record the model's native spatial and temporal units precisely enough that IPC reviewers can judge whether the output matches IPC analysis units, review windows, and projection horizons. If the model uses custom units, grids, or crosswalks, attach or reference the mapping file.*

#### C1. Spatial Unit Specification

| Field | Description |
| :--- | :--- |
| **Native Model Spatial Unit** | [e.g., country, ADM1, ADM2, district, livelihood zone, market, facility, grid cell, basin, point, polygon] |
| **Reporting / Output Spatial Unit** | [Unit shown to analysts or exported by the system] |
| **Spatial Coding System** | [e.g., GAUL, GADM, OCHA P-code, ISO, custom shapefile ID, raster grid ID, latitude/longitude] |
| **Spatial Coding Version / Boundary Date** | [e.g., GAUL 2015, GADM v4.1, OCHA P-code release date, custom boundary vintage] |
| **Spatial Coverage** | [Countries/regions/admin units covered, plus excluded or low-coverage areas] |
| **Aggregation / Disaggregation Method** | [Explain any grid-to-admin, livelihood-zone-to-district, market-to-admin, or admin-to-IPC-area transformation] |
| **Spatial Crosswalk / Mapping File** | [Link to crosswalk, shapefile, boundary source, or state Not available] |
| **Known Spatial Mismatch Risks** | [Boundary changes, missing P-codes, livelihood-zone/admin mismatch, national output masking subnational crisis, etc.] |

#### C2. Temporal Unit Specification

| Field | Description |
| :--- | :--- |
| **Input Data Frequency** | [e.g., daily, 10-day/dekadal, weekly, monthly, quarterly, yearly, event-based, irregular] |
| **Model Update Frequency** | [e.g., daily, weekly, monthly, quarterly, ad hoc] |
| **Output Time Step / Reporting Period** | [e.g., daily, dekadal, weekly, monthly, seasonal, annual, rolling window] |
| **Prediction Horizon / Lead Time** | [e.g., nowcast, 30-day, 90-day, 3-month, 5-month, seasonal, annual] |
| **Training Period** | [Start/end dates] |
| **Validation Period** | [Start/end dates] |
| **Current Output Vintage Fields Required** | [Record model run date, data cut-off date, latest input date by source, and output publication date when completing a live use review] |
| **Known Temporal Mismatch Risks** | [Stale inputs, irregular IPC/FEWS cadence, seasonal-calendar mismatch, forecast horizon mismatch, lagged data, nowcast mistaken for forecast] |
### D. Data and Target Profile

| Field                                               | Description                                                     |
| :-------------------------------------------------- | :-------------------------------------------------------------- |
| **Input Data Sources**                        | [List main input datasets]                                      |
| **Training Target or Ground Truth**           | [What is the model trying to predict?]                          |
| **Target Nature**                             | [Is the target IPC, FEWS NET, an indicator, or a hazard proxy?] |
| **Target Threshold / Label Construction**     | [If the target uses a threshold, anomaly rule, expert label, IPC/FEWS/AMN label, or other constructed class, document how that label is created and what it means.] |
| **Population Denominator / Unit of Analysis** | [If output relates to people, households, children, area phase, caseload, or affected population, record the denominator and unit of analysis used by the model.] |
| **Geographic and Temporal Training Coverage** | [Where and when was the model trained?]                         |
| **Missing Data Profile**                      | [How are missing inputs handled?]                               |
| **Major Assumptions**                         | [List core assumptions the model relies on]                     |

---

## Part 2. Model Typology

### A. Typology Assignment

*Assign the model/output analytical focus and temporal dimension to determine assessment routing. According to the Framework, these typologies determine how outputs are reviewed, assessed, and calibrated.*

**1) Content Typology Reference:**
* **Contributing Factors:** Models that estimate the conditions and drivers influencing food security and nutrition outcomes.
* **Outcome Indicators:** Models that estimate the observed food security and nutrition outcomes experienced by a population.
* **IPC Outcome Modeling:** Models that directly estimate IPC phase, IPC phase-like severity, affected populations, or IPC-compatible outcome status. These outputs approximate IPC analytical outcomes and require strict guardrails.
* **IPC-Indicative Models:** Models trained against IPC severity, IPC-compatible severity, or IPC-like outcome labels to estimate or indicate potential phase, severity level, warning score, or alert status.

**2) Temporal Typology Reference:**
* **Nowcasting / Monitoring:** Estimating current, unobserved conditions based on recent/current data.
* **Forecasting:** Predicting future conditions.

| Field                                | Description / Classification                                                                                                                         |
| :----------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Content Typology**           | [Enter Typology from Content Reference above]                                                                                                        |
| **Temporal Typology**          | [Enter Nowcasting / Monitoring OR Forecasting / Projection]                                                                                          |
| **Prediction Horizon**         | [Specify the exact horizon, e.g., Current status, 1-month ahead. This directly dictates which IPC mapping is feasible.]              |
| **Typology Rationale**         | [Explain why these classifications were chosen based on the relationship between inputs, target, and time horizon]                                   |
| **Special Assessment Routing** | [e.g., Route to Part 3 Special Rule in Assess Card if the output may be interpreted as IPC outcome modeling, an IPC-indicative output, or proxy-trained food security output] |

---

## Part 3. Initial IPC Application Mapping

*Map the suitability of this output across the three potential IPC applications as defined in the Framework. This is a preliminary map to guide the assessment, not a final use decision. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team.*

### A. Initial IPC Mapping

**Suitability Criteria:**
* **High:** The output format, timeliness, and target directly align with the analytical function of the application.
* **Medium:** The output is relevant but requires significant transformation, additional context, or has slight temporal/spatial mismatches.
* **Low:** The output provides only tangential information or requires major assumptions to be relevant.
* **None:** The output is completely mismatched.

| Potential IPC Application | Suitability (High/Med/Low/None) | Visual Tag | Rationale (Link to Framework Definitions) |
| :--- | :--- | :--- | :--- |
| **Current Analysis** | [ ] | [Badge / label] | [Explain how it supports current condition assessment] |
| **Projection Analysis** | [ ] | [Badge / label] | [Explain how it tracks forward-looking assumptions] |
| **Risk Monitoring** | [ ] | [Badge / label] | [Explain how it flags contextual risks and anomalies] |

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
### B. IPC-GSU Summary

*This section is to be completed by the IPC Global Support Unit (GSU). It summarizes the model's typology, operational readiness, and initial mapping for downstream assessment routing.*

| Field | Summary / Decision |
| :--- | :--- |
| **Reviewer Name / Title** | [Enter Name and Title] |
| **Review Date** | [Enter Date] |
| **Operational Readiness** | [Confirm if demo/prototype vs fully operational] |
| **Confirmed Content Typology** | [e.g., Contributing Factors, Outcome Indicators, IPC Outcome Modeling, IPC-Indicative Models] |
| **Confirmed Temporal Typology**| [e.g., Nowcasting / Monitoring, Forecasting] |
| **Primary IPC Application(s)** | [Which applications are deemed suitable enough to proceed to the Assess step?] |
| **Special Routing Required?** | [e.g., Yes - route to Part 3 Special Rule in Assess Card, No] |
| **GSU Notes / Caveats** | [Any additional context for the assessment team] |















