# Evidence Notes v2 - CERES Probabilistic Early Warning System

## Source

Primary source: `../sources/ceres.pdf`.

## Extracted Evidence Used

- Page 1: CERES generates 90-day ahead probability estimates of IPC Phase 3+, Phase 4+, and Phase 5 for 43 high-risk countries, updated weekly.
- Page 1: Inputs include CHIRPS, MODIS NDVI, ACLED, IPC classifications, WFP food consumption scores, and FAO/WFP cereal price indices.
- Page 1: Model uses logistic scoring with author-specified initial coefficients and perturbation intervals with n=2,000 draws.
- Page 1: Historical back-validation uses four IPC Phase 4-5 events selected for data completeness; paper explicitly says these are in-sample sanity checks, not prospective performance claims.
- Page 2: The term calibrated is used aspirationally; demonstrated calibration is planned after prospective data accumulates.
- Page 3-4: Current coefficients are author-specified initial values, not validated Bayesian priors, and use an 87-record IPC transition dataset.
- Page 4: Coefficient perturbation shows tier stability in 39 of 43 regions (91%) in the March 2026 reference run.
- Page 5-6: Pre-registered prospective evaluation protocol includes Brier Score, Brier Skill Score, TIER-1 precision/recall, sensitivity interval coverage, CRPS, and reliability diagrams with target dates and minimum N.
- Page 6: Back-validation includes Somalia July 2011, South Sudan February 2017, Ethiopia Tigray March 2022, and Yemen June 2021, all flagged TIER-1.
- Page 6: In-sample Brier scores: CERES 0.0066, persistence 0.0494, climatological 0.2275, uninformative 0.2500.
- Page 7-8: Limitations include author-specified coefficients, AUC 0.84 on an approximately 17-case held-out split with CI [0.63, 1.00] consistent with chance performance, underestimated sensitivity intervals, country-level resolution, data gaps, structural drivers not modeled, and single-author design.
- Page 10: CERES is not a replacement for FEWS NET, IPC, or WFP HungerMap; it is described as an automated probabilistic layer pending public verification.

## Typology Evidence

CERES directly outputs IPC Phase 3+, Phase 4+, and Phase 5 probabilities. Under LACI, this is an IPC Outcome Modeling / IPC-Indicative and proxy-trained/direct IPC-derived food security output. It is one of the highest-risk categories for misinterpretation.

## Evidence Boundaries

- This sample is based only on the PDF, not live API verification.
- Prospective performance results were not available in the paper.
- The back-validation results are explicitly in-sample sanity checks and should not be treated as evidence of prospective skill.



