# Geospatial Research Portfolio | Google Earth Engine

**Md. Abdul Aziz** · Remote Sensing · GIS · Google Earth Engine · Environmental Change

This repository presents exploratory geospatial research workflows and method-inspired applications built with Google Earth Engine. It is a **research-development portfolio**, not a collection of independently validated forest-disturbance maps or exact replications of all source papers.

## Featured study

### Exploring persistent tree-probability decline in Nijhum Dwip, Bangladesh

**[Open project overview, methods, code guide, and limitations](./01_Ota_DW_Forest_Disturbance/README.md)**

The featured project was inspired by Li, Ota and Mizoue (2024), *Attribution of forest disturbance types based on the Dynamic World class probability data: A case study of Myanmar* ([article](https://doi.org/10.1016/j.jag.2024.104216)). It explores annual Dynamic World class-probability time series, candidate tree-probability declines, possible land-cover transitions, and supporting Sentinel-2 inspection for Nijhum Dwip National Park.

**Project status:** exploratory adaptation; independent reference-data validation and verified disturbance-type attribution are not yet complete. Satellite probability change alone is **not** proof of forest loss or disturbance cause.

### Core files

| File | Role |
| --- | --- |
| [Project README](./01_Ota_DW_Forest_Disturbance/README.md) | Research motivation, methods, code guide, limitations |
| [02 — Annual 9-band analysis](./01_Ota_DW_Forest_Disturbance/02_Nijhum_Annual_9Band_Analysis) | Annual class-probability exploration |
| [03 — Tree-decline candidate search](./01_Ota_DW_Forest_Disturbance/03_Nijhum_Tree_Disturbance_Search) | Baseline-relative candidate detection and time series |
| **[04 — Main exploratory analysis](./01_Ota_DW_Forest_Disturbance/04_Nijhum_Forest_Disturbance_Exploratory.js)** | **Canonical English-commented exploratory workflow and sensitivity diagnostics** |

Additional scripts include earlier site-selection trials and older development versions. These are retained to show method development, not as separate validated results.

## Research evidence

The scripts contain maps, charts and area/sensitivity diagnostics generated inside the Earth Engine Code Editor. **No numerical findings, exported figures, accuracy statistics or validated disturbance areas are claimed in this repository overview until checked and documented.** A curated visual-results section will be added following quality control.

## Reproducibility and responsible interpretation

Open the [Earth Engine Code Editor](https://code.earthengine.google.com/), follow the [project instructions](./01_Ota_DW_Forest_Disturbance/README.md), check the study-area and time-window settings, and inspect GEE Console results and map layers. Sensitivity tests indicate how outputs vary with chosen thresholds; they do not replace independent accuracy assessment. Dynamic World predictions are themselves based on Sentinel-2 imagery, so Sentinel-2 visual checks are supporting context rather than independent ground truth.

## Contact / research interests

**Md. Abdul Aziz**  
MSc in Geography and Environmental Studies, University of Rajshahi, Bangladesh  
Research interests: satellite remote sensing, forest and land-cover dynamics, geospatial analysis, GIS modelling and Google Earth Engine.

*Work in progress. Methods, scripts and interpretations may be revised after validation.*
