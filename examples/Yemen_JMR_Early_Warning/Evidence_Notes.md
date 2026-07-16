# Evidence Notes v2 - Yemen Data-Driven Early Detection Model

## Source

Primary source: `../sources/A Data-Driven Approach for Early Detection of Food Insecurity in Yemen.pdf`.

Duplicate source also exists under `../sources/`.

## Extracted Evidence Used in v2

- Page 1: The source is World Bank Policy Research Working Paper 10768, May 2024.
- Page 5: The paper situates FEWS NET and IPC as major systems for tracking food insecurity risks in Yemen.
- Page 6: The target-variable section states that the paper aims to predict transitions into critical food insecurity states using observable indicators.
- Page 6-7: Historical FEWS NET IPC-compatible data cover 333 districts from October 2014 to July 2023.
- Page 7: The application focuses on preventing transition from IPC Phase 3 to IPC Phase 4. Phase 4 or 5 is coded as emergency status.
- Page 16-17: The paper reports GLM/logit modeling, recursive feature elimination, and cross-validated balanced accuracy for indicator combinations.
- Page 23: The paper notes limits of data-driven approaches, including dependency on data quality/availability and the need for continuous refinement as ground realities change.

## Typology Evidence

This sample treats the model as an IPC-Indicative Model and Proxy-Trained Food Security Output because the target is FEWS NET IPC-compatible emergency transition status. The model estimates food security emergency risk using contributing factors, but the target/output relationship is food-security-proxy trained.

## Evidence Boundaries

- The sample does not verify the latest implementation, code repository, dashboard, or operational version.
- The sample does not constitute an IPC technical audit.
- Context-specific judgments are illustrative unless completed by IPC-GSU, country/regional analysts, and IPC-LACI Team for a real IPC context.
## Supplemental Operational Metadata Used in Checklist Demo

- JMR Yemen metadata version: 2026-07-15, with data cut-off 2026-07-15.
- Operational coverage: Yemen, 22 Admin 1 areas and 335 Admin 2 areas using the COD administrative-boundary standard.
- Temporal cadence: monthly time series from 2010-01-01 to 2026-03-01.
- Operational components: raw data, transformed indicators, binary alerts, alert levels, and population exposure estimates.
- Alert levels: Typical, Heightened, and Critical risks of escalation.
- Threshold logic: transformed indicators use approaches such as z-scores, moving-average divergences, and RSI; Heightened/Critical thresholds are calibrated against historical food insecurity escalations with different false-negative/false-positive emphases.
- Population exposure estimates: generated through GLM/WMLE using probability-weighted populations; WorldPop yearly population grids are aggregated to Admin 2 and held constant monthly within year.
- Boundary/version reconciliation note: the method paper evidence used earlier refers to 333 districts, while the JMR operational metadata for version 2026-07-15 records 335 Admin 2 areas. Any real IPC use must reconcile the exact boundary version, unit list, and crosswalk before analyst-facing consideration.






