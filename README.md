# Air Quality Philippines (GEE + Notebooks)

A practical, Philippines-first repository for studying air quality using **Google Earth Engine (GEE)** and reproducible **notebooks**. This repo is designed to be both a research workflow and a learning resource—helpful for students, early-career researchers, and practitioners who want to connect **satellite observations**, **meteorology**, and **air quality indicators**.

> **What this repo is:** A set of clean, reusable pipelines and notebooks for PH air quality analysis.  
> **What this repo is not:** A single “one-size-fits-all” PM₂.₅ product. Satellite-based proxies have limitations and should be interpreted carefully.

---

## What you can do here

- Build **monthly / seasonal summaries** of air-quality-relevant variables over a PH area of interest (AOI)
- Use **GEE scripts** to export clean CSV outputs (ready for Excel / R / Python)
- Explore Philippine-relevant drivers such as:
  - **Monsoon seasons and rainfall**
  - **Urban heat and land cover**
  - **Fire activity and smoke transport**
- Apply basic **QA/QC** practices (cloud screening, Sentinel-5P QA filters, minimum sample thresholds)

---

## Data sources (core)

This repo focuses on widely used, accessible datasets, especially those that work well in the Philippine context:

### Satellite / remote sensing
- **Sentinel-5P (TROPOMI)**: NO₂, SO₂, CO (use QA filtering; column measurements)
- **MODIS / MAIAC AOD**: aerosol optical depth (use with caution as a surface PM₂.₅ proxy)
- **VIIRS active fires / FRP**: fire activity for smoke-related analysis
- **Landsat / MODIS LST**: land surface temperature (useful for urban heat/UHI context)
- **Vegetation indices (e.g., NDVI)**: land cover / greenness context

### Meteorology & context
- **ERA5 / reanalysis**: winds, temperature, boundary-layer context (where applicable)
- **CHIRPS rainfall**: rainfall variability and wet/dry season contrasts (optional)

> Note: Satellite gas products are often **column-based** and may not directly represent surface concentrations. AOD is not PM₂.₅ by default—conversion requires assumptions and/or validation.

---

## Repository structure

air-quality-philippines/
├─ README.md
├─ notebooks/ # step-by-step analysis and explanation
├─ gee/
│ ├─ scripts/ # reusable GEE JS scripts
│ └─ exports/ # sample exported CSVs (small, shareable)
├─ data/
│ ├─ raw/ # keep local (gitignored)
│ └─ processed/
├─ figures/ # plots for the README/docs
├─ docs/ # glossary, QA/QC notes, PH context notes
└─ src/ # helper functions (python)


---

## Getting started

### Use Google Earth Engine scripts
- Open GEE Code Editor
- Import scripts from gee/scripts/
- Set your AOI (FeatureCollection asset or drawn polygon)
- Run exports → save CSV to Drive
