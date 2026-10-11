# Methods

Library Setup & Path Configuration: Loaded geospatial and mapping libraries including geopandas, pandas, folium, and branca, and established project directory paths.   

Data Ingestion:Loaded the final six-category CDI and equity layer (burnie_car_dependency_equity_6categories.gpkg) containing 56 SA1 features reprojected to EPSG:4326.   

Loaded OpenStreetMap road features for Burnie and clipped them to the unified Burnie SA1 boundary outline (reducing features from 5,112 to 4,059).   

Data Preparation: Formatted display attributes for population, IRSD scores, car/PT accessibility metrics, CDI values, and equity priority flags.   

Map Styling & Construction:Built a custom dark-themed map (#1B1C24) using Folium.   

Added the road network layer with stylized weights and opacities based on road class (fclass).   
Implemented a 5-class color scale (#2166AC to #D73027) representing lower to higher car advantage.   
Configured interactive hover tooltips and click popups displaying demographic and accessibility metrics.   
Injected custom HTML/CSS for a floating map title and a compact CDI legend.   

Mathematical Formulation
The Car Dependency Index (CDI) is a model that evaluates how easily populations at origin $i$ can reach essential opportunities $j$ (such as employment, education, and healthcare) across different transport 

:::{math}
:name: eq:cdi

CDI_i = \frac{O_{i,\text{Car}} - O_{i,\text{PT}}}{O_{i,\text{Car}} + O_{i,\text{PT}}}
:::

Where:
- $A_i$ represents the cumulative accessibility score for origin zone $i$.
- $O_j$ is the magnitude of opportunities available at destination $j$.
- $t_{ij}$ is the network travel time between origin $i$ and destination $j$.
- $\beta$ is the distance-decay parameter reflecting traveler sensitivity to travel time.

By comparing accessibility via private motor vehicles ($A_i^{car}$) against public transit ($A_i^{pt}$), the index derives a comparative ratio, quantifying the systemic advantage and reliance on private automobiles across regional mesh blocks.
:::