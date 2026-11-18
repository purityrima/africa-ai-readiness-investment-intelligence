# Project Metadata

**Project:** AI-Readiness Investment Intelligence for Africa  
**Project type:** Exploratory Data Science and Unsupervised Machine Learning  
**Last updated:** 18 November 2026  
**Status:** Model evaluation completed; geographical analysis pending.

## 1. Project Overview

This project investigates multidimensional infrastructure and socioeconomic characteristics of African urban centres to identify exploratory urban infrastructure profiles relevant to preliminary AI-readiness investment screening.

The analysis applies unsupervised machine learning to identify similarities and differences among urban centres. The resulting clusters are not independently validated AI-readiness categories, investment rankings or assessments of project bankability.

## 2. Analytical Dataset

| Property | Description |
|---|---|
| Geographical coverage | Africa |
| Unit of analysis | Urban centre |
| Number of observations | 2,172 |
| Original dataset columns | 16 |
| Identification variables | 3 |
| Clustering predictors | 12 |
| Supplementary indicators | 1 |
| Cluster-assignment columns | 3 |
| Final exported dataset | 2,172 rows × 19 columns |
| Primary clustering configuration | K-Means, k = 3 |
| Comparison configurations | K-Means, k = 2 and k = 6 |

**Final dataset location:** `data/processed/urban_centres_cluster_assignments.csv`

## 3. Data Sources

### Global Human Settlement Layer (GHSL)

The GHSL Urban Centre Database R2024A provides demographic, socioeconomic, infrastructure and environmental indicators used in the analysis.

The selected variables include urban population, average GDP, educational attainment, infrastructure coverage, road density, solar photovoltaic potential and annual mean temperature.

### International Telecommunication Union (ITU)

ITU terrestrial fibre-infrastructure information was used to derive an approximate fibre-distance-band indicator for urban centres.

This variable represents encoded distance categories rather than continuously measured distances.

### PeeringDB

The dataset retains `peeringdb_facility_count`, representing the number of PeeringDB-listed facilities associated with an urban centre.

This indicator provides supplementary information on registered digital-infrastructure presence. It was not included among the 12 clustering predictors.

The original rationale for excluding PeeringDB from modelling should be verified against the feature-selection documentation before a definitive methodological explanation is provided.

## 4. Dataset Variables

### Identification variables

- `ID_UC_G0` — Urban-centre identifier
- `GC_UCN_MAI_2025` — Urban-centre name
- `GC_CNT_GAD_2025` — Country

### Demographic and socioeconomic predictors

- `GH_POP_TOT_2025` — Urban population
- `SC_GDP_AVG_2020` — Average GDP (PPP)
- `SC_SEC_SYT_2020` — Mean years of schooling (25+)

### Infrastructure and connectivity predictors

- `IN_CIS_ENE_2020` — Energy infrastructure index
- `IN_CIS_TEL_2020` — Telecommunications infrastructure index
- `fibre_distance_band_km` — Terrestrial fibre-distance band
- `IN_CIS_TRA_2020` — Transport infrastructure index
- `IN_ROA_DEN_2024` — Road network density
- `IN_CIS_EDU_2020` — Education infrastructure index
- `IN_CIS_WAT_2020` — Water infrastructure index

### Environmental and renewable-energy predictors

- `CL_REN_PVO_2020` — Daily solar photovoltaic potential
- `CL_B01_CUR_2010` — Annual mean temperature

### Supplementary indicator (excluded from clustering)

- `peeringdb_facility_count` — PeeringDB facility count

Detailed definitions and interpretation notes are documented in `notebooks/03_model_evaluation.ipynb`.

## 5. Data Preprocessing

The clustering feature set contains 12 predictors.

Preprocessing includes:

- Base-10 logarithmic transformation of urban population and average GDP.
- Median-scaled `log1p` transformations of five sector-specific infrastructure indices.
- Retention of the remaining predictors without additional variable-specific transformation.
- StandardScaler standardization of all 12 predictors before clustering.

The fibre-distance indicator includes encoded distance-band approximations, including a provisional value of 125 km for the category exceeding 100 km.

The exported analytical dataset retains the original indicator values and the selected cluster assignments.

Detailed preprocessing steps are documented in `notebooks/01_data_preparation.ipynb`.

## 6. Clustering and Model Evaluation

The project compares K-Means and Ward agglomerative clustering across shortlisted configurations of k = 2, 3 and 6.

Evaluation considers internal clustering metrics, initialization stability, subsampling stability and interpretability of cluster profiles.

**Selected configuration:** K-Means with k = 3.

The selected configuration contains:

| Cluster identifier | Urban centres |
|---|---:|
| 0 | 522 |
| 1 | 1,380 |
| 2 | 270 |
| **Total** | **2,172** |

The k = 2 and k = 6 solutions are retained for comparative and sensitivity analysis.

Cluster identifiers are arbitrary categorical labels. They do not imply a hierarchy, readiness ranking or investment priority.

## 7. Cluster Assignment Outputs

The final exported dataset includes three additional variables:

- `KMeans_k2`
- `KMeans_k3`
- `KMeans_k6`

These columns record cluster membership under the three shortlisted K-Means configurations. They are modelling outputs, not clustering predictors.

## 8. Important Methodological Limitations

- Clustering identifies patterns of similarity, not independently validated AI readiness.
- GHSL infrastructure indices describe spatial infrastructure characteristics and should not automatically be interpreted as service reliability.
- Average GDP is not GDP per capita.
- Mean years of schooling is not a direct measure of AI-specific skills.
- Solar PV potential does not represent installed renewable-energy capacity.
- Annual mean temperature is not a direct measure of future heat stress.
- PeeringDB-listed facilities do not directly measure available computing capacity.
- The fibre-distance-band variable is an approximation rather than a continuous observed distance.
- Indicator reference years do not necessarily represent the observation dates of every underlying input.
- Investment suitability requires additional evidence, contextual assessment and explicitly defined decision criteria.

## 9. Reproducibility and Project Files

| File | Purpose |
|---|---|
| `notebooks/00_data_exploration.ipynb` | Initial data exploration |
| `notebooks/01_data_preparation.ipynb` | Data cleaning and feature preparation |
| `notebooks/02_clustering_experiments.ipynb` | Clustering experiments |
| `notebooks/03_model_evaluation.ipynb` | Model evaluation, selection and cluster profiling |
| `data/processed/urban_centres_cluster_assignments.csv` | Final analytical dataset with cluster assignments |
| `PROJECT_TRACKER.md` | Project progress and milestones |
| `README.md` | Repository overview |

## 10. Next Analytical Stage

Notebook 04 will focus on geographical analysis, descriptive cluster interpretation, infrastructure comparisons and sustainability-related considerations.

The analysis will retain the distinction between exploratory infrastructure profiles and validated investment recommendations.