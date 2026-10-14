# **KGG375 Geospatial Data Analytics | University of Tasmania | Group 4 | 2026**
Car Dependency and Essential-Service Accessibility in Burnie, Tasmania.

## Group Members
- Gloria Gachara
- Mishu Panta

## Project Overview

This project investigates differences in accessibility to essential services by private car and public bus across Burnie, Tasmania.

Using 56 Australian Bureau of Statistics Statistical Areas Level 1 (SA1s), we compare access to schools, healthcare facilities, pharmacies, supermarkets, greenspaces and leisure facilities.

The analysis uses a 30-minute travel-time threshold to examine spatial patterns of accessibility and car dependency, alongside socioeconomic disadvantage.

## Research Question

How does access to essential services within 30 minutes differ between private car and public bus across Burnie, and where does high car dependency coincide with socioeconomic disadvantage?

## Explore the Interactive Jupyter Book

**[View the published project website](https://university-of-tasmania-gpss.github.io/AT3_Group4_2026/)**

The website contains the study area, datasets, methods, maps, interactive results, discussion and conclusions.

## Key Outputs

- **Study Area Map:** Burnie and its 56 SA1 analysis units.
- **Transport Network Map:** Private-car road network, public bus routes and essential-service locations.
- **Accessibility Comparison:** Spatial differences in 30-minute accessibility by car and public bus.
- **Interactive Car Dependency Map:** SA1-level CDI values, with road context and interactive map controls.
- **CDI and SEIFA Scatter Plot:** Relationship between car dependency and the ABS Index of Relative Socio-economic Disadvantage (IRSD).

## Selected Findings

- Private-car accessibility generally exceeds public bus accessibility across the study area.
- Some northern urban SA1s show a smaller accessibility gap between transport modes.
- A high Car Dependency Index does not necessarily mean that an area has high absolute accessibility.
- For the 54 SA1s with available IRSD data, the CDI–IRSD association is positive (Pearson r = 0.333; Spearman ρ = 0.489). Lower IRSD scores indicate greater socioeconomic disadvantage.

## Data Sources

- Australian Bureau of Statistics: SA1 boundaries, Census data and SEIFA IRSD.
- OpenStreetMap: Road network and selected service locations.
- Metro Tasmania: Public transport GTFS schedules, routes and stops.
- LIST Tasmania: Spatial boundaries and selected community datasets.
- ESRI: Satellite basemap imagery.

## Methods

The project follows a geospatial analysis workflow:

1. Prepare spatial data and SA1 analysis units.
2. Construct road and public transport networks.
3. Calculate travel-time-based accessibility.
4. Compare car and public transport accessibility using the Car Dependency Index.
5. Examine socioeconomic patterns using IRSD.
6. Interpret findings and discuss modelling limitations.

The analysis was conducted using Python and geospatial datasets, with results presented through MyST Jupyter Book.

## Repository Contents

- `01_data_preparation.ipynb` – Data preparation
- `02_transport_network.ipynb` – Transport networks
- `03_accessibility_analysis.ipynb` – Accessibility analysis
- `04_car_dependency.ipynb` – Car Dependency Index
- `05_sensitivity_analysis.ipynb` – Sensitivity analysis
- `06_final_maps.ipynb` – Final mapping
- `Images/` – Supporting figures
- `Maps/` and `Outputs/Maps/` – Generated maps and interactive outputs
- `myst.yml` – Jupyter Book configuration
- `index.md`, `methods.md`, `results.md`, `readme.md`, `discussion.md`, `conclusion.md` – Website content

## Reproducibility

The notebooks document the analytical workflow. Reproducing the analysis requires a compatible Python environment and access to the relevant input datasets.

The published Jupyter Book provides a convenient way to explore the project without running the notebooks locally.

## Team

**University of Tasmania – KGG375 Geospatial Data Analytics, Group 4**

Gloria Gachara

Downloaded necessary data: SA1 Boundaries, METRO data, and ABS SEIFA data.

Developed and refined the spatial visualisations, including the Burnie study-area map and car-versus-public-transport accessibility maps.

Developed the interactive Car Dependency Index (CDI) map and the CDI–SEIFA socioeconomic scatter plot.

Contributed to interpreting spatial accessibility patterns and socioeconomic disadvantage.

Supported the integration and presentation of interactive visualisations within the Jupyter Book website.

Mishu Panta

Downloaded necessary data: Cadastral Parcels, Open Street Map road network, ABS Census, POIs from LIST, and Basemap from ESRI.

Developed and organised the Jupyter Book website structure, including its main sections and navigation.

Prepared and refined the project's written documentation, including the introduction, study area, methods, results, discussion and conclusion.

Contributed to the presentation of the analytical methodology, datasets and research findings.

Supported GitHub repository management, website integration and publication.

Joint Contributions

Both team members contributed to project planning, geospatial analysis, reviewing results, troubleshooting, and refining the final Jupyter Book website. 

## Academic Context

This repository was developed for AT3 Project for KGG375. The findings reflect the selected datasets, accessibility modelling assumptions and study-area definitions.