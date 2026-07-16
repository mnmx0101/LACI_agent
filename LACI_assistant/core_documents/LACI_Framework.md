# LACI Framework Content and Structure - Draft v1

Working title:

**LACI Framework: Learning, Assessing, Calibrating, and Integrating Food Security-Related AI, Machine Learning, and Statistical Model Outputs for IPC Use**

This draft defines the proposed content structure for the LACI framework document. The framework document is the authoritative guidance. Operational tools such as the Learn Card, Assess Card, IPC Technical Audit Record, and End-User Decision Summary are derived from the framework but remain separate instruments.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 1. Framework Foundations

### 1.1 Executive Overview

LACI is a framework for reviewing food security-related AI, machine learning, and statistical models and determining whether their model-generated outputs may be considered for use within IPC workflows.

LACI is built around a central distinction: a **model** is the technical system that generates outputs, while a **model-generated output** is the specific result proposed for IPC use. A model may be technically credible in general, while a particular output may still be inappropriate for a specific potential IPC applications, geography, time horizon, or operational context.

LACI therefore evaluates model-generated outputs through four sequential steps:

1. **Learn** - document the model and output, assign the model/output typology, and map preliminary IPC relevance.
2. **Assess** - evaluate the model and output through technical screening, minimum requirements, IPC relevance questions, and context-specific limitations.
3. **Calibrate** - translate an assessed output into IPC-relevant interpretation, thresholds, uncertainty framing, or guidance.
4. **Integrate** - define how calibrated outputs may be embedded into IPC workflows, governance, and quality control arrangements.

The current operational priority is to make **Learn** and **Assess** actionable. Calibrate and Integrate remain part of the full LACI framework but are described at a higher level until the Learn and Assess tools have been tested.

### 1.2 Purpose, Scope, and Principles

#### Purpose and Scope

#### Purpose

The purpose of LACI is to provide a structured process for determining whether and how model-generated outputs from food security-related AI, machine learning, and statistical models can support IPC analysis and monitoring.

LACI supports:

- consistent documentation of models and model-generated outputs
- initial mapping of outputs to potential IPC applications
- technical screening of model reliability
- assessment of output relevance and usefulness for IPC workflows
- documentation of context-specific limitations and reassessment triggers
- preparation of downstream audit and end-user decision products

#### Scope

LACI applies to models and outputs that may be relevant to:

- IPC Current Analysis
- IPC Projection Analysis
- IPC Risk Monitoring

LACI applies to model outputs related to:

- food security or nutrition outcomes
- IPC-like or IPC-compatible outcomes
- contributing factors, hazards, risks, and drivers
- early warning or monitoring signals
- statistical nowcasts, forecasts, or classifications

#### Out of Scope

LACI is not:

- a general certification system for all models
- a replacement for IPC analyst judgment
- a mechanism for automatic IPC phase classification
- a guarantee that a model output remains reliable in all contexts
- a one-time approval that removes the need for reassessment when context changes

#### Core Principles

1. **Evaluate outputs, not only models.** The unit of IPC use is the model-generated output, not the model in the abstract.
2. **Reliability is use-specific.** An output may be acceptable for contextual risk monitoring but not for current analysis evidence support.
3. **Reliability is context-specific.** An output may become less reliable when assumptions, shocks, data quality, geography, or timing differ from the assessed context.
4. **IPC use remains analyst-led.** Model-generated outputs may support analysis but do not replace IPC protocols, analyst judgment, or consensus processes.
5. **Assessment must be auditable.** Claims about data, methods, evaluation, assumptions, limitations, and intended use should be supported by evidence.
6. **Minimum requirements matter.** Some weaknesses should prevent use regardless of broader potential value.
7. **The framework guides operational tools.** Learn and Assess cards are derived from LACI; they do not replace the framework document.

### 1.3 Foundational Concepts

#### 1.3.1 Model vs. Model-Generated Output

LACI distinguishes between a **model** and a **model-generated output**. A model may perform well against its metrics in general, while a specific output from that model may still be unsuitable in a particular context.

A **model** describes how an estimate or prediction is produced. It is the underlying methodology, algorithm, or statistical approach used to generate results.

A **model-generated output** describes what the model produces. It is the specific estimate, forecast, or classification generated for a particular location, population, and time period.

For example, a conflict forecasting model may perform well across its training period, but its output for a specific country may be unsuitable after a sudden large-scale shock such as the COVID-19 pandemic, a rapid political collapse, or a major flood event. In that situation, the model remains intact as a technical system, but the specific model-generated output requires additional scrutiny before it is used in IPC analysis.

*Forward Link:* This distinction is why **Step 1: Learn (Section 2.1)** explicitly profiles the model separately from its output, and why **Step 2: Assess (Section 2.2)** evaluates the specific output in context rather than providing blanket approval for the model.

#### 1.3.2 Potential IPC Application Analytical Function

A potential IPC application refers to a defined analytical process within which model-generated outputs may be considered. Model-generated outputs may serve different roles within IPC workflows. For operational simplicity, LACI currently aligns each potential IPC application with a working analytical function. The analytical functions used in LACI are working categories intended to support routing and assessment. They may be revised as LACI is tested across model types and IPC workflows along with TDT and IPC-LACI Team. Model-generated outputs are not used for direct IPC classification.

The three potential IPC applications and their analytical functions for LACI are:

| Potential IPC Application | Analytical Function (Examples)    | Description & Role in IPC Workflow                                                                                                                                               | Example                                                                                                                                            |
| ------------------------- | --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Current Analysis          | Current Analysis Evidence Support | Cross-sectional assessment of current conditions. Outputs provide supporting evidence for classifying current severity.                                                          | A malnutrition model output is used alongside survey data to triangulate current conditions.                                                       |
| Projection Analysis       | Projection Assumption Tracking    | Forward-looking assessment of likely evolution. Outputs track whether conditions underlying existing projections remain suitable and flag where assumptions may need revisiting. | A seasonal forecast shows significantly worse-than-expected rainfall and triggers a review of whether the projected Phase 2 outlook remains valid. |
| Risk Monitoring           | Contextual Risk Monitoring        | Continuous between-cycle monitoring. Outputs identify unusual patterns, emerging risks, or changing conditions requiring analyst attention.                                      | A rainfall anomaly index flags below-average conditions in a livelihood zone and prompts further investigation.                                    |

A model-generated output may be permitted to flag an emerging deterioration risk within IPC Risk Monitoring while not being appropriate to inform a phase classification in IPC Current Analysis.

*Forward Link:* These definitions form the basis of the initial pathway mapping conducted in **Step 1: Learn (Section 2.1)** and the corresponding **Learn Card (Section 3.1)**.

#### 1.3.3 Assessment Terminology

The following concepts form the core evaluation criteria applied during **Step 2: Assess (Section 2.2)** and are operationalized via the **Assess Card (Section 3.2)**.

##### [Placeholder: Case-Specific Suitability / Performance]

In LACI, this concept is dynamic and context-dependent. When assessing a model, we refer to its **performance against its metrics**. When assessing a model-generated output, we refer to whether the output can be used credibly for a defined potential IPC application (i.e., its case-specific suitability). It is assessed in relation to the intended use, the context of application, the interpretability of the output, and the extent to which uncertainty can be understood and communicated.

##### Technical Screening

A structured set of questions used to assess data quality, harmonization, model design, evaluation rigor, transparency, and operational readiness.

##### Minimum Requirement

A condition that must be met before a model-generated output can proceed for IPC consideration. Failure of a minimum requirement may prevent use or require further evidence before assessment can proceed.

##### Context-Specific Limitation

A limitation that affects whether a model-generated output remains reliable or appropriate in a specific operational setting, time period, geography, shock context, or IPC workflow.

##### Reassessment Trigger

A condition or event that requires caution, updated review, or reassessment before a model-generated output is used.

#### 1.3.4 Model Typology and potential IPC applications

##### Model and Output Typology

LACI assigns model/output typologies so that assessment questions and reliability expectations can be tailored to the type of evidence being proposed. Different model types have different relationships to IPC outcomes, which affects how their model-generated outputs are reviewed, assessed, and calibrated.

*Forward Link:* Assigning a model/output typology is a primary outcome of **Step 1: Learn**.

**Model Typologies:**

| Type                                        | Short Definition                                                                                                                                                                                                                                                                                                         | Examples                                                          |
| :------------------------------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------- |
| **Contributing Factors**              | Models that estimate the conditions and drivers influencing food security and nutrition outcomes.                                                                                                                                                                                                                        | Drought, flood, conflict nowcast and forecasting model            |
| **Outcome Indicators**                | Models that estimate the observed food security and nutrition outcomes experienced by a population. They describe the severity of outcomes, such as food consumption, nutritional status and mortality, and provide the primary evidence used for IPC classification through a convergence of evidence approach. | FCS, rCSI forecasting model, malnutrition model generated outputs |
| **IPC Outcome Modeling** | Models that directly estimate IPC phase, IPC phase-like severity, affected populations, or IPC-compatible outcome status. These outputs approximate IPC analytical outcomes and therefore require strict guardrails to avoid being interpreted as official IPC classifications or official IPC population estimates. | IPC phase outcome nowcast or forecast model-generated outputs |
| **IPC-Indicative Models**             | Models trained against IPC severity, IPC-compatible severity, or IPC-like outcome labels to estimate or indicate potential phase, severity level, warning score, or alert status. These outputs are indicative only and do not constitute IPC classification. | JMR or IPC-like warning score models |

##### Initial IPC Mapping

> **Note:** The structure and definitions for Initial IPC Mapping need to be re-confirmed with TJ and TDT.

For each model-generated output, map Suitable relevance across the three potential IPC applications:

- Current Analysis Evidence Pathway: IPC Current Analysis + Current Analysis Evidence Support
- Projection Assumption Pathway: IPC Projection Analysis + Projection Assumption Tracking
- Risk Monitoring Pathway: IPC Risk Monitoring + Contextual Risk Monitoring

The output of Learn should be a preliminary map, not a use decision.

## 2. LACI Steps

The LACI process operationalizes model-generated outputs for IPC use through four sequential steps. The current operational priority is to make Learn and Assess actionable. Calibrate and Integrate remain part of the full LACI framework but are described at a higher level until the Learn and Assess tools have been tested.

### 2.1 Step 1: Learn

**Objective:**
The objective of the Learn step is to document model metadata, assign the model/output typology, and perform an initial mapping of its potential application in IPC workflows (e.g., Current Analysis, Projection Analysis, Risk Monitoring). It establishes the foundational understanding of the model before any technical evaluation occurs.

**Activities to be Done:**
- **Part 1 (Model Metadata, Output & Methodology):** Capture essential metadata, operational readiness, the definition of the model-generated output, and the underlying data sources and assumptions.
- **Part 2 (Model Typology):** Assign the model/output analytical focus and temporal dimension.
- **Part 3 (IPC Application Mapping):** Perform an initial alignment of the output against specific potential IPC applications and provide the IPC-GSU summary.

**Operational Output:**
The completed **Learn Card** serves as the definitive reference document (a "metadata dictionary") for the model. It provides the necessary context and initial IPC mapping required to conduct the rigorous technical screening in the subsequent Assess step.

**Implications for the Next Step (Assess):**
- **Typology Dictates the Assessment Protocol:** The identified Content Typology determines which technical screening questions apply and whether the Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs is triggered.
- **Mapping Sets the Suitability Baseline:** Establishing the potential IPC application sets the baseline standard of performance the model must prove.
- **Identification of Red Flags:** Clarifying inputs early focuses the assessment team on known vulnerabilities.

### 2.2 Step 2: Assess

**Purpose:** Assess determines whether a model-generated output is credible and useful enough for a defined potential IPC application, and whether its limitations are sufficiently documented. It unifies two distinct but sequentially linked assessment functions: baseline model-output assessment and context-specific assessment for a specific operational setting. The baseline assessment is typically drafted by model builders, data providers, and/or IPC-LACI Team technical reviewers; the context-specific assessment is led by IPC-GSU, country/regional analysts, and IPC-LACI Team as needed.

**Activities:**
- **Part 1 (Baseline Model-Output Assessment):** Apply the full technical screening questions to flag warning signs and check against minimum exclusion requirements. Screening questions must not be weakened or skipped.
- **Part 2 (Context-Specific Assessment):** Evaluate output performance limitations, assumption validity, reassessment triggers, and implications for each relevant IPC application or working analytical function.
- **Part 3 (Special Rule):** Apply strict guardrails if the model is IPC Outcome Modeling, an IPC-Indicative model, or a Proxy-Trained Food Security Output.
- **Part 4 (Suggested Use Guide):** Synthesize Parts 1-3 into suggested-consideration guidance, restrictions, cross-checks, and reassessment triggers for downstream analysts. This guide does not approve use.

*Forward Link:* The operational tool for this step is the **Assess Card (Section 3.2)**.

### 2.3 IPC Applicability Review Layer

**Purpose:** This layer is a review and translation layer downstream of Assess that connects assessment evidence to operational decision-making.

**Activities:**

- IPC-LACI Team, or another designated IPC technical review body, audits completeness, evidence support, internal consistency, and safety of the Learn and Assess documentation. IPC-GSU and relevant country/regional analysts may contribute when IPC-facing guidance is affected.
- End-users receive a decision summary that supports case-by-case use decisions.

*Forward Link:* The operational tools for this step are the **IPC Technical Audit Record (Section 3.3)** and the **End-User Decision Summary (Section 3.4)**.

### 2.4 Step 3: Calibrate

**Purpose:** Calibrate translates a model-generated output that remains suitable for consideration into IPC-relevant interpretation rules, uncertainty framing, thresholds, categories, or other guidance for analyst use.

### 2.5 Step 4: Integrate

**Purpose:** Integrate defines where and how a calibrated output may be embedded into IPC workflows, including analyst guidance, quality control, governance, and rules for operational use.

## 3. Actionable Model Cards & Operational Tools

### 3.1 Learn Card

*Supports Section 2.1: Step 1: Learn*

**Template Link:** [LACI_Learn_Card_Template.md](LACI_Learn_Card_Template.md)

The Learn Card is completed first. It establishes the foundational understanding of the model via three components:
- **Part 1 (Model Metadata, Output & Methodology):** Metadata, operational readiness, output definitions, data sources, and assumptions.
- **Part 2 (Model Typology):** Typology assignment.
- **Part 3 (IPC Application Mapping):** Alignment with specific potential IPC applications.

### 3.2 Assess Card

*Supports Section 2.2: Step 2: Assess*

**Template Link:** [LACI_Assess_Card_Template.md](LACI_Assess_Card_Template.md)

The Assess Card focuses on the baseline technical screening of the model-generated output and the context-specific evaluation of that output for a defined operational setting. Part 1 may be drafted by the model builder, data provider, and/or IPC-LACI Team technical reviewer. Part 2 is led by IPC-GSU, country/regional analysts, and IPC-LACI Team as needed.

**Part 1: Baseline Model-Output Assessment**
A technical screening to identify critical integrity problems, flag warning signs, and establish initial exclusion criteria.
- **Section A. Technical Screening Questions:** Evaluates Data Quality, Missing Data & Harmonization, Model Design, Evaluation Rigor, and Transparency. Any 'No' or 'Unclear' answer generates a flag.
- **Section B. Minimum Requirements Checklist:** Flags critical conceptual or technical flaws (e.g., undefined output, temporal leakage risk) that disqualify the model from IPC consideration.

**Part 2: Context-Specific Assessment**
An evaluation of the specific model-generated output to determine its performance limitations and assumption validity.
- **Section A. Output Characteristics & Granularity:** Scale, frequency, and time horizon.
- **Section B. Performance and Intended Capture:** Model capability and uncertainty communication.
- **Section C. Limitations and Assumptions:** Specific geographies where the model fails, and conditions that break assumptions.
- **Section D. Reassessment Triggers:** Data staleness and clear thresholds requiring immediate reassessment.

**Part 3: Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs**
Applies additional guardrails for outputs with a direct implication for IPC outcomes, IPC-like severity, or affected-population estimates, ensuring target definition correctness, assessing misinterpretation risk, and preventing replacement of analyst-led consensus.

**Part 4: Suggested Use Guide**
Translates findings into an actionable operational mapping table containing:
- **Suggested IPC Application(s):** Applications or working analytical functions suggested for consideration, with limitations.
- **Suggested Consideration Guidance:** How analysts may consider the output in the current cycle.
- **Uncertainty & Risks:** How to account for them.
- **Strict Non-Use / Non-Communication Rules:** What analysts must not do or communicate.
This guide serves as the assessment-to-decision bridge and provides inputs for the IPC Technical Audit Record and the Calibrate step.

### 3.3 IPC Technical Audit Record

*Supports Section 2.3: IPC Applicability Review Layer*

Purpose:

The IPC Technical Audit Record documents whether the Learn and Assess documentation is complete, evidence-backed, internally consistent, and safe enough to inform IPC decision support. It is a quality assurance review of the documentation and suggested guidance, not a second model assessment.

Completed by:

- IPC-LACI Team, or another designated IPC technical review body. IPC-GSU and relevant country/regional analysts may contribute when IPC-facing guidance is affected.

Inputs:

- Learn Card
- Assess Card
- model paper or documentation
- model builder responses

Audit verdict categories:

- documentation complete for decision support
- complete with clarifications needed
- conditional pending evidence
- not ready due to critical documentation or evidence gap

### 3.4 End-User Decision Summary

*Supports Section 2.3: IPC Applicability Review Layer*

Purpose:

The End-User Decision Summary translates assessment and audit findings into practical decision guidance for IPC actors.

It should answer:

- How, if at all, should this model-generated output be considered?
- For which potential IPC applications?
- Under what limitations?
- What should users not do with it?
- What context changes trigger caution or reassessment?
- What other evidence should be considered alongside it?

End-user decision categories:

- suggested for consideration with limitations
- suggested for consideration with caution
- consider only as contextual risk signal
- reassessment recommended before consideration
- not recommended for this context
- insufficient information

## 4. Demo Outcomes

### 4.1 Demo Learn Card

Demo model-generated output:

**Market Price Stress Alert trained against FEWS NET-like food security outcomes**

This is a hypothetical example based on the type of hybrid/composite model LACI may need to assess. It illustrates how Learn documents the model and maps the output to potential IPC applications without yet approving it for use.

| Learn Card Field               | Demo Entry                                                                                                                                             |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Model title                    | Market Price Stress Alert Model                                                                                                                        |
| Developer / organization       | Example analytics partner                                                                                                                              |
| Model version and date         | v1.0, 2026                                                                                                                                             |
| Model type                     | Hybrid/composite model                                                                                                                                 |
| Model-generated output         | District-level market price stress alert                                                                                                               |
| Output format                  | Categorical alert: normal, watch, warning, alarm                                                                                                       |
| Output frequency               | Monthly                                                                                                                                                |
| Spatial unit                   | District or market catchment area                                                                                                                      |
| Forecast / monitoring horizon  | Near-real-time monitoring with 1-month alert horizon                                                                                                   |
| Input data                     | Staple food prices, price volatility, market availability indicators, rainfall anomaly, conflict-event indicator                                       |
| Training target / ground truth | FEWS NET-like food security outcome or alert status                                                                                                    |
| Target / proxy nature          | Proxy-trained food security / IPC-compatible outcome signal                                                                                            |
| Intended users                 | IPC technical staff, food security analysts, monitoring teams                                                                                          |
| Stated intended use            | Identify areas where market stress may indicate worsening food security risk                                                                           |
| Known out-of-scope use         | Direct IPC phase classification; replacement for price evidence review; use where price data are sparse or delayed                                     |
| Initial model/output typology  | Proxy-Trained Food Security Output / Hybrid Alert because contributing-factor inputs are trained against a food-security or FEWS NET-like outcome to set an alert threshold |
| Special assessment routing     | Route to Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs because the output may be interpreted as food-security outcome evidence                                      |

Initial potential IPC applications mapping:

| potential IPC applications        | Initial Mapping      | Learn Rationale                                                                                                                                                                                           | Minimum Reliability to Test in Assess |
| --------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| Current Analysis Evidence Pathway | Suitable but limited | Current price stress may support convergence of evidence if data are timely, representative, and interpreted with other evidence. The output should not be treated as classification evidence on its own. | High                                  |
| Projection Assumption Pathway     | Suitable             | Price stress may indicate whether projection assumptions about market access, purchasing power, or price trends remain Suitable.                                                                          | Moderate-High                         |
| Risk Monitoring Pathway           | Strongly Suitable    | Monthly alerts are well suited to monitoring deterioration, unexpected market stress, or areas requiring analyst review.                                                                           | Moderate                              |

Learn verdict:

**Suitable IPC mapping, with special assessment required.**

The output should proceed to Assess because it has Suitable IPC relevance, especially for Risk Monitoring and Projection Assumption Tracking. Assess must examine whether the FEWS NET-like training target is appropriate for IPC use, whether price data are reliable and timely, and whether the alert output could be misinterpreted as an IPC classification signal.

### Appendix B. Assess Card Template

Template for intended use, development data, methodology, evaluation, operational readiness, IPC relevance, technical screening, minimum requirements, and flags.

### 4.2 Demo Assess Card

Demo model-generated output:

**Market Price Stress Alert trained against FEWS NET-like food security outcomes**

This demo illustrates how the Assess Card combines general technical screening with context-specific limitations in a single operational tool.

| Assess Card Field                   | Demo Entry                                                                                                                                                    |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Proposed potential IPC applications | Risk Monitoring Pathway; Projection Assumption Pathway; limited consideration for Current Analysis Evidence Pathway                                           |
| Output interpretation               | The alert indicates unusual market price stress relative to historical and expected conditions. It does not indicate IPC phase.                               |
| In-scope use                        | Flag districts or markets requiring analyst review; support monitoring of market-related assumptions; identify areas where additional evidence may be needed. |
| Out-of-scope use                    | Direct IPC classification; standalone evidence of acute food insecurity severity; use in locations with unreliable market price series.                       |
| Main evidence provided              | Model description, input data list, training target, validation summary, update frequency, historical performance by district, alert threshold description.   |
| Main evidence missing               | Clear false positive/false negative analysis by crisis type; performance during major price shocks; comparison against a simple price-threshold baseline.     |

Technical screening summary:

| Screening Dimension                    | Demo Finding                                                                                                                                     | Flag     |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------- |
| Data quality                           | Price data sources are documented, but market coverage varies by country and some markets have long gaps.                                        | Major    |
| Missing data and harmonization         | Missing prices are imputed, but the imputation method is only partially documented. Temporal alignment appears Suitable but needs audit.         | Major    |
| Model design                           | Model structure is described, but feature selection and alert threshold logic need clearer justification.                                        | Moderate |
| Evaluation rigor                       | Overall historical accuracy is reported, but crisis-period performance, lead-time behavior, and false alarms are not sufficiently disaggregated. | Major    |
| Transparency and operational readiness | Monthly update process exists. Documentation is available, but code is not public and recalibration responsibility is only partly specified.     | Moderate |

Minimum requirement check:

| Requirement                                 | Demo Result       | Implication                                                                                      |
| ------------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------ |
| Output definition is clear                  | Pass              | Alert categories are defined.                                                                    |
| Training target is clear                    | Pass with caution | FEWS NET-like target is identified, but IPC comparability is not established.                    |
| Meaningful validation exists                | Partial           | Validation exists, but not enough by crisis type and geography.                                  |
| Leakage risk addressed                      | Unclear           | Temporal alignment needs audit.                                                                  |
| Missing data treatment documented           | Partial           | Imputation needs stronger documentation.                                                         |
| Uncertainty and limitations documented      | Partial           | General limitations exist, but alert uncertainty is not consistently communicated.               |
| Risk of IPC classification misuse addressed | Partial           | Output is called an alert, but user guidance should explicitly say it is not IPC classification. |

Special Rule for IPC Outcome Modeling, IPC-Indicative, and Proxy-Trained Food Security Outputs addendum:

| Question                                                                               | Demo Finding                                                        | Assessment Implication                                            |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Is the training target IPC, FEWS NET, or another proxy?                                | FEWS NET-like food security outcome / alert status.                 | Treat as a Proxy-Trained Food Security Output and require safeguards before IPC use.     |
| Could the output be misinterpreted as direct IPC classification?                       | Yes, especially if alarm levels are displayed alongside IPC maps.   | Require clear display language and user guidance.                 |
| Does validation cover IPC-relevant contexts, shocks, geographies, and analysis cycles? | Partially. Stable periods are better documented than shock periods. | Restrict use until crisis-period performance is clearer.          |
| What guardrails prevent replacement of analyst-led classification?                     | Not yet sufficient.                                                 | Add explicit guardrails in Assess and later integration guidance. |

Suggested Use Guide:

**Suggested for consideration as a contextual risk signal for Risk Monitoring with major flags; suggested for consideration as a Projection Assumption Tracking prompt only where market-price assumptions are central and data quality is adequate; not recommended for Current Analysis Evidence Support without additional evidence.**

Suggested consideration status:

- Risk Monitoring Pathway: consider only as a contextual risk signal, with documented limitations.
- Projection Assumption Pathway: consider only as a projection assumption prompt where market-price assumptions are central and data quality is adequate.
- Current Analysis Evidence Pathway: not recommended for current evidence support unless additional validation, baseline comparison, uncertainty documentation, and IPC-specific interpretation guidance are provided.

Required follow-up before broader use:

- document missing-data and imputation methods
- audit temporal leakage risk
- provide false positive and false negative analysis
- test crisis-period and shock-period performance
- compare against simple market-price baseline rules
- add explicit user guidance that alerts are not IPC classifications

### Appendix C. Technical Screening Question Bank

Partner-developed technical screening questions organized by:

- data quality
- missing data and harmonization
- model design
- evaluation rigor
- transparency and operational readiness

### Appendix D. IPC Technical Audit Record Template

Template for auditing completeness, evidence quality, unresolved gaps, and readiness for IPC workflow consideration.

### Appendix E. End-User Decision Summary Template

Template for translating assessment and audit results into operational decision guidance.

## 5. Appendices

Recommended appendices for the LACI framework document:

### 5. Appendix A. Learn Card Template

Template for documenting model metadata, model-generated output profile, data/target profile, and initial IPC mapping.

### 5.x Implementation and Testing Plan

To test LACI, each candidate model paper should be run through a structured multi-agent workflow:

1. Evidence Extraction Agent extracts facts from the paper.
2. Learn Agent completes the Learn Card and initial IPC mapping.
3. Assess Agent completes the Assess Card.
4. IPC Tech Audit Agent produces the IPC Technical Audit Record.
5. End-User Decision Agent produces the End-User Decision Summary.
6. Framework Orchestrator synthesizes verdicts and identifies changes needed in LACI or the tools.

Each agent should produce:

- key findings
- evidence used
- flags
- open questions
- verdict
- implications for IPC use

The test run should identify whether the LACI framework is clear enough, whether the tools are answerable from real model documentation, and whether the final decision is actionable for IPC users.










