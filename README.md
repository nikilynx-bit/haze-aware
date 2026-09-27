# 🌫️ Singapore Haze Research Hub

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Markdown Lint](https://github.com/<your-username>/sg-haze-research/actions/workflows/markdown-lint.yml/badge.svg)](https://github.com/<your-username>/sg-haze-research/actions/workflows/markdown-lint.yml)
[![DOI](https://zenodo.org/badge/XXXXXX.svg)](https://zenodo.org/badge/latestdoi/XXXXXX)

> A comprehensive, reproducible, and open-source knowledge base and computational toolkit for studying transboundary and local haze pollution in Singapore.

![Haze Banner](docs/assets/haze-banner.jpg) <!-- Add a striking satellite image of smoke over SG -->

## 🌟 Why this repository?

Most haze resources are either purely academic papers (hard to reproduce) or raw data portals (hard to contextualize). This repo bridges the gap by combining **deep domain knowledge** with **production-ready GIS and data science pipelines**.

### 🏗️ Architecture & Data Flow

```mermaid
graph TD
    A[Top-Tier Earth Obs] -->|NASA Earthdata| B(VIIRS/MODIS Fires)
    A -->|Copernicus CDS| C(Sentinel-5P TROPOMI)
    A -->|AWS Open Data| D(Himawari-8 AHI)
    E[Local Gov APIs] -->|data.gov.sg| F(NEA PM2.5 / PSI)
    E -->|MSS| G(Meteorological Data)
    
    B --> H((Python / GIS Engine))
    C --> H
    D --> H
    F --> H
    G --> H
    
    H -->|Spatiotemporal Fusion| I[Exposure Surfaces]
    I --> J[Epidemiological Analysis]
    I --> K[Source Attribution]
    I --> L[Policy Evaluation]

## Disclaimer

This repository is an academic reference. It does not constitute official guidance from the National Environment Agency (NEA), Ministry of Health (MOH), or any government body. Always verify current advisories at [www.nea.gov.sg](https://www.nea.gov.sg).
