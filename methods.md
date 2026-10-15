# Methods

This workflow compares accessibility by **private car and public transport** across Burnie, then examines where car dependency overlaps with socio-economic disadvantage.

## Methodological Workflow

::::{grid} 1 1 2 2
:class: aligned-workflow

:::{grid-item}
:class: workflow-step

**1. Prepare spatial data**
:::

:::{grid-item}
Standardise coordinate systems and inspect geometry. Select SA1s, create representative origins, prepare destinations, and join population and IRSD.
:::

:::{grid-item}
:class: workflow-step

**2. Prepare transport networks**
:::

:::{grid-item}
Prepare OpenStreetMap roads for car routing. Combine Metro GTFS schedules with walking connections for bus journeys.
:::

:::{grid-item}
:class: workflow-step

**3. Measure accessibility**
:::

:::{grid-item}
Calculate origin–destination travel times. Assess access to services within **30 minutes**.
:::

:::{grid-item}
:class: workflow-step

**4. Compare modes and equity**
:::

:::{grid-item}
Calculate CDI from car and bus accessibility. Examine where **high CDI coincides with low IRSD**.
:::

:::{grid-item}
:class: workflow-step

**5. Check robustness**
:::

:::{grid-item}
Test alternative travel-time thresholds. Consider commuting patterns, departure times and service categories where applicable.
:::

:::{grid-item}
:class: workflow-step workflow-last

**6. Communicate findings**
:::

:::{grid-item}
Present maps, graphs and interpretation. Build and test the Jupyter Book.
:::

::::
First, five destination categories are prepared:

| Category | Preparation described in the plan |
| --- | --- |
| **Schools** | Prepare school locations |
| **Healthcare facilities** | Prepare health-facility locations |
| **Pharmacies** | Extract pharmacy destinations |
| **Supermarkets** | Extract supermarket destinations |
| **Leisure** | Extract parks & recreation destinations |

Clean spatial and tabular datasets are saved for subsequent analysis.

## 2. Transport Networks and Travel Times

## Transport Networks and Essential-Service Locations

Transport networks and destination locations were prepared to compare accessibility by **private car and public bus** across Burnie’s **56 SA1s**.

The road network was sourced from **OpenStreetMap**. Public transport routes, stops and timetables were obtained from **Metro Tasmania GTFS data**. For visualisation, the mapped networks were restricted to the Burnie study-area boundary.

Destinations were compiled from the project’s spatial datasets and grouped into six categories: **schools, healthcare facilities, pharmacies, supermarkets, greenspaces and leisure facilities**. The same destinations were used for both transport modes.

:::{figure} Images/transport_method_incl_services.png
:label: fig-transport-services
:alt: Two maps of Burnie showing the OpenStreetMap road network in panel A and public transport routes and stops in panel B, with six categories of service destinations and the study-area boundary.
:width: 100%
:align: center

**Transport networks and essential-service locations in Burnie, Tasmania.** (A) OpenStreetMap road network supporting private-car accessibility modelling. (B) Metro Tasmania GTFS public transport routes and stops. Coloured points distinguish the six destination categories. Both panels show the Burnie study-area boundary. Sources: OpenStreetMap, Metro Tasmania GTFS and compiled destination datasets. Figure prepared by the authors.
:::
[🔍 View full-size map](Images/transport_method_incl_services.png)

Most mapped destinations cluster in northern Burnie. Roads extend throughout much of the study area, while mapped bus routes follow a smaller set of corridors. These spatial patterns provide context for the travel-time analysis, which also accounts for timetables and walking connections.

## 3. Threshold Accessibility

Accessibility was calculated for Burnie's 56 Statistical Areas Level 1 (SA1s) using origin–destination travel times for private cars and public buses. Three travel-time threshold were evaluated with **30 minutes** selected as the primary scenario.

For each SA1, the proportion of destinations reachable within the specified travel-time threshold was calculated separately for each service category.

**Equation 1. Service-category accessibility**

```{math}
:label: eq-category-accessibility

A_{i,c,m}(T) =
\frac{N_{i,c,m}(T)}{N_c}
```

Where:

- $A_{i,c,m}(T)$ = accessibility proportion for SA1 $i$, service category $c$, transport mode $m$, and threshold $T$.
- $N_{i,c,m}(T)$ = number of destinations in category $c$ reachable within $T$ minutes.
- $N_c$ = total number of destinations in category $c$ in the study dataset.

The analysis included six categories: **schools, healthcare facilities, pharmacies, supermarkets, greenspaces and leisure facilities**.

The six category-specific accessibility proportions were combined using equal weighting to produce an overall accessibility score for each SA1 and transport mode.

**Equation 2. Overall accessibility score**

```{math}
:label: eq-overall-accessibility

A_{i,m}(T) =
\frac{1}{6}\sum_{c=1}^{6} A_{i,c,m}(T)
```

Each service category contributed equally to the overall score, regardless of the number of destinations within that category.

The resulting accessibility score ranges from **0 to 1**, where 0 indicates that no destinations are reachable within the selected threshold and 1 indicates that all destinations in the six categories are reachable.

Missing travel times were treated as unreachable destinations.

The analysis initially considered four essential-service categories: schools, healthcare facilities, pharmacies and supermarkets. It was subsequently expanded to include greenspaces and leisure facilities.

The **six-category, 30-minute accessibility scores** were used for the final Car Dependency Index analysis.

## 4. Car Dependency Index

The **Car Dependency Index (CDI)** compares accessibility by car with accessibility by public transport for each SA1.

```{math}
:label: eq-car-dependency
:enumerated: true

CDI_i = \frac{A_{i,\mathrm{Car}} - A_{i,\mathrm{PT}}}
{A_{i,\mathrm{Car}} + A_{i,\mathrm{PT}}}
```

Here, $A_{i,\mathrm{Car}}$ and $A_{i,\mathrm{PT}}$ represent accessibility to opportunities from SA1 $i$ by car and public transport, respectively.

| CDI value | Interpretation |
| --- | --- |
| **Close to +1** | Much better accessibility by car |
| **Positive** | Car accessibility advantage |
| **Around 0** | Similar accessibility by both modes |
| **Negative** | Public transport accessibility advantage |
| **Close to −1** | Strong public transport advantage |

If accessibility is zero for both modes, CDI is **undefined**. Such areas are classified separately as **No access**, rather than assigning a zero CDI.

## 5. Socio-Economic Equity

The planned SA1-level output brings together **SA1 code, population, IRSD score, IRSD decile, car accessibility, public transport accessibility and CDI**.

Areas with **high CDI and low IRSD** are examined for overlapping car dependency and socio-economic disadvantage. Lower IRSD indicates relatively greater disadvantage, while higher IRSD indicates relatively less disadvantage.

Population weighting is proposed where appropriate for aggregated comparisons. It is not treated as a confirmed calculation in this plan.

## 6. Context and Sensitivity Checks

| Check | Purpose |
| --- | --- |
| **ABS Method of Travel to Work** | Compare modelled accessibility patterns with observed census commuting patterns as supporting context |
| **30-minute thresholds** | Test whether conclusions change with the travel-time limit |
| **Alternative public transport departure times** | Consider timetable sensitivity if useful |
| **Selected service categories** | Consider category sensitivity if necessary |


## Notebook Sequence

| Notebook | Role in the plan |
| --- | --- |
| `01_data_preparation.ipynb` | Prepare study area, SA1 origins, demographics and destinations |
| `02_transport_network.ipynb` | Prepare networks and calculate car and public transport travel times |
| `03_accessibility_analysis.ipynb` | Calculate threshold accessibility |
| `04_car_dependency.ipynb` | Calculate CDI and examine equity |
| `05_sensitivity_analysis.ipynb` | Test the robustness of conclusions |

