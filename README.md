
# AI-Readiness Investment Intelligence for Africa: An Unsupervised Machine Learning Framework for Infrastructure Investment Screening

## Project Overview

This project develops an exploratory, data-driven framework for AI-enabling infrastructure investment screening across Africa, integrating unsupervised machine learning and geospatial analysis.

The project was undertaken as part of the Certified Data Scientist qualification at Digethic Digital Business School, Germany, within a simulated consulting assignment for the African Development Bank (AfDB).

## Research Question

What distinct AI-enabling infrastructure and socioeconomic profiles exist across Africa, and how can these profiles inform exploratory infrastructure investment screening?

## Dataset

- Geographical coverage: Africa
- Units of analysis: 2,172 urban centres
- Clustering predictors: 12
- Principal data source: Global Human Settlement Layer (GHSL) Urban Centre Database (R2024A)
- Supplementary data sources: ITU terrestrial fibre connectivity and PeeringDB

## Methodology

The project follows the CRISP-DM framework and includes:

- Data acquisition, integration and quality assessment
- Exploratory data analysis
- Feature transformation and standardisation
- K-Means clustering
- Agglomerative Hierarchical Clustering (Ward linkage)
- Model evaluation using Silhouette Score, Davies–Bouldin Index and Adjusted Rand Index
- Cluster stability and sensitivity analysis
- Infrastructure profile characterisation
- Geographical analysis and investment-screening interpretation

## Key Findings

The selected K-Means model (k = 3) identified three infrastructure profiles:

| Cluster | Urban centres | Distinguishing characteristics |
|---|---:|---|
| 0 | 522 (24.0%) | Relatively stronger economic, energy and transport conditions |
| 1 | 1,380 (63.5%) | Below-average conditions across most infrastructure and socioeconomic indicators |
| 2 | 270 (12.4%) | Relatively stronger telecommunications, education, transport and water infrastructure |

The findings support two complementary investment-screening objectives:

- Identifying locations with potentially favourable conditions for AI-related infrastructure development.
- Identifying locations where foundational investments may support broader and more equitable participation in the AI economy.

## Scope and Limitations

The identified clusters represent exploratory infrastructure profiles, not validated AI-readiness scores, investment rankings or evidence of project bankability.

The empirical analysis focuses on urban centres and does not directly capture all dimensions of AI readiness, including computing capacity, AI-specific skills and institutional readiness.

## Repository Structure

- `data/processed/` — Processed analytical datasets
- `notebooks/` — Python notebooks and analytical workflow
- `outputs/figures/` — Analytical and geographical visualisations
- `METADATA.md` — Dataset documentation
- `PROJECT_TRACKER.md` — Project implementation progress
- `requirements.txt` — Python dependencies

## Technologies

Python, Jupyter Notebook, unsupervised machine learning and geospatial analysis.

## Author

Purity Rima Mbaabu

Certified Data Scientist Project Work

November 2026
