# Research Methods for Singapore Haze Studies

## 1. Atmospheric / Dispersion Modelling

| Approach | Typical Tools | Application |
|----------|---------------|-------------|
| Gaussian plume / box models | Custom scripts | First-order exposure estimation |
| Lagrangian particle dispersion | HYSPLIT, FLEXPART, NAME | Back-trajectory source attribution |
| Eulerian chemical transport models | WRF-Chem, GEOS-Chem, CMAQ | Regional PM₂.₅ forecasting, scenario analysis |
| Coupled fire–atmosphere models | CAWFE, WRF-Fire | Fire spread + smoke feedback |

**Singapore-specific considerations:**
- Domain should cover Sumatra, Kalimantan, Peninsular Malaysia, and the Singapore Strait.
- High-resolution (≤ 3 km) nesting around Singapore captures sea-breeze recirculation.
- Peat-smoke emission factors differ from surface-biomass factors (see Andreae & Merlet 2001; Akagi et al. 2011).

## 2. Remote-Sensing Analysis

- **AOD retrieval:** Use MODIS MCD19A2 or Himawari AHI AOD; validate against AERONET Singapore site (NUS) or SKYNET.
- **Fire detection & FRP:** Aggregate MODIS/VIIRS detections over concession boundaries to attribute fires to land-use type.
- **Smoke-plume tracking:** RGB composites (Himawari true colour, MODIS true colour) + CO / HCHO from TROPOMI.
- **Vertical structure:** CALIPSO 532-nm attenuated backscatter to distinguish elevated smoke layers from boundary-layer pollution.

## 3. Epidemiological Study Designs

| Design | Strengths | Typical Outcome |
|--------|-----------|-----------------|
| Time-series (daily counts vs PM₂.₅/PSI) | Controls long-term trend, seasonality | Acute respiratory / CVD admissions |
| Case-crossover | Within-person control; handles confounding by design | ED visits, mortality |
| Distributed lag non-linear models (DLNM) | Captures delayed effects | Hospitalisations |
| Cohort / panel studies | Individual-level exposure, effect modification | Lung function, symptoms |
| Interrupted time-series | Evaluates policy interventions (e.g., THPA) | Before/after comparison |

**Key covariates:** temperature, relative humidity, day-of-week, public holidays, influenza season.

## 4. Exposure Assessment

- Assign exposure by nearest monitoring station, inverse-distance weighting, or land-use regression (LUR).
- For transboundary episodes, combine ground PM₂.₅ with satellite AOD via statistical or ML fusion (random forest, geographically weighted regression).
- Personal-exposure sub-studies may use low-cost sensors (e.g., Plantower PMS5003) with calibration against TEOM.

## 5. Source Apportionment

- **Positive Matrix Factorization (PMF)** on filter-based PM₂.₅ chemical speciation (if available).
- **Receptor modelling** using trace-metal / levoglucosan / K⁺ markers.
- **Trajectory clustering** (HYSPLIT + k-means) to classify air-mass origin.
- **Isotopic tracers** (¹⁴C, ¹³C) to distinguish biomass burning from fossil-fuel combustion.

## 6. Economic & Policy Evaluation

- **Avoided-cost method:** Healthcare expenditure, lost productivity, school closures.
- **Contingent valuation / willingness-to-pay:** Survey-based valuation of visibility and health.
- **Difference-in-differences:** Compare outcomes in Singapore before/after Transboundary Haze Pollution Act (THPA, 2014) enforcement actions.
- **Event studies:** Stock-market reaction of affected sectors (airlines, tourism, construction).

## 7. Reproducibility & Code

- Prefer open-source stacks: Python (xarray, pandas, cartopy), R (tidyverse, mgcv, dlnm), CDO/NCO for NetCDF.
- Publish analysis code alongside data (Zenodo, GitHub).
- Report software versions, CRS (EPSG:4326 for geographic; EPSG:3414 SVTM for Singapore local), and random seeds.

## 8. Reporting Standards

- Follow **STROBE** (observational epi), **STROBE-ME** (molecular epi), or **GRADE** for evidence synthesis as appropriate.
- For modelling papers, report model evaluation statistics (MB, NME, r, FAC2) against ground truth.

---

*Previous: [← Data Sources](02-data-sources.md) | Next: [Policy Framework →](04-policy-framework.md)*
