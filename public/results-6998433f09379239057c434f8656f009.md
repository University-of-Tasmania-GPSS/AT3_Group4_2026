# Results

- **Output Artifact:** Executing the notebook generates the publication-ready **Burnie CDI 30-Min Interactive Map Display**, rendering 56 SA1 polygon features and 4,059 clipped OpenStreetMap road segments over a custom dark base (`#1B1C24`).

- **Spatial Categorization & Model Advantage:** 
  - **Categories 1 & 2 (Public Transit Advantage / Parity):** Concentrated in central Burnie and inner suburbs, where high stop density yields competitive public transit travel times ($A_i^{\text{pt}} \approx A_i^{\text{car}}$).

  - **Categories 3 & 4 (Moderate to High Dependency):** Covers middle-ring residential zones (e.g., Shorewell Park, Acton) where service frequencies drop and transfer delays expand the $A_i^{\text{car}} / A_i^{\text{pt}}$ gap.

  - **Categories 5 & 6 (Severe & Extreme Disadvantage):** Dominates peri-urban and steep peripheral SA1s (e.g., Havenview, Ridgley fringe), where transit options fail to provide functional access within 30 minutes.

- **Equity & Disadvantage Overlap:** Cross-tabulating the 6 CDI categories with IRSD scores identifies specific high-priority SA1s where low socio-economic status intersects with high automotive reliance.

- **Interactive Features:** Hover tooltips display immediate CDI classification, while click popups expose underlying block-level attributes (population, IRSD decile, raw $A_i^{\text{car}}$ and $A_i^{\text{pt}}$ scores, and equity flags).

<iframe src="./Outputs/Maps/burnie_cdi_30min_interactive.html" width="100%" height="550px" style="border:none;"></iframe>