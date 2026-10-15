# Car Dependency and Urban Accessibility in Burnie, Tasmania

**KGG375 Geospatial Data Analytics | University of Tasmania | Assessment Task 3 | Group 4 | 2026**

**Project team:** Gloria Gachara and Mishu Panta

[**Explore our Interactive Jupyter Book**](https://university-of-tasmania-gpss.github.io/AT3_Group4_2026/)

---

## 1. Project Overview

Access to essential services is an important component of urban accessibility. However, the ability to reach everyday destinations can differ considerably between private vehicles and public transport. These differences contribute to car dependency and may create inequalities in access to opportunities (Geurs & van Wee, 2004; Campanelli et al., 2026).

This project investigates **car dependency and urban accessibility in Burnie, Tasmania**, by comparing access to essential services using private cars and public buses.

The analysis covers **56 Australian Bureau of Statistics Statistical Areas Level 1 (SA1s)** and evaluates access to six service categories:

- Schools
- Healthcare facilities
- Pharmacies
- Supermarkets
- Greenspaces
- Leisure facilities

Using Python-based geospatial analysis, road networks, public transport timetables and socioeconomic data, the project examines spatial patterns of accessibility and identifies areas where reliance on private vehicles is greatest.

The study draws on accessibility concepts established by Geurs and van Wee (2004), and Levinson and Wu (2020), alongside more recent research on inclusive urban accessibility and car dependency (Bruno et al., 2024; Campanelli et al., 2026).

## 2. Research Question

**How does access to essential services within 30 minutes differ between private car and public bus across Burnie, and where does high car dependency coincide with socioeconomic disadvantage?**

### Research Objectives

1. Measure accessibility to essential services using private car and public bus networks.
2. Compare spatial accessibility patterns across Burnie's 56 SA1s.
3. Develop a Car Dependency Index (CDI) to quantify the relative accessibility advantage of private cars.
4. Examine the relationship between car dependency and socioeconomic disadvantage using ABS SEIFA IRSD data.
5. Interpret the findings and discuss implications for equitable transport planning.

## 3. Study Area

Burnie is a regional coastal city in north-west Tasmania, Australia. Its urban settlements are concentrated near the coast, while inland areas contain more dispersed residential and rural landscapes.

These contrasting settlement patterns provide an opportunity to investigate differences in transport accessibility.

The study uses 56 SA1s as its spatial units of analysis, based on the Australian Statistical Geography Standard (ABS, 2021).

## 4. Data Sources

| Dataset | Source | Application |
|---|---|---|
| SA1 boundaries | Australian Bureau of Statistics (2021) | Study-area definition and spatial analysis |
| Population and commuting characteristics | ABS Census 2021 | Demographic and travel-to-work context |
| SEIFA Index of Relative Socio-economic Disadvantage | ABS (2023) | Socioeconomic analysis |
| Road network | OpenStreetMap | Private-car routing |
| Bus routes, stops and timetables | Metro Tasmania GTFS | Public transport accessibility |
| Cadastral and community spatial datasets | LIST Tasmania | Supporting spatial information |
| Service destinations | Compiled project datasets, LIST and OpenStreetMap | Essential-service accessibility |
| Satellite imagery | Esri | Study-area mapping |

## 5. Methodology

The project follows a Python-based geospatial workflow combining spatial data preparation, transport network modelling, accessibility analysis and socioeconomic interpretation.

### Step 1: Spatial Data Preparation

The Burnie study-area boundary and 56 SA1 polygons were prepared and standardised. Representative SA1 origins, service destinations and supporting demographic information were assembled.

### Step 2: Transport Network Preparation

OpenStreetMap road-network data were used to support private-car travel-time modelling.

Metro Tasmania GTFS data, including bus routes, stops and timetables, were used to represent public transport services, together with walking connections.

### Step 3: Accessibility Analysis

Accessibility was assessed by determining the availability of essential-service opportunities within a **30-minute travel-time threshold**.

The analysis compared private-car and public bus accessibility across six service categories.

### Step 4: Car Dependency Index

A Car Dependency Index was calculated to compare accessibility between the two transport modes.

**CDI = (A_car − A_bus) / (A_car + A_bus)**

Where:

- **A_car:** Accessibility by private car
- **A_bus:** Accessibility by public bus

The CDI ranges from −1 to +1 when defined.

- Values approaching +1 indicate a greater accessibility advantage for private cars.
- Values around 0 indicate similar accessibility between transport modes.
- Negative values indicate an accessibility advantage for public transport.

Where both accessibility scores are zero, the CDI is undefined and must be interpreted separately.

This approach provides a relative measure of car dependency. The conceptual motivation is informed by research on accessibility and car dependency, particularly Campanelli et al. (2026). The equation above describes the index implemented in this project.

### Step 5: Socioeconomic Analysis

CDI values were compared with the ABS Index of Relative Socio-economic Disadvantage (IRSD).

Lower IRSD scores represent relatively greater socioeconomic disadvantage, while higher scores represent relatively less disadvantage (ABS, 2023).

Pearson and Spearman correlations were used to examine the association between CDI and IRSD for SA1s with available data.

### Step 6: Visualisation and Interpretation

The results were presented through static maps, an interactive CDI map and an interactive socioeconomic scatter plot.

The analysis also considers modelling assumptions and limitations, including the use of representative SA1 origins, travel-time thresholds, scheduled bus services and the distinction between relative car dependency and absolute accessibility.

## 6. Key Results

### Accessibility by Private Car and Public Bus

The 30-minute accessibility comparison shows a widespread advantage for private cars across Burnie in six categories "schools, healthcare facilities, pharmacies, supermarkets, greenspaces and leisure facilities". 

Public bus accessibility is generally more limited, although parts of northern urban Burnie show smaller differences between transport modes.

### Spatial Patterns of Car Dependency

The interactive CDI map demonstrates substantial spatial variation across the study area.

Higher CDI values indicate greater relative accessibility by private car, but do not necessarily indicate that an area has good overall access to essential services.

Some SA1s have high CDI values despite low absolute car accessibility.

### Car Dependency and Socioeconomic Disadvantage

The CDI–IRSD analysis includes **54 SA1s** with available socioeconomic data.

The calculated correlations were:

| Statistical measure | Result |
|---|---|
| Pearson correlation | 0.333 |
| Spearman correlation | 0.489 |
| Sample size | 54 SA1s |

The positive association suggests that SA1s with higher CDI values tend to have higher IRSD scores in this sample.

Because higher IRSD scores indicate relatively less disadvantage, these findings do not demonstrate that greater car dependency consistently coincides with greater socioeconomic disadvantage.

The analysis is correlational and does not establish causation.

## 7. Interactive Visualisations

The published Jupyter Book includes:

**Interactive Car Dependency Map**

Explore the spatial distribution of CDI values across Burnie's 56 SA1s, with road-network context and interactive map controls.

**Interactive CDI–IRSD Scatter Plot**

Explore the relationship between car dependency and socioeconomic disadvantage, including the fitted linear trend and correlation statistics.

**[View Interactive Results](https://university-of-tasmania-gpss.github.io/AT3_Group4_2026/results/)**

## 8. Tools and Technologies

The project uses Python and geospatial analysis tools, including relevant libraries for spatial data handling, numerical analysis, network modelling and visualisation.

The outputs are presented using:

- Jupyter Notebook
- Python
- MyST Jupyter Book
- Folium and Leaflet for interactive mapping
- Plotly for interactive statistical visualisation
- Git and GitHub for version control and collaboration
- GitHub Pages for website publication

Additional Python dependencies are documented within the project's notebooks and environment configuration where available.

## 9. Repository Structure

| File or directory | Purpose |
|---|---|
| `01_data_preparation.ipynb` | Prepare spatial and demographic datasets |
| `02_transport_network.ipynb` | Prepare transport networks and travel-time calculations |
| `03_accessibility_analysis.ipynb` | Calculate service accessibility |
| `04_car_dependency.ipynb` | Analyse CDI and socioeconomic relationships |
| `05_sensitivity_analysis.ipynb` | Examine sensitivity and robustness |
| `06_final_maps.ipynb` | Prepare final maps and visualisations |
| `Maps/` | Maps and interactive outputs |
| `Outputs/Maps/` | Additional mapping outputs |
| `Images/` | Supporting images |
| `myst.yml` | Jupyter Book configuration |
| `index.md` | Introduction |
| `study_area.md` | Study area and datasets |
| `methods.md` | Methodology |
| `results.md` | Results |
| `discussion.md` | Discussion |
| `conclusion.md` | Conclusions |
| `readme.md` | Repository overview, documentation, and build instructions |

## 10. Limitations

The results should be interpreted within the assumptions of the accessibility model.

Important considerations include:

- Using one representative origin for each SA1 rather than individual household locations.
- Applying a 30-minute threshold to assess accessibility.
- Representing public transport using scheduled services and selected travel conditions.
- Differences between relative car dependency and absolute accessibility.
- Variation in destination availability and service quality.
- The ecological limitations of analysing socioeconomic relationships using aggregated SA1 data.

These factors may influence the interpretation of accessibility inequalities and the transferability of findings to individual residents.

## 11. Team Contributions

This project was developed collaboratively by **Gloria Gachara and Mishu Panta**, with responsibilities divided across geospatial analysis, visualisation, documentation and website development.

### Gloria Gachara

- Developed and refined the Burnie study-area map and supporting spatial visualisations.
- Prepared the final private-car and public transport accessibility comparison maps.
- Developed the interactive Car Dependency Index map.
- Developed the interactive CDI–IRSD scatter plot.
- Contributed to interpreting spatial patterns of car dependency and socioeconomic disadvantage.
- Integrated and tested interactive outputs within the Jupyter Book.

### Mishu Panta

- Downloaded data for use.
- Developed and organised the Jupyter Book website structure, navigation and content presentation.
- Prepared and refined the project documentation, including the introduction, study area, methods, results, discussion and conclusion.
- Contributed to documenting the analytical workflow and explaining the project findings.
- Supported repository management, GitHub integration, troubleshooting and publication of the website.

### Joint Contributions

Both team members contributed to project planning, analytical discussions, reviewing outputs, troubleshooting, interpreting results and preparing the final submission.

## 12. Acknowledgements

We acknowledge the **University of Tasmania** and the **KGG375 Geospatial Data Analytics teaching team** for providing the academic framework and guidance for this project.

We also acknowledge the Australian Bureau of Statistics, OpenStreetMap contributors, Metro Tasmania, LIST Tasmania and Esri for the datasets and mapping resources supporting the analysis.

The research was informed by academic literature on accessibility, car dependency, transport equity and inclusive urban planning.

## 13. References

### Academic Literature

Bruno, M., Monteiro Melo, H. P., Campanelli, B., & Loreto, V. (2024). A universal framework for inclusive 15-minute cities. *Nature Cities, 1*, 633–641. https://doi.org/10.1038/s44284-024-00119-4

Campanelli, B., Marzolla, F., Bruno, M., Monteiro Melo, H. P., & Loreto, V. (2026). *Car dependency in urban accessibility*. arXiv. https://arxiv.org/abs/2604.01019

Geurs, K. T., & van Wee, B. (2004). Accessibility evaluation of land-use and transport strategies: Review and research directions. *Journal of Transport Geography, 12*(2), 127–140. https://doi.org/10.1016/j.jtrangeo.2003.10.005

Levinson, D. M., & Wu, H. (2020). Towards a general theory of access. *Journal of Transport and Land Use, 13*(1), 129–158. https://www.jstor.org/stable/26967239

Wiersma, J. K., Bertolini, L., & Harms, L. (2021). Spatial conditions for car dependency in mid-sized European city regions. *European Planning Studies, 29*(7), 1314–1330. https://doi.org/10.1080/09654313.2020.1854691

Wu, H., Avner, P., Boisjoly, G., Braga, C. K. V., El-Geneidy, A., Huang, J., Kerzhner, T., Murphy, B., Niedzielski, M. A., Pereira, R. H. M., Pritchard, J. P., Stewart, A., Wang, J., & Levinson, D. (2021). Urban access across the globe: An international comparison of different transport modes. *npj Urban Sustainability, 1*, Article 16. https://doi.org/10.1038/s42949-021-00020-2

### Data and Mapping Sources

Australian Bureau of Statistics. (2021). *Australian Statistical Geography Standard (ASGS) Edition 3: Digital boundary files*. https://www.abs.gov.au/statistics/standards/australian-statistical-geography-standard-asgs/edition-3-july-2021-june-2026/access-and-downloads/digital-boundary-files

Australian Bureau of Statistics. (2023). *Socio-Economic Indexes for Areas (SEIFA), Australia, 2021*. https://www.abs.gov.au/statistics/people/people-and-communities/socio-economic-indexes-areas-seifa-australia/2021

Esri. (n.d.). *ArcGIS Living Atlas of the World*. https://livingatlas.arcgis.com/

Metro Tasmania. (n.d.). *Metro Tasmania*. https://www.metrotas.com.au/

OpenStreetMap contributors. (n.d.). *OpenStreetMap*. https://www.openstreetmap.org/copyright

Tasmanian Government. (n.d.). *The LIST: Land Information System Tasmania*. https://www.thelist.tas.gov.au/

### Supporting Planning Example

National Transport Authority. (n.d.). *Connecting Ireland*. https://www.nationaltransport.ie/connecting-ireland/

---

## Academic Context

This project was developed for **KGG375 Geospatial Data Analytics, Assessment Task 3**, at the University of Tasmania in 2026.

The analysis is intended to demonstrate the application of geospatial data processing, transport accessibility modelling, spatial visualisation and socioeconomic interpretation to Burnie, Tasmania.