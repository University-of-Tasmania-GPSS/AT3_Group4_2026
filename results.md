# Results

:::{figure} Images/transport_map.png
:label: fig-transport-map
:alt: Transport map supporting the Burnie accessibility analysis.
:width: 100%
:align: center

Transport context for comparing accessibility by private car and public bus in Burnie.
:::

## Interactive Car Dependency Map

The **Burnie CDI 30-Minute Interactive Map** compares accessibility by private car and public bus across Burnie.

| Map component | Description |
| --- | --- |
| **Analysis units** | 56 SA1 polygons |
| **Road context** | 4,059 clipped OpenStreetMap road segments |
| **Travel-time threshold** | 30 minutes |

:::{iframe} ../burnie_cdi_30min_interactive.html
:width: 100%
:::
*Figure 1: Interactive map of 30-minute car dependency across Burnie’s 56 SA1s. Higher CDI values indicate a greater accessibility advantage by private car compared with public bus.*

## Interpreting Car Dependency Scatter Plot

Explore the relationship between car dependency and socio-economic disadvantage across Burnie’s SA1s.

:::{iframe} ../burnie_cdi_seifa_scatter_interactive.html
:width: 100%
:::
*Figure 2: Car dependency and socio-economic disadvantage across 54 Burnie SA1s with available IRSD data. Lower IRSD scores indicate greater disadvantage, while higher CDI values indicate greater car advantage. The dashed line shows the fitted linear trend.*
