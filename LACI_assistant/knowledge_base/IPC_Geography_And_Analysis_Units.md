# IPC Geography Anchor: GAUL, ADM1/ADM2, and LACI Spatial Fit

**Status:** user-confirmed operational anchor, pending later verification against IPC platform implementation documentation.

## Confirmed Working Rule

IPC currently uses **GAUL as the default geographic system** for IPC geographic units. IPC analyses commonly use **ADM1 and ADM2** units, but the unit of analysis can vary depending on decision needs, data availability, feasibility, access, and the specific IPC analysis design.

## IPC Manual Context

The IPC Manual states that IPC can classify food insecurity and malnutrition in any administrative unit or geographic area when minimally adequate and representative evidence is available. It also states that the Technical Working Group should define the unit of analysis, geographic coverage, and validity period during planning and confirm the unit/geographic scope during preparation.

The manual also emphasizes that population tables should be disaggregated at the relevant administrative level or other unit used in the analysis, and communication products may aggregate findings at the most suitable administrative subdivision when needed for readability.

## LACI Implications

For any Learn Card, Assess Card, or IPC Analysis Use Checklist:

- Record whether the model uses GAUL, GADM, OCHA P-code, ISO, raster/grid, latitude/longitude, or a custom boundary system.
- Record the boundary version/date where available.
- Record the native model unit and the reporting/output unit separately.
- Record whether a crosswalk is required between model units and IPC analysis units.
- Treat missing geography/coding/crosswalk information as a material fit problem, not a cosmetic metadata gap.
- Do not assume ADM1/ADM2 alignment just because a model says it is district-level or admin-level.

## Special Caution For Model Outputs

A model output may be technically useful but operationally unusable for IPC if its geography cannot be matched to the IPC unit of analysis. National, coarse-grid, market-point, livelihood-zone, district, ADM, and IPC analysis-area units are not interchangeable without an auditable crosswalk.

## Source Notes

- User confirmation, 2026-07-16: IPC currently uses GAUL as default geographic system and commonly ADM1/ADM2, with variation depending on needs.
- IPC Technical Manual v3.1, using source-library extracts around key features and analysis-cycle planning.
- Official IPC Manual page: `https://www.ipcinfo.org/ipcinfo-website/resources/ipc-manual/en/`.




