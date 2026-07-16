# Template Feedback v2 - AI Flood Forecasts

## Why v2 Was Needed

The first-pass flood sample correctly classified the model as an environmental hazard forecast, but it was too compressed. It did not fully show the decision logic that a technically strong hazard model can still be only indirectly relevant to IPC.

## What v2 Corrects

- Restores the full Assess Card structure.
- Preserves all 19 screening questions with flag points.
- Makes the distinction between flood hazard skill and IPC evidence relevance explicit.
- Adds food-security transmission-pathway logic: hazard -> exposure -> impact -> IPC application.
- Adds basin reliability, ungauged-basin, return-period, lead-time, and user-facing uncertainty caveats.
- Adds Step 3 calibration needs for flood thresholds, exposure overlays, trigger rules, and communication guardrails.

## Template Refinements Surfaced by v2

- Add a `Food-Security Transmission Pathway` prompt to Assess Part 2 for all contributing-factor and hazard models.
- Add `Hazard Exposure and Vulnerability Fit` for environmental models.
- Add `Operational Product Version / Access Verification` for live external forecasting products.
- Add `Lead-Time and Threshold Fit` to clarify whether forecast timing matches the IPC application.



