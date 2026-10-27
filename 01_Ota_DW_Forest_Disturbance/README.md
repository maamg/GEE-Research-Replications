# Google Earth Engine Research Replications & Exploratory Studies

**Remote Sensing · Geospatial Analysis · Forest Change · Google Earth Engine**

This repository documents my learning-to-research workflow using **Google Earth Engine (GEE)**, satellite imagery, and geospatial analysis. The primary project explores whether **Dynamic World land-cover probability time series** can help identify and interpret potential forest/vegetation change in Bangladesh.

The emphasis is on **transparent methods, reproducible scripts, and careful interpretation**—not on claiming that exploratory change signals are independently verified forest-disturbance events.

> **Research status:** Exploratory / work in progress. The current analysis is an adaptation inspired by published research, **not a complete replication** of the original method. Independent reference-data validation and robust disturbance-type attribution remain future work.

## Featured project: Exploring tree-probability decline in Nijhum Dwip, Bangladesh

**Location:** Nijhum Dwip, Bangladesh  
**Platform:** Google Earth Engine (JavaScript API)  
**Core datasets:** Dynamic World V1; Sentinel-2 imagery; related spectral indices and quality-screening data

### Research motivation

Dynamic World provides per-pixel probabilities for nine land-cover classes rather than only a single categorical label. Investigating their temporal behavior may help flag locations showing sustained reductions in *tree* probability and examine whether other classes become more probable. Such patterns are **candidate change indicators**, not definitive evidence of deforestation or a specific disturbance cause.

### Current workflow

1. **Study-area and data inspection** — inspect available Dynamic World observations and land-cover probabilities.
2. **Annual probability summaries** — explore annual patterns across the nine Dynamic World classes.
3. **Candidate change screening** — examine changes in tree probability relative to a baseline and across subsequent years.
4. **Temporal diagnostics** — inspect repeated/persistent decline indicators, possible transitions, and time-series behavior.
5. **Supporting imagery and sensitivity checks** — inspect Sentinel-2 imagery and vegetation/water indices, and assess the effect of selected thresholds.

Some scripts also contain maps, charts, area summaries, and diagnostic outputs. **Their successful execution and scientific interpretation should be checked in GEE before any numerical result is cited.**

### Code guide

The following files are currently available in [`01_Ota_DW_Forest_Disturbance/`](./):

| Script | Purpose |
| --- | --- |
| [`01_AOI_DW_Inspection`](./01_AOI_DW_Inspection) | Initial study-area and Dynamic World inspection. |
| [`02_Probability_Preprocessing`](./02_Probability_Preprocessing) | Early probability-preprocessing exploration. |
| [`02_Nijhum_Annual_9Band_Analysis`](./02_Nijhum_Annual_9Band_Analysis) | Annual nine-class probability analysis for Nijhum Dwip. |
| [`03_Nijhum_Tree_Disturbance_Search`](./03_Nijhum_Tree_Disturbance_Search) | Tree-probability decline candidate screening. |
| **[`04_Nijhum_Forest_Disturbance_Exploratory.js`](./04_Nijhum_Forest_Disturbance_Exploratory.js)** | **Main exploratory script:** expanded temporal analysis and diagnostics. |

**Additional development material:** `03_Annual_Probability_TimeSeries` and `04_Bhawal_Disturbance_Candidates` document earlier site/method experiments. Two older Nijhum attribution files (`04_Nijhum_Disturbance_Attribution` and `_updated`) are retained as development versions and substantially overlap with the main exploratory script. The root-level `reformated_code` is an experimental draft, **not the validated implementation of the Dynamic World method**.

> **Why do some exploratory files mention different places?** The workflow evolved through site-selection trials (including Madhupur, Teknaf, Bhawal and others) before Nijhum Dwip was selected as the focus. Older headings or comments may retain trial-site names; these should not be taken as evidence that those scripts use an identical study area.

## How to explore the code

1. Open the [Google Earth Engine Code Editor](https://code.earthengine.google.com/) with an account authorized to use Earth Engine.
2. Open the relevant script from the table above and copy it into a GEE script, or access the corresponding script through a configured Earth Engine repository.
3. Review its study-area definition, dataset availability, baseline/analysis years, and parameters **before running**.
4. Run and inspect Console messages, map layers, charts, and any exported outputs; large analyses may require additional time or adjustment.
5. Treat threshold-based decline maps as **hypothesis-generating products** until checked against suitable independent reference data.

This GitHub repository contains code and research notes; it is **not a packaged software library or a released, validated geospatial dataset**. Some scripts may depend on study-area assets or settings that require adjustment in another GEE account.

## Methodological considerations and limitations

- **Probability is not land-cover area:** a drop in `trees` probability is not automatically equivalent to tree loss, deforestation, or a confirmed disturbance event.
- **Baseline-relative persistence:** a pixel flagged in consecutive years relative to the baseline does not necessarily show a new decline in each consecutive year.
- **Clouds, tides, water dynamics and seasonal effects:** these can complicate interpretation, particularly in coastal and island environments.
- **Resolution and aggregation:** annual summaries may suppress short events or mix observations from different seasons.
- **Validation:** Sentinel-2 visual/spectral inspection is useful context, but because Dynamic World is derived from Sentinel-2, it is **not fully independent ground truth**. Independent reference observations and an explicit sampling design are needed to quantify accuracy.
- **Disturbance attribution:** identifying a probability transition is not equivalent to establishing a disturbance mechanism or causal driver.

## Relationship to published research

This project was motivated by:

**Li, Ota & Mizoue (2024).** *Attribution of forest disturbance types based on the Dynamic World class probability data: A case study of Myanmar.* *International Journal of Applied Earth Observation and Geoinformation*. [Read the article](https://www.sciencedirect.com/science/article/pii/S1569843224005727).

The published study serves as **methodological inspiration**. The scripts here reflect my own learning, site experiments and exploratory adaptations; they should **not** be described as an exact implementation or reproduction of its full workflow, results, or accuracy assessment.

## Results and quality-control status

The present repository contains GEE scripts for maps, time-series charts, area summaries, year-of-decline diagnostics, and threshold-sensitivity analyses. **Curated figures and numerical output tables have not yet been checked and exported for this README.** Interpret all displayed maps as exploratory candidates until external reference data have been used to assess classification and disturbance-detection accuracy.

**Recommended evidence package (pending verification):**

1. Study-area location and 2017 high-tree-probability baseline (WDPA boundary).
2. Persistent candidate tree-probability decline, labelled explicitly as **baseline-relative screening**, not verified deforestation.
3. Selected location probability trajectories and supporting Sentinel-2 2023/2024/2025 imagery.
4. Drop-threshold (0.20/0.25/0.30) and baseline-threshold (0.55/0.60/0.65) sensitivity tables, with GEE QC differences (T25/B60 versus main calculation).

## Next steps

- Consolidate the current exploratory workflow into a concise, documented analysis script.
- Check study-area consistency, input-image counts, thresholds, and sensitivity outputs.
- Produce a small set of interpretable example maps and probability time-series figures.
- Design an independent reference-data sampling and validation procedure.
- Evaluate whether detected change candidates can be distinguished from seasonal, tidal, or classification-related variability.
- Develop a more rigorous forest-disturbance characterization workflow.

## Researcher

**Md. Abdul Aziz**  
MSc, Geography and Environmental Studies — University of Rajshahi, Bangladesh  
Research interests: Google Earth Engine, remote sensing, GIS, land-cover dynamics, forest monitoring, and geospatial modelling.

Experience includes geospatial data processing and GIS analysis in research and applied remote-sensing settings.

---

*This repository is a research-development portfolio. The code, interpretations and documentation may change as experiments are revised and validated.*
