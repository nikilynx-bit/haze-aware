# Data Sources for Singapore Haze Research

## 1. Air-Quality Monitoring (Singapore)

### 1.1 National Environment Agency (NEA)

| Dataset | Variables | Resolution | Access |
|---------|-----------|------------|--------|
| 1-hourly PSI & sub-indices (PM₂.₅, PM₁₀, SO₂, CO, NO₂, O₃) | 6 pollutants + composite PSI | 1-hr, 24-hr | [data.gov.sg](https://data.gov.sg) – API & CSV |
| PM₂.₅ mass concentration | µg/m³ | 1-hr | NEA API (`api.nea.gov.sg`) |
| Air Quality Index (AQI) bands | Categorical | 1-hr | NEA website / myENV app |

- **API endpoint (PSI):** `https://api.data.gov.sg/v1/environment/psi`
- **API endpoint (PM2.5):** `https://api.data.gov.sg/v1/environment/pm25`
- Licence: Singapore Open Data Licence.

### 1.2 NEA Air Quality Monitoring Network

- 11 monitoring stations island-wide.
- Continuous beta-attenuation / TEOM / gravimetric samplers.
- Data downloadable from [www.nea.gov.sg/our-services/pollution-control/air-quality](https://www.nea.gov.sg).

## 2. Satellite Remote Sensing

| Product | Provider | Variables | Spatial Res. | Temporal Res. |
|---------|----------|-----------|--------------|---------------|
| MODIS Active Fire (MCD14ML) | NASA FIRMS | Fire radiative power, confidence | 1 km | Daily (2×/day) |
| VIIRS Active Fire (VNP14IMGTDL_NRT) | NASA FIRMS | FRP, brightness temp | 375 m | ~12-hr |
| MODIS Aerosol Optical Depth (MCD19A2) | NASA LAADS | AOD @ 550 nm | 10 km / 1 km | Daily |
| Sentinel-5P TROPOMI | ESA / Copernicus | NO₂, CO, HCHO, SO₂ columns | 5.5 × 3.5 km | Daily |
| Himawari-8/9 AHI | JMA | AOD, smoke plume RGB | 2 km (SG region) | 10-min |
| CALIPSO / CATS | NASA / JAXA | Vertical aerosol profile | Lidar track | Overpass |

**Access portals:**
- NASA FIRMS: <https://firms.modaps.eosdis.nasa.gov>
- NASA LAADS DAAC: <https://ladsweb.modaps.eosdis.nasa.gov>
- Copernicus Open Access Hub: <https://dataspace.copernicus.eu>
- JMA Himawari: <https://www.jma.go.jp/msat_e/>

## 3. Meteorological Data

| Source | Variables | Notes |
|--------|-----------|-------|
| Meteorological Service Singapore (MSS) | Wind (speed/dir), RH, temp, rainfall | Station-level; request via MSS |
| ERA5 Reanalysis (ECMWF) | Full 3-D atmosphere, boundary layer, AOD proxy | 0.25°; Copernicus CDS |
| ASMC (ASEAN Specialised Meteorological Centre) | Regional wind fields, fire weather indices | Hosted in Singapore |
| NOAA HYSPLIT | Back-trajectories | Free; web or local install |

## 4. Fire and Land-Use Data (Source Regions)

| Dataset | Provider | Use |
|---------|----------|-----|
| Global Forest Watch (GFW) fire alerts | WRI / UMD | Near-real-time fire detections |
| GFED v4.1s | NASA / VU Amsterdam | Monthly burned-area & emissions |
| FINN (Fire INventory from NCAR) | NCAR | Daily emissions for CTM input |
| Copernicus Global Land Cover | ESA | Land-use / plantation mapping |
| Indonesian Ministry of Environment (KLHK) concession maps | KLHK | Overlay fires with permits |
| World Resources Institute (WRI) palm-oil concessions | WRI / GFW | Attribution analysis |

## 5. Health Data (Singapore)

| Dataset | Provider | Access |
|---------|----------|--------|
| Polyclinic attendances (ARI) | MOH / HPB | Aggregate; published weekly |
| Hospital admissions (respiratory, cardiovascular) | MOH | Restricted; ethics approval required |
| Mortality registry | MOH / Registry of Births & Deaths | Restricted |
| Emergency department visits | Public hospitals (SGH, NUH, etc.) | IRB / DOR approval |

## 6. Socio-Economic / Behavioural Data

- **data.gov.sg:** Transport ridership, school-closure records, N95 retail indices (ad hoc).
- **Google Trends / social-media archives:** Public response proxies.
- **LTA traffic data:** Congestion changes during haze.

## 7. Access Notes & Ethics

- NEA and data.gov.sg data are open; no registration required for API keys (as of 2024, confirm current policy).
- Satellite data (NASA, ESA) require free account registration.
- Health microdata require **SingHealth / NHG / MOH IRB** approval and data-sharing agreements.
- Indonesian concession data may have redistribution restrictions – check KLHK terms.

---

*Previous: [← Background](01-background.md) | Next: [Research Methods →](03-research-methods.md)*
