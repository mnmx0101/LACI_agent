# JMR Yemen Operational Details

**Source status:** User-provided pasted metadata from the World Bank Microdata Library record for `YEM_2010-2025_JMR_v01_M`, Joint Food Security Monitor - Yemen.

**Stored for LACI use:** This source note supplements the Yemen Data-Driven Early Detection method paper and should be used when completing the Yemen Learn Card, Assess Card, and IPC Analysis Use Checklist.

## LACI Extraction Summary

- Dataset: Joint Food Security Monitor / Joint Monitoring Report (JMR) data for Yemen.
- Version: 2026-07-15, based on July 2026 Joint Food Security Monitor.
- Data cut-off: 2026-07-15, with publication-delay caveat by source.
- Coverage: Yemen, 22 Admin 1 areas and 335 Admin 2 areas.
- Geographic standard: subnational Admin 2 using COD administrative boundaries.
- Temporal structure: monthly time series, 2010-01-01 to 2026-03-01.
- Output components: raw data, transformed indicators, binary alerts, and population exposure estimates.
- Alert levels: Typical, Heightened, and Critical risks of escalation.
- Threshold method: transformed indicators are thresholded to anticipate historical food insecurity escalations; Heightened and Critical thresholds are calibrated with different false-negative/false-positive emphases.
- Population exposure estimates: binary alerts and lagged indicators feed a GLM estimated with weighted maximum likelihood; weights are calibrated to historical country-level population totals exceeding IPC cutoff phases.
- Data processing: FEWS NET livelihood-zone data are transformed to Admin 2 using population percentages; WorldPop yearly population grids are aggregated to Admin 2 and held constant monthly; ACLED, IOM displacement, rainfall, exchange rates, food prices, and fuel prices are mapped or aggregated to monthly Admin 2 series.
- LACI implication: this metadata improves spatial/temporal and threshold documentation, but does not remove the need for IPC-cycle-specific review, IPC-LACI Team verification, source-specific latest-input dates, current context review, and non-use guardrails for IPC classification and official population estimates.

## Original Pasted Metadata

```textIdentification
Survey ID number
YEM_2010-2025_JMR_v01_M

Title
Joint Food Security Monitor

Subtitle
Yemen, 335 areas, 2010-01-01 - 2026-03-01, version 2026-07-15

Abbreviation or Acronym
Joint Monitoring Report (JMR) data

Country/Economy
Name	Country code
Yemen	YEM
Study type
Ongoing food security assessement in Yemen

Series Information
The Joint Food Security Monitor country pages provide live datasets compiled and updated monthly by the World Bank–led Joint Monitoring Report (JMR) team. These datasets draw on publicly available food-security-related data and statistical modeling techniques.

Each dataset provides a combination of raw data, transformed indicators, binary alerts, and population exposure estimates. The alerts are raised using the transformed indicator data at thresholds that best anticipate historical food insecurity escalations. The alert levels are categorized as Typical (no alert), Heightened, or Critical risks of escalation. The population estimates are generated using regression techniques.

The datasets are continually updated and refined as new data become available.

The following country pages are part of this series:

• World: https://microdata.worldbank.org/index.php/catalog/study/WLD_2010-2025_JMR_v01_M
• Afghanistan: https://microdata.worldbank.org/index.php/catalog/study/AFG_2010-2025_JMR_v01_M
• Burkina Faso: https://microdata.worldbank.org/index.php/catalog/study/BFA_2010-2025_JMR_v01_M
• Cameroon: https://microdata.worldbank.org/index.php/catalog/study/CMR_2010-2025_JMR_v01_M
• Democratic Republic of the Congo: https://microdata.worldbank.org/index.php/catalog/study/COD_2010-2025_JMR_v01_M
• Ethiopia: https://microdata.worldbank.org/index.php/catalog/study/ETH_2010-2025_JMR_v01_M
• Haiti: https://microdata.worldbank.org/index.php/catalog/study/HTI_2010-2025_JMR_v01_M
• Kenya: https://microdata.worldbank.org/index.php/catalog/study/KEN_2010-2025_JMR_v01_M
• Mali: https://microdata.worldbank.org/index.php/catalog/study/MLI_2010-2025_JMR_v01_M
• Mozambique: https://microdata.worldbank.org/index.php/catalog/study/MOZ_2010-2025_JMR_v01_M
• Malawi: https://microdata.worldbank.org/index.php/catalog/study/MWI_2010-2025_JMR_v01_M
• Niger: https://microdata.worldbank.org/index.php/catalog/study/NER_2010-2025_JMR_v01_M
• Nigeria: https://microdata.worldbank.org/index.php/catalog/study/NGA_2010-2025_JMR_v01_M
• Sudan: https://microdata.worldbank.org/index.php/catalog/study/SDN_2010-2025_JMR_v01_M
• Somalia: https://microdata.worldbank.org/index.php/catalog/study/SOM_2010-2025_JMR_v01_M
• South Sudan: https://microdata.worldbank.org/index.php/catalog/study/SSD_2010-2025_JMR_v01_M
• Chad: https://microdata.worldbank.org/index.php/catalog/study/TCD_2010-2025_JMR_v01_M
• Yemen: https://microdata.worldbank.org/index.php/catalog/study/YEM_2010-2025_JMR_v01_M

Abstract
This dataset provides high-frequency food security alerts and metrics of key indicators relevant to food security crises, offering critical insights into localized risks in areas prone to food insecurity. The dataset includes metrics such as food price inflation, agricultural productivity shocks, and economic indicators, designed to support the identification of emerging food crises.

Generated using a data-driven approach, food security alerts are calibrated for accuracy and reliability, capturing granular trends often missed by traditional, infrequently updated assessments. The dataset aims to enhance the ability of policymakers, humanitarian organizations, and researchers to monitor and respond to food security risks promptly, supporting proactive interventions to mitigate impacts on vulnerable populations.
Kind of Data
Alert levels for each indicator that drives food insecurity in Yemen, where the level can be Typical (no alert raised), Heightened or Critical

Unit of Analysis
Sub-national level, admin 2, monthly basis

Version
Version Date
2026-07-15

Version Responsibility Statement
Joint Monitoring Report (JMR) team

Version Notes
This version is based on the Joint Food Security Monitor of July 2026. Data cut-offs for the are set to July 15, 2026. The data do generally not reflect the impact of events up to the cut-off date as there is varying delay with which official data is published. Joint Food Security Monitor data are not directly comparable across different versions. Indicators are selected based on data availability and may be revised to improve the performance in predicting food security deteriorations using calibration methods outlined by Penson et al. (2024). Consequently, alert thresholds are also re-evaluated based on the updated data and may change over time. Historical versions of Joint Food Security Monitor data are preserved for transparency and research purposes.

Scope
Notes
The indicator groups selected by the model for Yemen, with their respected possible indicators are:

Conflict: conflict fatalities, conflict fatalities neighbouring areas
Displacements: displacements to, displacements from
Drought - rainfall: rainfall
Exchange rates: exchange_rate_unofficial, milling_cost_wheat, wage_non_qualified_labour, wage_qualified_labour
Food prices: beans, eggs, lentils, livestock_sheep_two_year_old_male, meat_chicken_fao, meat_mutton_fao, millet_fao, oil, oil_fao, onions, onions_fao, peas, potatoes, rice, salt, sorghum_fao, sugar, tomatoes, wheat, wheat_flour, food_price_index
Fuel prices: fuel_diesel, fuel_gas, fuel_petrol_gasoline
Volatility - Exchange rate: exchange_rate_unofficial, milling_cost_wheat, wage_non_qualified_labour, wage_qualified_labour
Volatility - Food prices: beans, eggs, lentils, livestock_sheep_two_year_old_male, meat_chicken_fao, meat_mutton_fao, millet_fao, oil, oil_fao, onions, onions_fao, peas, potatoes, rice, salt, sorghum_fao, sugar, tomatoes, wheat, wheat_flour, food_price_index
Volatility - Fuel prices: fuel_diesel, fuel_gas, fuel_petrol_gasoline

Keywords
Yemen Joint Monitoring Report Integrated Food Security Phase Classification Threshold modeling FEWS NET Food prices Drought - rainfall Volatility - Food prices Volatility - Fuel prices Exchange rates Fuel prices Displacements Volatility - Exchange rate Conflict
Coverage
Geographic Coverage
Yemen, down to sub-national level, 22 admin 1 areas and 335 admin 2 areas

Geographic Coverage notes
The sub-national levels follow the COD standard (https://knowledge.base.unocha.org/wiki/spaces/imtoolbox/pages/2557378679/Administrative+Boundaries+COD-AB)

Geographic Unit
Sub-national level, admin 2

Producers and sponsors
Primary investigators
Name	Affiliation
Lomme, Mathijs	World Bank, Development Data Group (DECDG)
Andrée, Bo Pieter Johannes	World Bank, Development Data Group (DECDG)
Funding Agency/Sponsor
Name	Grant number	Role
World Bank's Food Systems 2030	TF0C0728	Support to methodological development. Support to data analytics. Data documentation and dissemination. Expansion of coverage and maintenance.
World Bank's Food Systems 2030	TF0C0828	Support to methodological development. Support to data analytics. Data documentation and dissemination. Expansion of coverage and maintenance.
Other Identifications/Acknowledgments
Name	Affiliation	Role
IPC	iNGO	Multi-partner
FEWS NET	USAID	Source of FEWS NET IPC data
ACLED	iNGO	Source of conflict data
FAO	United Nations	JMR drafting team
Source of market prices
Source of the Agricultural Stress Index
OCHA	United Nations	Source of administrative boundaries data
WFP	United Nations	JMR drafting team
Source of market prices
Source of Rainfall data
Source of NDVI data
UNICEF	United Nations	JMR drafting team
WHO	United Nations	JMR drafting team
ACAPS	Non-profit, non-governmental project	JMR drafting team
WorldPop	School of Geography and Environmental Science, University of Southampton	Source of population data
FEWS NET	United States Agency for International Development, and the US Department of State	Source of food insecurity data
Survey instrument
Methodology notes
The Joint Food Security Monitor datasets consist of four components: raw data, transformed indicators, binary alerts, and population exposure estimates. The transformation and alert framework is developed by Penson et al. (2024). For each indicator, multiple transformation methods and time windows are evaluated, and the best-performing ones are automatically selected. These transformations normalize time-varying risk into a stable range and include methods such as z-scores, moving average divergences, and the Relative Strength Index (RSI).

Alert levels (Heightened or Critical) are determined by applying thresholds to the normalized indicators so as to best reproduce historical food insecurity patterns. Thresholds are optimized by minimizing a loss function that balances the False Positive Rate (FPR) and the False Negative Rate (FNR). The loss formulations follow Andrée et al. (2020). The Heightened threshold minimizes the weighted loss with a two-thirds emphasis on false negatives, while the Critical threshold uses a more conservative calibration that places a two-thirds weight on false positives.

Binary alerts from different indicators are combined into a Generalized Linear Model (GLM) to produce population-at-risk estimates. The GLM is estimated using weighted maximum likelihood estimation (WMLE). The weights are calibrated so that the sum of probability-weighted populations best matches each country’s historical total of populations exceeding IPC cutoff phases.

Across the literature, several approaches exist. Andrée et al. (2020) develop a GLM using lagged continuous indicator data and optimize it for prediction of escalations only, defined as transitions from non-critical IPC phases. Training and validation are done on panel data to ensure sufficient escalation events. Penson et al. (2024) develop a GLM using only binary alerts, trained and validated against escalation events. Gbadegesin, Andrée, and Braimoh (2024) fit a GLM using lagged continuous indicators in Afghanistan against all phase data rather than escalation events only.

Because the Joint Food Security Monitor spans many countries with differing prevalence of escalation events, these methods are unified into a hybrid framework. In the first stage, recursive feature elimination (RFE) is used to select binary alerts following the Penson et al. (2024) approach. In the second stage, lagged continuous indicators from the Andrée and Gbadegesin models are added, while keeping the binary indicators fixed, and RFE is reapplied. The calibration and validation frameworks are also unified. Specifically, the escalation-only validation logic of Andrée and Penson is merged with the full-sample validation of Gbadegesin by combining loss functions as follows: loss1 = 1 - x / log(2), where x = w loss(escalations) + (1 - w) loss(all), and w = log(N_escalations) / log(N_all). When escalation events are scarce, this combined loss approximates that of Gbadegesin et al. (2024), while when escalation events are plentiful, it converges toward Andrée et al. (2020) and Penson et al. (2024).

The final GLM is estimated using WMLE with positive-class weights calibrated to match historical country-level population totals. A second loss function, loss2 = 1 - (pooled_rmse^2) / (pooled_rmse_baseline^2), measures fit between estimated and observed country-level population exposures, pooling values above and below the median. This acts as a balanced pseudo R-squared, sensitive to errors in both high and low exposure regimes.

The overall loss combines loss1 (admin-level balanced loss) and loss2 (country-level balanced loss). The weights are determined by effective sample sizes that account for spatial and temporal correlation: N_eff = N / (1 + (N - 1) rho_s) and T_eff = T / (1 + (T - 1) rho_t). The combined loss is calculated as loss = 1 - sqrt(w (1 - loss1)^2 + (1 - w) (1 - loss2)^2), where w = N_eff / (N_eff + T_eff). This mirrors the weighted error logic of Andrée et al. (2020). When the time series is short, model optimization prioritizes cross-sectional fit (loss1); when the time series is long, it prioritizes temporal consistency (loss2). The correlation adjustments prevent over-weighting in cases where many administrative units are identical (e.g., due to coarse IPC assessment levels) or where country-level totals vary little over time.

References:
Andrée, B. P. J., Chamorro, A., Spencer, P., Kraay, A., & Wang, D. (2020). Predicting food crises (Policy Research Working Paper No. 9412). World Bank. https://hdl.handle.net/10986/34510
Gbadegesin, T. K., Andrée, B. P. J., & Braimoh, A. (2024). Climate shocks and their effects on food security, prices, and agricultural wages in Afghanistan (Policy Research Working Paper No. 10999). World Bank. https://hdl.handle.net/10986/42552
Penson, S., Lomme, M., Carmichael, Z., Manni, A., Shrestha, S., & Andrée, B. P. J. (2024). A data-driven approach for early detection of food insecurity in Yemen’s humanitarian crisis (Policy Research Working Paper No. 10768). World Bank. https://hdl.handle.net/10986/41534

Data collection
Dates of Data Collection
Start	End	Cycle
2010-01-01	2026-03-01	monthly
Time Method
time-series

Frequency of Data Collection
monthly

Time periods
Start date	End date	Cycle
2010-01-01	2026-03-01	monthly
Sources
Data source	Origin of source
ACLED CONFLICT	ACLED (Armed Conflict Location and Event Data), is an independent, impartial, international non-profit organization collecting data on violent conflict and protest in all countries and territories in the world.Main page: https://acleddata.com/api. Country page: https://acleddata.com/country/Yemen
IOM IDP RAPID	Rapid displacements of internally displaced households. We keep track of both the number of households to and from admin 2 areas.Main page: https://dtm.iom.int/yemen#producttabs. Country page: https://dtm.iom.int/yemen#producttabs
WFP RAINFALL	WFP publishes this dataset on HDX, where it contains dekadal rainfall indicators computed from Climate Hazards Group InfraRed Precipitation satellite imagery with insitu Station data (CHIRPS) version 2, aggregated by subnational administrative units.Main page: https://data.humdata.org/dataset/?dataseries_name=WFP+-+Rainfall+Indicators+at+Subnational+Level. Country page: https://data.humdata.org/dataset/yem-rainfall-subnational
WORLD BANK EXCHANGE RATES	The World Bank's Real Time Exchange Rates, contains monthly exchange rate estimates by product and market, using FAO and WFP data as input.Main page: https://microdata.worldbank.org//api/downloads. Country page: https://microdata.worldbank.org/catalog/6159
WORLD BANK FOOD PRICES	The World Bank's Real Time Food Prices, contains monthly food price estimates by product and market, using FAO and WFP data as input.Main page: https://microdata.worldbank.org//api/downloads. Country page: https://microdata.worldbank.org/catalog/4508
WORLD BANK FUEL PRICES	The World Bank's Real Time Energy Prices, contains monthly fuel price estimates by product and market, using FAO and WFP data as input.Main page: https://microdata.worldbank.org//api/downloads. Country page: https://microdata.worldbank.org/catalog/6133
Data processing
Data Processing
Type	Description
FEWS NET	Data is provided by livelihood zone, which is transformed to admin level 2 areas by using the population percentages in the different livelihood zones. The IPC phases are rounded to the nearest integer adjusted for whether or not humanitarian assistance was available in that admin level 2 area.
WorldPop	Data is provided in .tif files on a yearly basis. The gridded data is aggregated to the admin level 2 areas by taking the sum by area. Monthly population numbers are kep constant throughout each year.
ACLED CONFLICT	All events contain a date, a lat/lon location and the number of fatalities. We map the lat/lon locations to an admin level 2 area and we aggregated to a monthly level per admin level 2 area by taking the sum of the total fatalities. Additionally, we keep track of neighbouring conflict by taking the sum of all fatalities in directly neighbouring admin level 2 areas per admin level 2 area.
IOM IDP RAPID	The weekly IOM reports about rapid displacements in Yemen is aggregated to a monthly level and per admin 2 area. We keep track of the number of households moving to and from this area.
WFP RAINFALL	The average rainfall per dekad, which is given in mm by admin level 2 area by dekad, is aggregated to a monthly level by taking the average. Likewise, we keep track of the total rainfall and the maximum rainfall per month per area. Admin level 2 areas with missing data are filled in by taking the average rainfall of all direct neighbouring admin level 2 areas.
WORLD BANK EXCHANGE RATES	Exchange rates are provided on a monthly basis for various markets. These markets are mapped onto admin level 2 areas using their lat/lon coordinates. Admin 2 areas without a market take the average of all markets found in the corresponding admin 1 area. If there are still admin 2 areas with missing exchange rates, we take the average of all neighbouring admin 2 areas.
WORLD BANK FOOD PRICES	Food prices are provided on a monthly basis for various markets. These markets are mapped onto admin level 2 areas using their lat/lon coordinates. Admin 2 areas without a market take the average of all markets found in the corresponding admin 1 area. If there are still admin 2 areas with missing food prices, we take the average of all neighbouring admin 2 areas.
WORLD BANK FUEL PRICES	Fuel prices are provided on a monthly basis for various markets. These markets are mapped onto admin level 2 areas using their lat/lon coordinates. Admin 2 areas without a market take the average of all markets found in the corresponding admin 1 area. If there are still admin 2 areas with missing fuel prices, we take the average of all neighbouring admin 2 areas.
Quality standards
Standard compliance
World Bank Group. (2024). Development Data Quality Policy. https://ppfdocuments.azureedge.net/de65051a-a1ee-410e-aba8-9c302f59be2f.pdf

Access policy
Location of Data Collection
World Bank Microdata Library, JMR Collection

URL for Location of Data Collection
https://microdatalib.worldbank.org

Number of Files
4 per country page

Data Access
Access authority
Name	Affiliation	Email
Data Help Desk	World Bank, Development Data Group	https://datahelpdesk.worldbank.org/
Citation requirements
Please cite this dataset as follows: Lomme, M. and Andrée, B. P. J. (2025). Joint Food Security Monitor - Yemen (Version 2026-07-15). YEM_2010-2025_JMR_v01_M. Washington, DC: World Bank Microdata Library. DOI: TBC

Restrictions
The values presented in these datasets are all based on publicly-available data.
The datasets are published as open data.

Disclaimer and copyrights
Disclaimer
The JMR data and metadata provided as is and as available, and every effort is made to ensure their timeliness, accuracy, and completeness. When errors are discovered, they are corrected as appropriate and feasible. For details on the terms and conditions for usage of the JMR database, please refer to the license details

Copyright
For details on the terms and conditions for usage of the data, please refer to the Terms and Conditions when accessing the microdata.

Contacts
Contacts
Name	Affiliation	Email
Data Help Desk	World Bank, Development Data Group	https://datahelpdesk.worldbank.org/
Metadata production
DDI Document ID
YEM_2010-2025_JMR_v01_M

Producers
Name	Affiliation	Role
Mathijs Lomme	World Bank, Development Data Group (DECDG)	Lead modeler
Bo Pieter Johannes Andrée	World Bank, Development Data Group (DECDG)	Technical lead
Zacharey Carmichael	World Bank, Agriculture and Food Global Practice	Technical coordinator
Steve Penson	World Bank, Agriculture and Food Global Practice	Co-investigator
Date of Metadata Production
2026-07-15

Metadata version
Version date
2026-07-15

Version responsibility
Joint Monitoring Report (JMR) team

Version notes
This version is based on the Joint Food Security Monitor of July 2026. Data cut-offs for the are set to July 15, 2026. The data do generally not reflect the impact of events up to the cut-off date as there is varying delay with which official data is published. Joint Food Security Monitor data are not directly comparable across different versions. Indicators are selected based on data availability and may be revised to improve the performance in predicting food security deteriorations using calibration methods outlined by Penson et al. (2024). Consequently, alert thresholds are also re-evaluated based on the updated data and may change over time. Historical versions of Joint Food Security Monitor data are preserved for transparency and research purposes.
```



