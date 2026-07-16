# LACI Framework Overview

**LACI** stands for **Learning, Assessing, Calibrating, and Integrating** Food Security-Related AI, Machine Learning, and Statistical Model Outputs for IPC Use.

This document serves as a high-level, 2-page overview of the LACI framework, its core concepts, and its operational toolkit.

---

## 1. Background & Objective

The humanitarian sector increasingly relies on AI, machine learning, and statistical models to predict food security outcomes, track anomalies, and forecast crises. However, the Integrated Food Security Phase Classification (IPC) relies on rigorous, consensus-based, analyst-led protocols. There is an urgent need to safely evaluate whether, when, and how data from these advanced models can be ingested as evidence into the IPC workflow.

**The Objective of LACI:**
To provide a structured, auditable process for determining whether and how model-generated outputs can support IPC Current Analysis, Projection Analysis, and Risk Monitoring. LACI is *not* a general certification system for all models, nor is it a replacement for IPC analyst judgment. Instead, it operationalizes model outputs as rigorous, complementary evidence.

---

## 2. Core Term Clarification

A fundamental principle of LACI is the critical distinction between a **Model** and a **Model-Generated Output**:

> [!IMPORTANT]
> **Evaluate outputs, not only models.**
> A **model** describes how an estimate or prediction is produced. It is the underlying methodology, algorithm, or statistical approach used to generate results.
>
> A **model-generated output** describes what the model produces. It is the specific estimate, forecast, or classification generated for a particular location, population, and time period.
>
> A model may perform well against its metrics in general, but a specific *output* might still be inappropriate for a given time horizon, geography, or shock context. Suitability and performance are case-specific and context-dependent.

---

## 3. The Four Steps of LACI

LACI evaluates model-generated outputs through four sequential steps:

1. **Learn:** Metadata, typology definition and perform an initial mapping of its potential application in IPC (e.g. Current Analysis, Projection Analysis, Risk Monitoring).
2. **Assess:** Evaluate the model and output through technical screening (data quality, methodology, validation rigor), minimum requirements, and IPC relevance. Document context-specific limitations and flags.
3. **Calibrate:** Translate assessed outputs into IPC-relevant interpretation rules, threshold categories, or uncertainty framing.
4. **Integrate:** Define exactly how the calibrated outputs are embedded into IPC workflows, governance, and end-user guidance.

---

## 4. Operational Tools & Templates

To operationalize the **Learn** and **Assess** steps, LACI relies on three primary operational tools. These templates guide model builders, IPC-LACI Team reviewers, and analysts through the evaluation process.

### The Templates

* [LACI Learn Card Template](LACI_Learn_Card_Template.md): A descriptive metadata sheet cataloging the model, its outputs, training data, and an initial mapping to potential IPC applications.
* [LACI Assess Card Template](LACI_Assess_Card_Template.md): Technical evaluation of model soundness and time-relevance. Now includes context-specific limitations.

---

## 5. Real-World Application: Yemen Data-Driven Model

To demonstrate the LACI framework in action, we applied it to the World Bank's recent publication: *A Data-Driven Approach for Early Detection of Food Insecurity in Yemen’s Humanitarian Crisis*.

This model uses inflation, conflict, and agricultural productivity indicators to predict transitions into IPC Phase 4+ emergencies with a 5-month lead time.

Review the completed samples below to see how LACI systematically structures complex model assessments into actionable IPC guidance:

### The Yemen Sample Set

* **[Sample Learn Card (Yemen)](LACI_Learn_Card_Yemen_Datadriven.md)**: Documents the model's reliance on price shocks, conflict data, and drought (SPI) to trigger binary early warnings.
* **[Sample Assess Card (Yemen)](LACI_Assess_Card_Yemen_Sample.md)**: Assesses the methodology (GLM with Recursive Feature Elimination) and explicitly flags the risk that the model's output ("Population in Phase 4+") could be misinterpreted as a direct, endorsed IPC classification without proper guardrails. Includes context-specific limitations addressing IRG/AA geographic data divides.






