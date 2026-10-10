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

I am a book about ... something! Wikipedia has [information about books](wiki:book): hover over the link for more information.

% An admonition containing a note
:::{note}
Books are usually written on paper ... But Jupyter Book can create _websites_!
:::

If you sold 100 books at \$10 per book, you'd have \$1000 dollars according to [](#eq:book). If instead you publish your Jupyter Book to the web for free, you'd have \$0 dollars!

% An arbitrary math equation
:::{math}
:name: eq:book

x \times y = z
:::

Sometimes when reading it is helpful to foster a _tranquil_ environment. The image in [](#fig:mountains) would be a perfect spot!

% A figure of a photograph of some mountains, followed by a caption
:::{figure} https://github.com/rowanc1/pics/blob/main/mountains.png?raw=true
:label: fig:mountains

A photograph of some beautiful mountains to look at whilst reading.
:::