# Template Feedback v2 - Acute Child Malnutrition Forecasting

## Why v2 Was Needed

The first-pass AMN sample correctly identified the model as an AMN-relevant outcome indicator model, but it compressed too much of the assessment. It did not fully show the operational difference between baseline technical validity, IPC AMN protocol relevance, and context-specific use.

## What v2 Corrects

- Restores the full Assess Card structure.
- Preserves all 19 screening questions with flag points.
- Makes the AMN/IPC boundary explicit: forecasting GAM prevalence is not the same as IPC AMN classification.
- Adds Kenya NDMA sentinel-site context, including ward/month MUAC-derived GAM prevalence.
- Makes the key model-dependence visible: temporal autocorrelation, sentinel-site stability, representativeness, and period-specific performance.
- Adds Step 3 calibration needs for nutrition thresholds, local validation, and analyst-facing communication.

## Template Refinements Surfaced by v2

- Add an explicit `IPC AMN protocol relevance` prompt for nutrition outcome models.
- Add a `Data Collection Continuity` prompt for sentinel-site and survey-derived models.
- Add a `Target-to-IPC Relationship` field to the Learn Card so AMN-relevant indicators are not confused with IPC AMN classification.
- Consider a separate AMN-specific special rule if LACI will review models presented as IPC AMN classification support.



